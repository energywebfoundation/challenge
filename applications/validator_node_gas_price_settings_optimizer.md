# Energy Web Innovation Challenge Proposal

* **Project Name**: Validator Node Gas Price Settings Optimizer Module (VNGPO)
* **Project Proposer GitHub**: <https://github.com/ttimon7/challenge>
* **Energy Web Chain Payment Address**: 0x37d32444BF9cF87600987279Eb24d03c90e0561b

## Project Description

### Summary

Our proposal introduces VNGPO, an open-source, locally-runnable software component, capable of providing a dynamic gas-price-management service to the validator nodes. As we demonstrate below, replacing the currently used static settings with dynamic ones is indispensable for enhanced network security, and reaching the gas-price expenditure optimum.

### Motivation and background

#### The gas system and its intended purpose

State changes of EVM based chains are performed by executing transactions which can be contract function calls or native token transfers initiated by external accounts. Each node in the blockchain network runs the same protocol, thus performs the same computations and stores the same values. In order to protect such a distributed system against spam attacks and congestion, a gas mechanism was introduced.

Each unit of EVM operation (opcode) is accounted for by having a scalar value assigned to it called gas cost. Therefore each and every transaction has a certain load on the nodes measured in gas used, capped by the block gas limit, and has to be paid for by the sender of the transaction in native tokens. This is done so by specifying a gasPrice parameter which is the price of one unit of gas the sender is willing to pay for.

Validator (or miner) nodes are responsible for fetching pending transactions from the transaction pool and weaving them into blocks while taking the transaction fees for their execution according to the gas used * gasPrice  formula for each separate transaction included.

Which transactions validators take from their pool is actually up to their discretion. The incentive model of the Ethereum protocol assumes that validators are profit maximizers, thus they sort transactions by gasPrice and try to include as many as they can into one block. Not choosing to do so is possible, but it results in a competing validator/miner reaping the transactions with higher fees.
As transaction senders also get a free hand in choosing the gasPrice, they can set higher prices if they want their transactions to be prioritized by validators over other ones. Assuming profit maximization, senders try to find the minimum gasPrice that gets the transaction through with the maximum acceptable delay.
This, in theory, should result in an efficient gas market and gasPrice equilibrium. If there are more pending transactions in the network that the nodes can handle, prices organically increase to resolve the congestion (which is indifferent from malicious network spamming), and organically decrease otherwise.

It is important to note that in practice there are some technical limitations to the system. There is no “global” or “the” transaction pool. Because resources are finite, each node maintains its local transaction pool in memory, fixed in size to store pending transactions, referred to as mempool or transaction queue, and each node circulates transactions with their connected peers which is also limited in size. Validators might not even see all transactions globally. They get an additional filter though to prevent senders, benign or malicious alike, from clogging up the precious mempool with less valuable transactions by specifying a minimum accepted gasPrice. Transactions not meeting the threshold are not included in the pool, often doomed to circulate in the network for a long time or dropped altogether. This setting is one of the main measures to control the gas market on the demand side, giving the network its immune system against spam type attacks.

#### Problem formulation

Currently Energy Web’s validator nodes, both on Volta and on Energy Web Chain use a static minimum-accepted-gasPrice setting of 1 wei (<https://github.com/energywebfoundation/ewc-validator-node-install-scripts/blob/master/ewc-affiliate/install-validator-ubuntu-server-18.04-production.sh#L498>). While this can be easily changed, it is not ideal for the following reasons:

* If the setting is static and the price is set low, it is entirely possible for a malicious spammer to clog transaction pools, thus the network, if initiating enough, low fee transactions, which results in the denial of service (DoS) for others. As of now there seems to be no automated process for detecting and preventing such an event, only manual which is ineffective, and unsafe as it relies on human interaction.
* If the setting is static but high, spamming might be prevented, but results in an inefficient gas market by artificially keeping transactions costs unjustifiably high, resulting in a waste of funds and dissatisfaction of users.

A solution would be to dynamically adjust minimum gas price settings to filter on the validator side. This parameter should be continuously and automatically adjusted based on measured network conditions. If there is no traffic, low priced transactions should be allowed to incentivize network usage. In case of full blocks and filling pools, the price floor should be continuously raised so that overly cheap, spam-like transactions are not even considered in the pool, giving space to useful traffic and resulting in a healthy immune system of the network. Having such a capability would render these types of attacks useless.

### Solution Overview

Our proposed solution is called Validator Node Gas Price Optimizer module (work title VNGPO) which would be an additional, optional, open-source software component running next to EnergyWeb validator nodes (see figure 1).

VNGPO would be an optional, easily installable system component, whose purpose is to deliver a direly missing security feature, dynamic gas price modulation, to the Energy Web Chain. It would achieve said purpose by monitoring blockchain transactions, and based on historical data, predict/detect the emergence of congestion inducing situations, no matter whether they are caused by malicious or non-malicious intent, and dynamically reconfigure the node’s Parity client in order to mitigate the threat. Once the threat is bygone, or predicted to subside, VNGPO shall adjust gas prices to a more economic level inciting network usage.

The proposed sub-system can, and should, be implemented in a manner that makes it transparent to operate and easy to adapt, with algorithm choices being configurable. This proposal will outline a simple yet complete algorithm that can be used directly in the prototype, but once telemetry data is available we encourage the research and development of more advanced, and possibly more optimal, alternatives.

![Figure 1. System-components](https://drive.google.com/file/d/1NEgIAOkuO4zYXCDb3O0dvbwYj7Nf0oTe/view?usp=sharing)

**Figure 1.** System-components

Source: <https://energyweb.atlassian.net/wiki/spaces/EWF/pages/703922247/System+Architecture>

### Algorithm Outline

Historically, DoS attacks on a blockchain have appeared either as a multitude of subsequent, minimal-fee transactions or repeated low-fee, long-execution-time opcode calls. Both of which exhibit time based characteristics, which implies that a threat detection algorithm based on a simple regression model using time-series data might be suitable, once the right feature set has been identified (Sequential Change-Point Detection and Wavelet-based detection algorithms are widely used to detect DoS attacks in traditional, non-blockchain based systems).

As a proof of concept, we propose a regression based approach, where the following features should be taken into consideration when forming the input vector:

* the amount of submitted transactions
* median transaction amount
* median transaction cost
* median transaction amount per account of top X account with the lowest transaction costs
* median transaction data size
* transaction target account occurrence frequency among submitted transaction requests

All historical data should be included in the feature vector metrics, not just the one derived from the current transaction pool, as relevant transaction requests previously rejected serve also as valuable sources of information during an ongoing attack; therefore such information should be locally persisted with a Time-To-Live (TTL) value to be determined. Time series databases, such as InfluxDB would be ideal for this purpose.

We propose an overlapping sliding-window approach to be taken when compiling the feature vector, whose width and step size parameters should be determined under simulation.

### Proposed Requirements & Deliverables

Since VNGPO is meant to be an optional component, it must be designed in a way that makes its presence transparent to other nodes in the network, and provide a seamless transition when upgrading from VNGPO-less setups. In order to ensure that, we found the following qualities to be desired:

* **Security**: since VNGPO will be introduced to patch a well-known vulnerability, its implementation must make sure that it does not introduce another vulnerability.
* **Transparency**: in order to facilitate compatibility with VNGPO-less setups, communication with a network node guarded by a VNGPO should not require any change in the communication scheme being used.
* **Modularity and configurability**: algorithm theory, just like the EW network itself, is constantly evolving. Certain algorithms are found to be superior to others when applied to certain scenarios and topologies; therefore the system must be designed in a way that can accommodate new implementations of control strategies in the form of packages, and enable the user to freely choose the algorithm in which he trusts the most. On the other hand, only proven, secure, and able algorithms should be made available this way, in order to comply with the security criteria, and maximize user satisfaction.
* **High availability**: the system must be up and running whenever the node it provides filtering services to is operational.
* **Persistence**: to the same extent as the underlying node, the system must retain state, so that filtered transactions remain excluded even after an unforeseen system failure.
* **Robustness**: the system must retain its responsiveness, even in the face of systematic attacks directed against it.
* **Resilience**: in case the VNGPO sub-system gets terminated either due to resource shortage, a system error, or any other kind of malfunction, VNGPO must be able to recover, and continue protecting its dedicated node. In order to adhere to the security quality, nodes must be prevented from accepting incoming connections until the corresponding VNGPO is recovered.
* **Easy deployability**: it is highly desirable for the VNGPO to be easily deployable along with the other EW system components, in order to mitigate setup complexity for EW node operators.
* **Monitorability**: VNGPO should be designed in a way that allows optional telemetry collection upon the consent of node operators as other EW components do. This shall enable the creation of an Early Warning System (EWS), that can alert operators of ongoing attacks, and ease the process of providing improved services.

Docker containers provide ideal deployment candidates, as they are easy to distribute, set up, they provide code isolation, guarantee cross platform operability, and once orchestrated through a suitable solution, such as Docker Compose, can be automatically restarted upon malfunction (Security, Resilience, High availability)

Security goes beyond dockerization. The actual implementation should prevent remote access to the application code, configuration and run environment, and should only allow data to be fed into the system from trusted sources. This shall not impair the modularity and configurability constraints, as they do not require remote access in any way. Modules implementing alternative/improved congestion control methods should ship with the updated application image, whose signature can be easily verified; and configuration should only be edited by the system administrator, locally, during the deployment phase.

Transparency is guaranteed by not setting up the system as a proxy between the Parity client and the network, but rather in parallel to the already existing architecture.

The application should ship with a database providing persistence, configured in a local-network setup, to further mitigate attack surfaces.

Robustness is a matter choosing the right programming language, architecture, and communication scheme within software components. We propose the use of a low-level system programming language, such as Rust or C, but there are no ready-made answers for choosing the optimal architecture and communication schemes, as many possible combinations would equally suffice, nevertheless, in case the communication between the persistent datastore and the application becomes a bottleneck, the implementation of an in-memory data store, as in interposing caching layer is advised (Redis or Memcached might be suitable choices).

In order to provide the same monitorability as other EW-DOS components have, a module with implementing the necessary API should be included.

The solution should comprise of the following deliverables:

* The test-driven development and implementation of the modular VNGPO micro-framework components:

  * data storage and retrieval module (+tests)
  * algorithm selection module (+tests)
  * Parity configuration module (+tests)
  * logging module (+tests)
  * monitoring interface (+tests)

* The development and implementation of a testing framework capable of simulating DoS type attacks on the EW test chain.
* The development and implementation of the prototype algorithm

  * implementation of feature extraction modules
  * the actual implementation of the algorithm
  * isolating useful features (based on test results)
  * fine-tuning the configuration parameters (based on test results)

## Team

* **Members**:
  * Timon Tomás ([LinkedIn](https://www.linkedin.com/in/ttimon/))
  * Richard B. N. ([LinkedIn](https://www.linkedin.com/in/richard-nagy-b073a7156/))
* **Code Repositories**: <https://github.com/ttimon7>
* **Website**: not applicable
* **Team's Experience**:
We are a team of blockchain enthusiasts who strongly believe that blockchain technology has a relevant place in the future. We love to participate in blockchain-related events, and choose our challenges with this technology in mind. Being multiple years into the ‘crypto game’, we actively trade cryptocurrencies, have participated in ICOs and also have experience in mining. We both share an engineering and coding background, Timon having vast experience in software development and data science, and Richard in system architectures, and testing. We are proud of our diverse skill set and multidisciplinary knowledge that has helped us gain insight when solving challenging problems in the past; we adamantly believe that our ideas can be a valuable asset to the Energy Web project.

## Development Roadmap

### Milestone 1: The development and implementation of the VNGPO micro framework using a dev network

*Man-hour estimate*: 80

### Milestone 2: The development and implementation of a testing framework

*Man-hour estimate*: 60

### Milestone 3: The development and implementation of the prototype algorithm

*Man-hour estimate*: 120

### Milestone 4: Successfully passing tests of various scenarios on a dev network

*Man-hour estimate*: 40

### Milestone 5: Passing integration and QA tests

*Man-hour estimate*: 40

### Milestone 4: Successfully passing tests of various scenarios on the live Volta test network

*Man-hour estimate*: 40

### Milestone 6: Successfully deploying the first working instance in the live environment

*Man-hour estimate*: 12

**Total estimated man-hour investment**:  392 (with 25% margin of error as a first round estimate)
