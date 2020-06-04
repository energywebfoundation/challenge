# Energy Web Innovation Challenge Proposal
* **Project Name**: EW-OCEAN AI Bridge
* **Project Proposer GitHub**: https://github.com/Rjrunner44/challenge.git
* **Energy Web Chain Payment Address**: 0x882001eb216Dc32435aB7202ac09EcdC053f3376

## Project Description
BUILD AN EW-TO-OCEAN BRIDGE ENABLING POWER ANALYTICS AND INTELLIGENCE (A.I. LEARNING) FOR EWC ENABLED IOT DEVICES - ENERGY ANALYTICS & LEARNING

Create an EWC to OCEAN Bridge (EWC-AI) which enabling the creation of OCEAN IOT Energy Data Marketplace(s) fed by billions of EWT enabled devices. The EWC devices send Power Telemetry Data (PDT) about usage and consumption to the marketplace(s). Enable two types of energy IOT data marketplaces:

    > Public: Billions of IOT devices publish their data (anonymously) for the benefit of all
    > Private: Millions of similar IOT devices publish their data (anon or id) for the benefit of the manufacturer and partners

Premises:

1. To improve the efficiency of energy devices and networks, we need to learn from them based on real-world usage data analysis,
2. To learn, we need to see patterns,
3. To get patterns, we must have data,
4. To get data, we need EWC IOT enabled devices to generate and report power telemetry data (PTD),
5. Billions of EWT enabled IOT devices will be able to.

Practical Examples:

intra company/mfg analysis : learn from their own devices and networks


cross company analysis: learb from devices abs networks across companies and manufacturers. eg learn that when device x limits power to Y then another companies device W actually increases to offset it (and more, net energy waste)

another example; of you limit gone thermostats to X during summer people actually then spend MORE energy driving their cars to the beach to cool off cross network/device/mfg analysis and learning 


    - Enables analytics and learning from energy data consumption and usage data.
    - Build a prototype system (Data Model, API, DB, UI) which enables the creation of EWC Energy Data Marketplace(s) in OCEAN for IOT Devices 
    - Enables AI Learning From Power Metrics and Consumption in Feedback Loop to IOT Developers & Manufacturers 
    - Billions of devices are using energy/EWT...how to get their data into OCEAN somehow for analytics...to refine,learn and improve and feedback into the devices... (feedback loop of AI learning/improvement). Maybe it's just analytics at the first phase LOL... but that's the thought
    - Maybe it's just "power analytics" for prototype proof 🙂 I like that phrase!
    - Eventually the AI connection should result in specific recommendations based on analytics about suggestions that could be made to improve the power grid (of the IOT devices)...
    - For now, just getting power mgmt data into ocean somehow (making it available) for "power analytics" to even be possible I think is the goal (as proof of concept). Anyway, what do you guys think?
    - Maybe we define a core set of power analytics metrics that EWT devices should emit (as a standard of some kind) which makes it possible to import/analyze in ocean. I'm just thinking of diff ways of expressing the goal I guess. Anyway, enough from me...


is there an ewc-dos device simulator (react) maybe sep project allows devices to be simulated, power profiles simulated, generates ewc-ai data streams 


this project will only use simulated ewc-dos devices and simulated data 


Define set of (extensible) Power Telementry Data JSON sets

Create intermediary structure (blockchain based) to act as intermediary and aggregator and normalizor of data (Adivate)

Expose Data Sets to OCEAN marketplace(s)

Monetization Areas:
    a) provide IOT power datasets for a fee
    b) provide architecture and analytics as a service to IOT manufacturers of EWT enabled devices
    c) provide EWC-AI as a service to manufacturers of EWT enabled devices and energy network providers

AI Enable the data sets to enable learning and feedback to manufacturers to improve device efficiencies, find patterns, trends, etc. 
    * enable energy iot ewc data marketplaces
    * enable public and private data sets
    * aggregate, normalize and prepare PTD for OCEAN marketplace
    * enable both private marketplaces and public markeplaces 
    * enable buy/sell of Energy IOT data
    * not trading or buy/selling energy contracts
    * IOT PDT Analytics, Analysis & Learning (collection, funnel, API, normalization, aggregation) 

 Deliverables: End to end proof of concept
    - multiple device types registered
    - multiple devices of each type sending data
    - REST API, ties to ENS
    - back -end db
    - Protype UI (react?, RUNE?)
    - one or more OCEAN algo's applied
    - no DB UI (hand coded db for this project)
    - no live EWC-DOS devices (us simulated devices and simulated data)
    - fixed JSON model (just examples really), ultimately would allow any JSON data set to be registered

    Decices: Mfg (Company) -> Network -> Pool -> Device X
    ideally, long term could do cross mfg, cross network, cross pool and cross decice analysis and pattern learning and reporting

Proposed Architecture:
    a) Thin client REST API (JSON): This might be required for performance and thin client integration, optimized to billions of tx/sec on traditional cloud based architecture deployment. This would enable EWC-AI to be integrated easily into many different clients,
    b) Back end DB (NoSQL),
    Prototype UI (react.js/)


## Team
* **Members**: Robert Anderson (Adivate.net, a division of Discovery Productions, Inc.)
* **Code Repositories**: https://github.com/Rjrunner44/
* **Website**: https://adivate.net
* **Team's Experience**:

Most recent: Founded, developed, managed and sold an E-Commerce business. Developed shopping cart platform based on asp.net/SQL. Our customers were dotnet developers (we developed a platform they would customize). Grew to 10,000 customers and $5M sales. Had 70 employees (20 US, 50 Philippines) and 40 developers working for me at the time I sold the business in 2012. I then took a few years off to decompress and did photography (https://rjohnanderson.photography). I'm looking for my next project/startup now and blockchain solutions have my interest. Longer term: I have 30-years of experience in development, databases, E-commerce, embedded systems, real time command & control systems, communications systems. Full stack developer and manager so I can work on both front-end and back-end projects, although I prefer back-end projects which involve data management (REST API’s, etc.), analysis, retrieval, transformation and abstraction. Experienced with SQL and NoSQL and proficient in several languages and dev platforms. Have done: Development, Product Marketing, Sales, Investor Relations, CEO...so my business experience helps me to make common sense decisions when doing design and development. Typically work remote in rapid prototyping and other agile development environments.

## Development Roadmap

    * Total Estimated Duration: 6 months

### Milestone 1: Power Telemetry Data (PTD) Definition and REST API Spec
    * Estimated Duration: 4 weeks
### Milestone 2: Database Design & Spec
    * Estimated Duration: 4 weeks
### Milestone 3: Protoptype Device Integration
    * Estimated Duration: 8 weeks
### Milestone 4: Sample Marketplace UI Client
    * Estimated Duration: 4 weeks
### Milestone 5: Apply A Couple Real AI algos to data for demonstration
    * Estimated Duration: 4 weeks

# Additional Information/Notes:

    * Project genesis came from seeing EWT and Vodaphone partnering, which leads to IOT. I then thought there must be a way for all the IOT "power and device mgmt data" (and analytics) to feed into OCEAN for AI consumption, learning and refinement of EWT tech (feedback loop). This might also enable markeplaces, public and private in OCEAN for Energy Data for IOT.

    * I'm a solid dev, but still new to both crypto and EWT/OCEAN. 25+ Years dev, primarily asp.net, SQL based systems. Education: B.S. Physics

    * I'm good at high level concepts and strategy...but I need to find one or two collaborators to brainstorm together with on how it all might hook together and maybe submit a proposal. I'd like to partner with an EWT dev and an OCEAN dev potentially, although I could probably do it all myself, it will just take a bit more time.

    * I'd be interested in follow-on dev/projects for both EWC and OCEAN



