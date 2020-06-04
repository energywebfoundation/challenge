# Energy Web Innovation Challenge Proposal
* **Project Name**: EW-OCEAN AI Bridge
* **Project Proposer GitHub**: https://github.com/Rjrunner44/challenge.git
* **Energy Web Chain Payment Address**: 0x882001eb216Dc32435aB7202ac09EcdC053f3376

## Project Description (DRAFT NOT FINISHED YET!!)

BUILD AN EW-TO-OCEAN BRIDGE ENABLING POWER ANALYTICS AND INTELLIGENCE (A.I. LEARNING) FOR EW-DOS ENABLED IOT DEVICES - ENERGY ANALYTICS & LEARNING

Create an EW to OCEAN API Bridge (EW-AI) which enables the creation of OCEAN IOT Energy Data Marketplace(s) fed by billions of EW-DOS enabled devices. The EW-DOS devices send Power Telemetry Data (PDT) about usage and consumption to the marketplace(s). 

Premises and Overall Goal:

    1. To improve the efficiency of IOT energy devices and networks, we need to learn from them by collecting and analyzing real-world consumptiom data analysis,
    2. To learn, we need to see patterns,
    3. To get patterns, we need to have data,
    4. To get data, we need EW-DOS IOT devices to be able to report their power telemetry data (PTD),

This project would develop an end-to-end prototype of how this could be accomplished, showing how EW-DOS enabled IOT devices would be able to do this. 

    - Enables analytics and learning from energy data consumption and usage data.
    - Build a prototype system (Data Model, API, DB, UI) which enables the creation of EW-DOS Energy Data Marketplace(s) in OCEAN for EW-DOS IOT Devices 
    - Enables AI Learning From Power Metrics and Consumption in Feedback Loop to IOT Developers & Manufacturers 
    - Eventually the AI connection should result in specific recommendations based on analytics about suggestions that could be made to improve the power grid (of the IOT devices)...
    - For now, just getting energy device mgmt data into ocean (making it available) for "energy & power analytics" to be possible is the goal (as proof of concept).

This could enable two types of energy IOT data marketplaces, both private and public:

    > Private Same-vendor/network/manufacturer Marketplace (SVM): IOT devices publish their data (anon or not) for the benefit of that manufacturer (and their partners). The data from a single vendor's devices would be aggregated, normalized and used for pattern development and learning. In this case, for example, all Vendor X phones would send data into a single pool for analysis. Benefits of learning and pattern recogition would only be available to Vendor X.
    
    > Public Cross-vendor/network/manufacturer Marketplace (CVM): IOT devices publish their data (anonymously) for the benefit of all to analyze and learn from. The Data from multiple vendors, networks and devices could be aggregated, normalized, and cross-analyzied for pattern development and learning. In this case, for example, data from Vendor X cars, Vendor Y smart meters, and Vendor Z phone IOT devices would be availabe for cross analysis. Benefits of learning and pattern recognition would be available to all who contributed the data.

EW-AI would funnel, prepare (normalize), and aggregate PTD for OCEAN marketplace consumptiom (i.e. data funnel) and analytics/learning. Devices would identify via ENS and be anonymized as necessary (different requirements for CVM and SVM):

In CVM, since we would be able to learn from devices and networks across companies, manufacturers and networks, we may discover patterns that were heretofore unknown (and unpredicatble). E.g. we might learn that when Vendor X device X limits power to P, then Vendor Y device Y actually increases it's power consumption by 1.1*P, actually offsetting (and more) energy consumption to produce net energy waste. An example of this might help (wildly fictional): When home thermostat devices in homes are set to allow max temp Y when the ambient temperature is >Z, then we learn that consumers actually drive their cars MORE to the beach to cool off than we saved by limiting the thermostats (net energy waste, not gain). Again, this is a wildly fictional example, but it just may start ideas about what might be possible. This shows how IOT energy device data from 3 different vendors is cross analyzed (home thermostat IOT, car (EV) IOT, user Phone IOT (location data)).

By exposing energy and power consumption data sets to the OCEAN marketplaces, we might enable the following monetization Areas:

    a) provide IOT power datasets for a fee (i.e. enable buy/sell of energy data)

    b) provide EW-DOS-AI as a service to manufacturers of EW-DOS enabled devices and energy network providers

    c) provide architecture and analytics as a service (Actual AI algos) to IOT manufacturers of EW-DOS enabled devices

Proposed Architecture & Deliverables:

    1. Thin client REST API (either Typescript/Node.js or Golang, JSON): Ultimately, we'd have to optimize this for millions of TPS, probably using traditional cloud based architecture deployment. This would enable EW-AI to be integrated easily into many different EW-DOS clients,

    2. Back Eend Data Model/DB (Either SQL or NoSQL, Both?, Mongo?, other?): This protoype would hand-code scheme, no UI for the DB is called for (would be possible later of course)

    3. Prototype UI (Electron React.js app): showing how it could all be used together, and tied to OCEAN

    ((DIAGRAMS HERE TBD))

Prototype would demonstrate how data could be handled from multiple devices (e.g. Vendor, Network, Pool, Device struture and hierarchy, not fully fleshed out yet):

    - multiple vendors (manufacturers)
    - multiple networks (pools?)
    - multiple device types
    - one or more OCEAN algo's applied (very simple ones probably!)
    
## Team
* **Members**: Robert Anderson (Adivate.net, a division of Discovery Productions, Inc.)
* **Code Repositories**: https://github.com/Rjrunner44/
* **Website**: https://adivate.net
* **Team's Experience**:

25+ Years dev & entrepeneur, primarily asp.net, SQL based systems. Education: B.S. Physics

Most recent: Founded, developed, managed and sold an E-Commerce business. Developed shopping cart platform based on asp.net/SQL. Our customers were dotnet developers and corporations (we developed a platform they would customize). Grew to 10,000 customers and $5M sales, mostly small-mid size businesses, but we also had bigger clients (Crocs, McDonalds, PGA Tour, Ed Hardy, ZGallerie, etc...). Had 70 employees (20 US, 50 Philippines) and 40 developers working for me at the time I sold the business in 2012. I then took a few years off to decompress and did photography (https://rjohnanderson.photography). I'm looking for my next project/startup now and blockchain solutions have my interest. Longer term: I have 30-years of experience in development, databases, E-commerce, embedded systems, real time command & control systems, communications systems. Full stack developer and manager so I can work on both front-end and back-end projects, although I prefer back-end projects which involve data management (REST API’s, etc.), analysis, retrieval, transformation and abstraction. Experienced with SQL and NoSQL and proficient in several languages and dev platforms. Have done: Development, Product Marketing, Sales, Investor Relations, CEO...so my business experience helps me to make common sense decisions when doing design and development. Typically work remote in rapid prototyping and other agile development environments.

## Development Roadmap

    - Total Estimated Duration: 6 months

### Milestone 1: Power Telemetry Data (PTD) Definition and REST API Spec
    - Estimated Duration: 4 weeks

### Milestone 2: Database Design & Spec
    - Estimated Duration: 4 weeks

### Milestone 3: Protoptype Device Integration
    - Estimated Duration: 8 weeks

### Milestone 4: Sample Marketplace UI Client
    - Estimated Duration: 4 weeks

### Milestone 5: Apply A Couple Real AI algos to data for demonstration
    - Estimated Duration: 4 weeks

# Additional Information/Notes:

    - Project idea genesis came from seeing EW and Vodaphone partnership, which leads to IOT. I then thought there must be a way for all the EW-DOS enabled IOT device "power and energy data" to feed into OCEAN for AI consumption, learning and refinement of EW tech (feedback loop). This might also enable markeplaces, public and private in OCEAN for Energy Data for IOT.

    - This project is not trading or buying/selling energy contracts (that's a whole different market than the focus of this project)

    - I will almost certainly need some advice/input from 1) IOT person (Vodaphone maybe?), 2) EW Dev, 3) OCEAN dev. I'm a solid dev, but still fairly new to crypto and EW/OCEAN. I understand all the basics and concepts.

    - This project will only use simulated EW-DOS devices and simulated data (i.e. we will make simulated JSON payloads for PTD). This leads me to wonder if there is an EW-DOS device simulator (maybe that is a separate dev project to do) which allows devices to be simulated, power profiles simulated, generates EW-AI data streams, etc. Ultimately, we'd like to register JSON schema by device, so it could be extensible and cross-analyziable (even across different networks, devices and manufacturers)

    - I'd be interested in doing follow-on projects for both EW and OCEAN








