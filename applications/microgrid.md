# Energy Web Innovation Challenge Proposal
* **Project Name**: MicroGrid
* **Project Proposer GitHub**: https://github.com/saahilshangle
* **Energy Web Chain Payment Address**: [WIP]

## Project Description
MicroGrid is a peer to peer energy management platform that implements dynamic energy pricing. In this system, government regulated energy monopolies and individual energy producers sell on the same market through the existing power grid. We deliver market competitive prices to retail consumers and prosumers by leveraging the existing non-competitive surplus renewable energy market currently controlled by monopolistic energy companies.



This platform will assign individual energy producers and consumers to microgrid regions, or neighborhoods, where sellers and buyers are matched off-chain. We utilize blockchain to execute energy transactions and maintain a complete record of them. Ethereum smart contracts will handle the exchange of energy rights with neighborhood-unique stablecoin. However, the user experience will be largely abstracted away from the blockchain, and transactions are automated to minimize costs through a continuous process of dynamic energy pricing.

A decentralized ledger provides transparent neighbor to neighbor energy management that significantly reduces reliance and costs associated with a single energy provider. Existing energy providers will be given royalties for operating on their infrastructure and still available as a seller option for consumers.







Power generated will be tracked by some integrator as it enters either a battery. If into a battery, some amount will be stored for personal use, but the rest will be available for purchase. Meanwhile, users of electricity will make their intent clear by plugging in electronics into outlets or turning on devices connected to outlets. A node controlling the building circuitry will measure current draw intermittently at some high rate, like 1kHz, and automatically make bids for electricity. The bidding algorithm will have a default setting that stakes the average sale price over some number of previous transactions (let’s say 100) on the chain, but users and building managers can install custom staking systems. The bid will be in the form of a smart contract, which holds money for an electricity request to be fulfilled by some power generating node. This node mentioned previously will run a trading algorithm to decide which requests to fulfill. The first node timestamped to submit the request to the smart contract will be rewarded the amount, and the electricity will be transferred. If a bid is not fulfilled at the cancellation time set by the buyer, the smart contract will terminate and the bidding node will buy from PGE.


A web interface will abstract low level blockchain computation, and assist the user in understanding their energy transactions on the microgrid. As part of the Energy Microgrid Project team, team members will deliver a design and prototype for a final web application.

In addition to a modern web architecture using the MERN stack, our toolchain will include Figma, a leading design software for enterprise. We will use Figma to make high-fidelity iterations that indicate the user flow before implementing the flow in our full-stack application.

The user flow will begin with the authentication login page. Once a user logs in, they will be taken to a splash page showing several “feeds”. One will be a catalog of energy shares that have been bought, one will be a catalog of energy shares that have been sold, and below both feeds will be a variety of metrics that indicate user “performance” over time. These metrics in specific will be determined after evaluating what information is valuable to users; one example is a line graph showing surplus energy held over time so users can determine whether their buy/sell strategy is wasteful or on-par with their expectations. The visual portrayals of these metrics will provide important information that will help users contextualize the value of energy they are trading through methods like translating energy amounts into recognizable figures (e.g. “You sold enough energy last month to power an 8-floor apartment building!”) A settings page will allow users to edit profile information and adjust two key metrics: their maximum buying price and minimum selling price. 

We plan to perform exhaustive user testing in both Figma and our fully developed application for usability and feedback in low-fidelity and high-fidelity iterations.


Traditionally, households consume electricity, and their cost is based on the locational marginal pricing determined by centralized firms such as PG&E. These energy companies require large fixed costs to build the infrastructures. As a result, they often form natural monopolies with government subsidies. There are regulations regarding how these monopolies price energy, but their electricity buy and sell prices still have a huge spread (around 3¢/kWh vs 20¢/kWh). This effectively makes them a large middleman of the energy market, profiting from this spread. Using a blockchain provides a novel mechanism for individuals to have the additional option of trading energy in a peer-to-peer fashion. The prosumers can now post offers to sell their surplus energy while the consumers buy from them. With the P2P market force, both the supply and the demand side can trade energy at a better price. Our algorism will automatically match the buyers and suppliers, allowing them to trade at ease. This solution generates the possibility of P2P energy trading, but when the market is illiquid or when the price is not ideal, people can still choose to buy/sell energy with centralized firms as they used to do.


## Team
* **Members**: Omkar Waingankar, Ratan Kaliani, Ruhi Pudipeddi, Kelvin Xu
* **Code Repositories**: https://github.com/saahilshangle/microgrid-blockchain
* **Website**: https://blockchain.berkeley.edu/
* **Team's Experience**:
We are a group of 5 UC Berkeley students from Blockchain @ Berkeley. My name is Saahil, I am a third year studying Data Science and Business Administration. I enjoy learning

## Development Roadmap
* Total Estimated Duration: 8 weeks

### Milestone 1
* Estimated Duration: 4 weeks

### Milestone 2
* Estimated Duration: 4 weeks

# Additional Information
Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vivamus pharetra a sapien eget porttitor. Suspendisse potenti. Nam malesuada est urna, et ullamcorper dolor accumsan sit amet. Sed dapibus risus vel turpis aliquet gravida.
