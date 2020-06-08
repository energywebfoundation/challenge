# Energy Web Innovation Challenge Proposal
* **Project Name**: MicroGrid
* **Project Proposer GitHub**: https://github.com/saahilshangle/microgrid-blockchain
* **Energy Web Chain Payment Address**: 0x6b73E4Bae3839f929138604967BF46d3295c8189

## Project Description
### Executive Summary
MicroGrid is a U.S. P2P energy sharing platform that creates a competitive energy market with dynamic pricing built on the EW-DOS infrastructure. In this system, government regulated energy monopolies (often grid operators) and individual energy producers sell on the same market through the existing power grid. We deliver market competitive prices to retail consumers and prosumers by leveraging the existing non-competitive surplus renewable energy market currently controlled by monopolistic energy companies. Self-soverign decentralized identifiers (SSI) will enable simple supplier switching as users build their identities with transaction histories and other personal tokens. MicroGrid can reduce the need for aggregated DER amounts in a marketplace (as seen with Community Choice Aggregation & California's DRAM program) by leveraging smart contract-based Distributed Energy Resource Management Systems (DERMS).

### Background
Traditionally, when households consume electricity their cost is based on the locational marginal pricing calculated by centralized providers like PG&E. As a result of the large fixed costs to build the infrastructure and complex distribution systems, grid operators often form natural monopolies with government subsidies. While they are price regulated, their electricity buy and sell prices still have a huge spread (around 3¢/kWh vs. 20¢/kWh). Furthermore, net metering programs fail to offer the full extent of financial incentives possible to communities. While prosumers (defined as energy consumers capable of producing energy with renewable DERs) receive retail rate kWh credit through net metering 2.0, neighbors who do not produce energy are paying higher retail rates for that same amount because they are not eligible for the same plans (e.g. EV2-A, EV2-B). If providers like PG&E maintained their current rate plan structure, EV owners would still be incentivized to charge at night (so as to protect against overloading grid infrastructure) and solar panel owners would profit more by selling to non-EV2-A/EV2-B consumers in the P2P model MicroGrid proposes.

## Concept & Commercialization

Using a blockchain provides a novel mechanism for individuals to have the additional option of trading energy in a peer-to-peer fashion. The prosumers can now post offers to sell their surplus energy while the consumers buy from them. With the P2P market force, both the supply and the demand side can trade energy at a better price. Our algorithm will automatically match the buyers and suppliers, allowing them to trade at ease. This solution generates the possibility of P2P energy trading, but when the market is illiquid or when the price is not ideal, people can still choose to buy/sell energy with centralized firms as they used to do.

### User Flow



### Technical Architecture

This platform will assign individual energy producers and consumers to microgrid regions, or neighborhoods, where sellers and buyers are matched off-chain. We utilize blockchain to execute energy transactions and maintain a complete record of them. Ethereum smart contracts will handle the exchange of energy rights with neighborhood-unique stablecoin. However, the user experience will be largely abstracted away from the blockchain, and transactions are automated to minimize costs through a continuous process of dynamic energy pricing.

A decentralized ledger provides transparent neighbor to neighbor energy management that significantly reduces reliance and costs associated with a single energy provider. Existing energy providers will be given royalties for operating on their infrastructure and still available as a seller option for consumers.







Power generated will be tracked by some integrator as it enters either a battery. If into a battery, some amount will be stored for personal use, but the rest will be available for purchase. Meanwhile, users of electricity will make their intent clear by plugging in electronics into outlets or turning on devices connected to outlets. A node controlling the building circuitry will measure current draw intermittently at some high rate, like 1kHz, and automatically make bids for electricity. The bidding algorithm will have a default setting that stakes the average sale price over some number of previous transactions (let’s say 100) on the chain, but users and building managers can install custom staking systems. The bid will be in the form of a smart contract, which holds money for an electricity request to be fulfilled by some power generating node. This node mentioned previously will run a trading algorithm to decide which requests to fulfill. The first node timestamped to submit the request to the smart contract will be rewarded the amount, and the electricity will be transferred. If a bid is not fulfilled at the cancellation time set by the buyer, the smart contract will terminate and the bidding node will buy from PGE.


A web interface will abstract low level blockchain computation, and assist the user in understanding their energy transactions on the microgrid. As part of the Energy Microgrid Project team, team members will deliver a design and prototype for a final web application.

In addition to a modern web architecture using the MERN stack, our toolchain will include Figma, a leading design software for enterprise. We will use Figma to make high-fidelity iterations that indicate the user flow before implementing the flow in our full-stack application.

The user flow will begin with the authentication login page. Once a user logs in, they will be taken to a splash page showing several “feeds”. One will be a catalog of energy shares that have been bought, one will be a catalog of energy shares that have been sold, and below both feeds will be a variety of metrics that indicate user “performance” over time. These metrics in specific will be determined after evaluating what information is valuable to users; one example is a line graph showing surplus energy held over time so users can determine whether their buy/sell strategy is wasteful or on-par with their expectations. The visual portrayals of these metrics will provide important information that will help users contextualize the value of energy they are trading through methods like translating energy amounts into recognizable figures (e.g. “You sold enough energy last month to power an 8-floor apartment building!”) A settings page will allow users to edit profile information and adjust two key metrics: their maximum buying price and minimum selling price. 

We plan to perform exhaustive user testing in both Figma and our fully developed application for usability and feedback in low-fidelity and high-fidelity iterations.



## Team
* **Members**: Omkar Waingankar, Ratan Kaliani, Ruhi Pudipeddi, Saahil Shangle, Kelvin Xu
* **Code Repositories**: https://github.com/Omkar-Waingankar, https://github.com/ratankaliani, https://github.com/ruhi1999, https://github.com/saahilshangle
* **Website**: https://blockchain.berkeley.edu/
* **Team's Experience**:
We are a group of 5 UC Berkeley students part of Blockchain at Berkeley. 
  * Omkar is a rising senior studying EECS, former Amazon intern, former undergraduate data science researcher, and co-founder of Flipout, an angel-backed sports betting startup. He is currently an 8VC Fellow and software engineering intern at Nylas, a series B startup building unified communications APIs. 
  * Ratan is a rising sophomore EECS major who loves playing basketball, organizing legal games of poker and curating Spotify playlists. Currently, Ratan is a Software Engineer Intern at Virgil Quantitative Research (VQR). 
  * Ruhi is a rising senior, studying Computer Science & City Planning. She’s currently interning at Lyft in their autonomous vehicle/self-driving division and is interested in the intersections of software and urban design.
  * Saahil is a rising junior studying Data Science & Business Administration with internship experience as a PayPal Strategy Analyst and Cisco Product Manager. He is Vice President for a student run pro bono consulting organization and enjoys working on projects that bridge social impact and technology. Relevant skills include: U.S. energy regulation/initiative domain knowledge, smart contract design, competitive market analysis, commericialization strategy, and web development.
  * Kelvin is a rising senior at Cal studying economics, logic, and data science. He is very passionate about trading and studying secondary markets. Joined Blockchain at Berkeley at 2018 as a Public Relations Officer, he contributed to the student club’s marketing and branding efforts. Later that year, he took a gap year from UC Berkeley and became a full time trader at Amber AI, a leading cryptocurrency hedge fund and liquidity provider. He is currently interning at the Sales and Trading department at Morgan Stanley.

## Development Roadmap
* Total Estimated Duration: 8 weeks

### Milestone 1: 
* Estimated Duration: 4 weeks

### Milestone 2
* Estimated Duration: 4 weeks

# Additional Information
We already developed a dApp with a P2P energy sharing PoC on an ethereum test net over the course of the past 4 months. In mid-May we had the opportunity to present our work to Sam Hartnett, EWF Research & Market Development Manager, who encouraged us to apply. Our team is enthusiastic about the sector and this project, and believe that the EW-DOS infrastructure would the ideal backbone for our platform. While EWF has made great progress globally already, we are particularly interested in penetrating the U.S. energy market and navigating the regulations and existing monopoly set up. 
