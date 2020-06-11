# Energy Web Innovation Challenge Proposal
* **Project Name**: MicroGrid
* **Project Proposer GitHub**: https://github.com/saahilshangle/microgrid-blockchain
* **Energy Web Chain Payment Address**: 0x6b73E4Bae3839f929138604967BF46d3295c8189

## Project Description
### Executive Summary
MicroGrid is a U.S. P2P energy sharing platform that creates a competitive energy market with dynamic pricing built on the EW-DOS infrastructure. In this system, government regulated energy monopolies and individual energy producers sell on the same market through the existing power grid. We deliver competitive prices to retail consumers by leveraging the existing non-competitive surplus renewable energy market. MicroGrid will integrate with EW Origin such that producers may sell energy attribute certificates (EAC) and/or EWT tokens. Self-soverign decentralized identifiers (SSI) will enable simple supplier switching as users build their identities with transaction histories and other personal tokens. MicroGrid can reduce the need for aggregated DER amounts in a marketplace (as seen with Community Choice Aggregation & California's DRAM program) by leveraging smart contract-based Distributed Energy Resource Management Systems (DERMS).

### Background
Traditionally, when households consume electricity their cost is based on the locational marginal pricing calculated by centralized providers like PG&E. As a result of the large fixed costs to build the infrastructure and complex distribution systems, grid operators often form natural monopolies with government subsidies. While they are price regulated, their electricity buy and sell prices still have a huge spread (around 3¢/kWh vs. 20¢/kWh). Furthermore, net metering programs fail to offer the full extent of financial incentives possible to communities. While prosumers (defined as energy consumers capable of producing energy with renewable DERs) receive retail rate kWh credit through net metering 2.0, neighbors who do not produce energy are paying higher retail rates for that same amount because they are not eligible for the same plans (e.g. EV2-A, EV2-B). Therefore, MicroGrid works such that with PG&E's current rate plans, EV owners would still be incentivized to charge at night (so as to protect against overloading grid infrastructure) and solar panel owners would profit more by selling to non-EV2-A/EV2-B consumers.

### Concept & Commercialization
When a prosumer generates power, excess (defined as amounts not expended by the producer in the moment of generation) will be either a) stored in a personal battery supply for later use/sale, b) sent directly to the grid for a net metering/automatic smart contract transaction, or c) stored in a community battery shared between residents for later use/sale (Community Choice Aggregation inspired). Multiple oracles (meter, energy provider billing, SSI information) will be necessarily be trusted in aggregate to determine excess energy ownership of a prosumer. An off-chain automatic trading algorithm tuned to seller pricing preferences will identify a) local buyers willing to pay more than net metering rates, or b) parties interested in purchasing EACs (EW Origin). Buyers participating in this system will automatically submit bids according to rates being paid at the moment, recycled at a pre-set interval. With the P2P market force, both the supply and the demand side can trade energy at a better price. Once a match is identified, the transaction will pseudonymously be rolled up with others occuring near the same moment (increasing privacy) and excecuted as a smart contract on-chain (EW Chain). Grid operators will receive royalties on all transactions for infrastructure ownership. Sellers without battery storage options will only have the option to take trades available at time of generation. This solution generates the possibility of P2P energy trading, but when the market is illiquid or when the price is not ideal, people can still choose to buy/sell energy with centralized firms as they used to do. A key advantage of using the EW-DOS infrastructure for this design is the reliability that comes with a consortium of reputable energy advocates that can validate transactions instead of a single provier. Participants do not necessarily need to host their own node, however can still engage in a more affordable, democratic market. Commercialization could come from several possible avenues, we propose either an initial onboarding fee for neighbors to participate in P2P trading or adding to the proposed energy provider royalty fee. 

### User Flow
The user flow will begin with the authentication login page. Once a user logs in, they will be taken to a splash page showing several “feeds”. One will be a catalog of energy shares that have been bought, one will be a catalog of energy shares that have been sold, and below both feeds will be a variety of metrics that indicate user “performance” over time. These metrics in specific will be determined after evaluating what information is valuable to users; one example is a line graph showing surplus energy held over time so users can determine whether their buy/sell strategy is wasteful or on-par with their expectations. The visual portrayals of these metrics will provide important information that will help users contextualize the value of energy they are trading through methods like translating energy amounts into recognizable figures (e.g. “You sold enough energy last month to power an 8-floor apartment building!”). A settings page will allow users to edit profile information and adjust two key metrics: their maximum buying price and minimum selling price. We plan to perform exhaustive user testing in both Figma and our fully developed application for usability and feedback in low-fidelity and high-fidelity iterations.

<sub>Click below for a short demo</sub><br>
[<img src="https://saahilshangle.github.io/images/microgrid_home.jpg" width="50%" length="50%"/>](https://www.youtube.com/watch?v=abb4BOO2_os)

### Architecture
This platform will assign individual energy producers and consumers to microgrid regions where sellers and buyers are matched off-chain. We utilize blockchain to execute energy transactions and maintain a complete record of them. EW-Chain smart contracts will handle the exchange of energy rights with EWT/EAC ERC-721 tokens. However, the user experience will be largely abstracted away from the blockchain, and transactions are automated to minimize costs through a continuous process of dynamic energy pricing. A decentralized ledger provides transparent pseudonymous neighbor to neighbor energy management that significantly reduces reliance and expected costs associated with a single energy provider. A web interface will abstract low level blockchain computation, and assist the user in understanding their energy transactions on the microgrid. //@Omkar make more technical, add MERN stack, check differences in architecture when building dApp on EW Client. 

<sub>Click below for a full deck</sub><br>
[<img src="https://saahilshangle.github.io/images/dapp_flow.jpg" width="50%" length="50%"/>](https://docs.google.com/presentation/d/1NNWVx2BMPqyycyE4lmdhekEvGsu1hgPRqYgJBBLIQYQ/edit?usp=sharing)

The implementation of the full-stack dApp demo shown above was built using the MongoDB, Express.js, React.js, Node.js, and Solidity/Ethereum frameworks. Our front-end application was built entire in React

## Team
* **Members**: 
  * Omkar Waingankar ([GitHub](https://github.com/Omkar-Waingankar) | [LinkedIn](https://www.linkedin.com/in/omkar-waingankar))
  * Ratan Kaliani ([GitHub](https://github.com/ratankaliani) | [LinkedIn](https://www.linkedin.com/in/ratankaliani))
  * Ruhi Pudipeddi ([GitHub](https://github.com/ruhi1999) | [LinkedIn](https://www.linkedin.com/in/ruhip/))
  * Saahil Shangle ([GitHub](https://github.com/saahilshangle) | [LinkedIn](https://www.linkedin.com/in/saahilshangle))
  * Kelvin Xu ([GitHub](https://github.com/kelvinxu97) | [LinkedIn](https://www.linkedin.com/in/kelvinxu97))
* **Website**: https://blockchain.berkeley.edu/
* **Team's Experience**:
We are a group of 5 UC Berkeley students part of Blockchain at Berkeley. 
  * **Omkar** is a rising senior studying EECS, former Amazon intern, former undergraduate data science researcher, and co-founder of Flipout, an angel-backed sports betting startup. He is currently an 8VC Fellow and software engineering intern at Nylas, a series B startup building unified communications APIs. 
    * Skills: Full-stack mobile/web development, smart contract development, data engineering, visualization
    * Languages: Python, Golang, Java, Javascript, Solidity, SQL
    * Tools/Frameworks: React, MongoDB, Express, Spring, Firebase, Docker, AWS, Kubernetes, Spark, Tableau, Truffle
  * **Ratan** is a rising sophomore studying EECS, and a former Cisco software intern fascinated by the Internet of Things, Blockchain & Big Data. Currently, Ratan is a Software Engineer Intern at Virgil Quantitative Research (VQR), a quantitative cryptocurrency trading firm based out of NYC, researching the emerging Decentralized Finance (DeFi) market.
    * Skills: 
  * **Ruhi** is a rising senior, studying Computer Science & City Planning. She’s currently interning at Lyft in their autonomous vehicle/self-driving division and is interested in the intersections of software and urban design.
    * Skills: 
  * **Saahil** is a rising junior studying Data Science & Business Administration with internship experience as a PayPal Strategy Analyst and Cisco Product Manager. He is Vice President of a student run pro bono consulting organization and enjoys working on projects that bridge social impact and technology. 
    * Skills: U.S. energy regulation/initiative domain knowledge, smart contract design, competitive market analysis, commericialization strategy, and web development
  * **Kelvin** is a rising senior studying Economics, Logic, and Data Science. He is very passionate about trading and studying secondary markets. In 2018, he took a gap year from UC Berkeley and became a full time trader at Amber AI, a leading cryptocurrency hedge fund and liquidity provider. He joined Blockchain at Berkeley earlier that year as a Public Relations Officer, contributed to the student club’s marketing and branding efforts, and is now with the consulting division. Kelvin is currently interning at the Sales and Trading department at Morgan Stanley.
    * Skills: U.S. energy market landscape knowledge, smart contract design, competitive market analysis, market making strategies, and financial modeling

## Development Roadmap
* Total Estimated Duration: 14 weeks
  * Limited PoC already complete

### Milestone 1: Rinkeby -> Volta Testnet
* Estimated Duration: 4 weeks

### Milestone 2: EW Origin & SSI functionality
* Estimated Duration: 4 weeks

### Milestone 3: Automated trading
* Estimated Duration: 4 weeks

### Milestone 4: User Interface
* Estimated Duration: 2 weeks

# Additional Information
We already developed a [PoC dApp](https://github.com/saahilshangle/microgrid-blockchain) for P2P energy sharing on an ethereum test net over the course of the past 4 months. In mid-May we had the opportunity to [present](https://docs.google.com/presentation/d/1NNWVx2BMPqyycyE4lmdhekEvGsu1hgPRqYgJBBLIQYQ/edit?usp=sharing) our work to Sam Hartnett, EWF Research & Market Development Manager, who encouraged us to apply. Our team is enthusiastic about the sector and this project, and believe that the EW-DOS infrastructure would the ideal backbone for our platform. While EWF has made great progress globally already, we are particularly interested in penetrating the U.S. energy market and navigating the regulations and existing monopoly set up. 
