# Energy Web Innovation Challenge Proposal
* **Project Name**: EW-TEE: Confidentiality Through Trusted off-chain Execution for EW Chain
* **Project Proposer GitHub**: https://github.com/scs
* **Energy Web Chain Payment Address**: 0x02E4E8A26eDD4277031876432531F53bC19D2eD5

## Project Description

SCS has developed [SubstraTEE](https://www.substratee.com) for the Polkadot ecosystem and proposes to port this solution to the EW Chain. Let the working title be **EW-TEE**.

SubstraTEE is a framework for trusted off-chain computation. Confidential data can be processed in Intel SGX "worker" enclaves while using the blockchain as a root of trust for enclave attestation. The chain currently also takes care of transaction ordering - completely blind to what the encrypted transactions contain. A high-level introduction is given in [our introductory medium article](https://medium.com/polkadot-network/have-a-tee-with-polkadot-7ea052e4d69a)

Our solution requires trust in Intel as a manufacturer of CPU's as well as a provider of attestation services (IAS). Intel SGX offers *integrity* and *confidentiality* guarantees: Intel can remotely attest that a specific software (identified by the binary's hash) is executed on a genuine Intel CPU platform. Alternative platforms are being evaluated by SCS but as of today, Intel SGX is the only platform meeting [our trust model](https://www.substratee.com/security.html).

The advantage of combining the concept of TEEs with blockchain is that we can decouple the trust in the workers from Intel attestation services (IAS) for end-users. Workers must obtain a commercial license with Intel in order to perform remote attestation (RA). The blockchain performs transparent validation of RA on behalf of end users who don't want to register an account with Intel before using the system. This way, the blockchain acts as a trusted registry of attested worker enclaves. The advantages of blockchain become even more evident when manufacturers would register their devices directly on the chain in the future (i.e. [Keystone enclaves](https://keystone-enclave.org/)).

The maturity level of substraTEE is still experimental. [Encointer](https://encointer.org) will be the first live network based on this framework, to be deployed in June 2020. 

### EW Flex with privacy and scalability

The [EW Flex](https://www.energyweb.org/technology/toolkits/ew-flex/) system allows prosumers behind the meter to participate in flexibility markets. A prosumers' flexibility offers represent sensitive data because they contain behavioral information about the persons living in a household. In the EU, such data is protected by GDPR. According to the [EU Blockchain observatory](https://www.eublockchainforum.eu/sites/default/files/reports/20181016_report_gdpr.pdf?width=1024&height=800&iframe=true), sensitive data may not even hit the blockchain in encrypted form (because the encryption key could leak in the future) and the right to be deleted is in contradition to immutable ledgers - for data stored on that ledger. Off-chaining state and computation is our recommended approach to compliance with regulations.

The current solution requires the entity who performs the market matching to know and process sensitive data. As we will show, the goal of decentralization doesn't have to be in contradiction with privacy. To the contrary: We can offer transparency of the process while keeping data ownership with the user. The user can share her data with well-defined algorithms executed inside TEE enclaves selectively.

EW-TEE enables private smart contracts. For the EW Chain this would allow to keep sensitive data off-chain and process the data inside SGX enclaves. This way, the operator of the EW-TEE-worker doing the matchmaking doesn't see the offer data.

Moreover, EW-TEE has the potential to scale the solution as it is effectively a 2nd layer solution and already supports sharding. You can take certain smart contract invocations off-chain entirely. Measurement data doesn't need to be supplied

### EW Origin with privacy

A similar reasoning applies to EW Origin. If you'd like to get real-time certificates of the exces PV energy your houshold sells, the profile of the houshold's consumption may leak when comparing curves with neighboring PV plants with similar irradiation.

Also in this case, EW-TEE could enhance privacy and scalability.

## Team
* **Members**: 
  * Alain Brenzikofer, Department Head
  * Marcel Frei, Project Manager SubstraTEE
  * Christian Langenbacher, Developer
  * Sabine Proll, Developer
* **Code Repositories**: https://github.com/scs, https://github.com/encointer
* **Website**: https://www.scs.ch/ueber-scs/departments/decentralized-systems/
* **Team's Experience**:
  * Our department took part in the Quartierstrom project where it evaluated blockchain paltforms, developed a dynamic grid usage tariff as a smart contract and evaluated privacy concepts for P2P energy markets.
  * currently, our team is developing [encointer](https://encointer.org), a universal-basic-income local community cryptocurrency based on self-sovereign identity.
  * We also developed [SubstraTEE](https://www.substratee.com) and [substrate-api-client](https://github.com/scs/substrate-api-client) honoured with grants from the web3 foundation.
  * We developed a [concept and PoC for e-Mobility charging](https://youtu.be/xJUKNlV79pg) paid with tokens with enhanced privacy and incentivized demand response for grid balancing. Based on an ethereum PoA network
  * We also developed decentralized solutiones for two startups in the energy sector.

## Development Roadmap
Total Estimated Duration: 8 weeks

### Milestone 1: Porting to Ethereum
Estimated duration: 5 weeks
* Port SubstraTEE-worker to work with EW Chain (Ethereum PoA chain) (like [SubstraTEE M6](https://www.substratee.com/roadmap.html) yet without reading on-chain data or tx inclusion proofs)
* featuring worker [redundancy](https://www.substratee.com/design.html#redundancy-m3-onwards)
* because of Ethereum smart contract restrictions, the verifiation of worker remote attestation would have to be done off-chain by clients themselves.
* demonstrate private token transfer with EW-TEE

### Milestone 2: Use Case PoC
Estimated Duration: 3 weeks

* Implement a PoC similar to EW Flex on EW-TEE with enhanced privacy

### Milestone 3: Security Hardening
Estimated Duration: 5 weeks
* Implement ethereum light-client inside enclave to read on-chain state trustlessly (see [SubstraTEE M6 & M7](https://www.substratee.com/roadmap.html))

