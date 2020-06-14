# Energy Web Innovation Challenge Proposal
* **Project Name**: EW-AI (EW to OCEAN AI Bridge)
* **Project Proposer GitHub**: https://github.com/Rjrunner44/challenge.git
* **Energy Web Chain Payment Address**: 0x882001eb216Dc32435aB7202ac09EcdC053f3376

## Project Description (DRAFT NOT FINISHED YET!!)

BUILD AN EW-TO-OCEAN BRIDGE ENABLING POWER ANALYTICS AND INTELLIGENCE (A.I. LEARNING) FOR EW-DOS ENABLED IOT DEVICES - ENERGY ANALYTICS & LEARNING

1. OVERVIEW

Create an EW to OCEAN API Bridge and subsystem (EW-AI) which enables the creation of OCEAN IOT Energy Data Marketplace(s) fed by millions/billions of EW-DOS enabled devices. The EW-DOS devices send Power Telemetry Data (PDT) about usage and consumption to the marketplace(s). OCEAN's data marketplaces would be an ideal way to apply AI learning to improve energy efficiency of IOT devices by studying patterns visible from their real-world usage data. Applying OCEAN AI analysis would also allow algos to be developed which may look for and spot unusual consumption patterns, and even potentially start automatically addressing their causes through learning techniques.

Project Premises and Overall Goal:

    1) To improve the efficiency of IOT energy devices and networks, we need to learn from them by collecting and analyzing real-world consumptiom data analysis and apply AI techniques and algos,
    2) To learn, we need to see patterns,
    3) To get patterns, we need to have data,
    4) To get data, we need EW-DOS IOT devices to send their Power Telemetry Data (PTD). Note that PTD (Power Telemetry Data) is a very open-ended term. It could encompass many different JSON data payloads/datasets with things from the device's power metrics, usage and consumption data, event related data, etc. This system would not be limited to only new device data but would allow lagacy PTD importing (see API below).

![EW-AI Architecture Diagram](https://adivate.net/doc/ewai/EWAI-ArchDiagram-V5.jpeg)

This project would develop an end-to-end prototype of how this could be accomplished by creating an EW-DOS Energy IOT OCEAN Marketplace (app, api, etc.), showing how EW-DOS enabled IOT devices would be able to do this. 

    - Enables analytics and learning from energy data consumption and usage data.
    - Build a prototype system (Data Model, API, DB, UI) which enables the creation of EW-DOS Energy Data Marketplace(s) in OCEAN for EW-DOS IOT Devices 
    - Enables AI Learning From Power Metrics and Consumption in Feedback Loop to IOT Developers & Manufacturers 
    - Eventually the AI connection should result in specific recommendations based on analytics about suggestions that could be made to improve the power grid (of the IOT devices)...
    - For now, just getting energy device management data into ocean (making it available) for "energy & power analytics" to be possible is the goal (as proof of concept).
    - I think EW-AI would be positioned into the new EW-DOS toolkit layer 

This could enable two types of energy IOT data marketplaces, both private and public:

    > Private Same-vendor/network/manufacturer Marketplace (SVM): IOT devices publish their data (anon or not) for the benefit of that manufacturer (and their partners). The data from a single vendor's devices would be aggregated, normalized and used for pattern development and learning. In this case, for example, all Vendor X phones would send data into a single pool for analysis. Benefits of learning and pattern recogition would only be available to Vendor X.
    
    > Public Cross-vendor/network/manufacturer Marketplace (CVM): IOT devices publish their data (anonymously) for the benefit of all to analyze and learn from. The Data from multiple vendors, networks and devices could be aggregated, normalized, and cross-analyzed for pattern development and learning. In this case, for example, data from Vendor X cars, Vendor Y smart meters, and Vendor Z phone IOT devices would be available for cross analysis. Benefits of learning and pattern recognition would be available to all who contributed the data.

EW-AI would funnel, prepare (normalize), and aggregate PTD for OCEAN marketplace consumption (i.e. data funnel) and analytics/learning. Devices would identify via ENS and be anonymized as necessary (different requirements for CVM and SVM). This prototype will focus on a SVM implementation but the real benefit of OCEAN powered AI learning would be realized when able to look at cross vendor patterns (and cross device, cross network, etc), using anonymous data sets, so vendors could learn from others in system aggregate consumption analysis.

IOT-X Data

    - It should be possible in later iterations of this system to add/merge data external to the actual IOT devices themselves (IOT-X) into the system for correlation and analysis. For example, add tire make and model into EV IOT PTD data in a correlated fashion. Such IOT-X data might enable learning about patterns and trends which go beyond pure PTD input data, to achieve broader learning and carbon cleansing. (e.g. the effect of specific tire brands, treads, etc on energy consumption). This would open up the data marketplace to be of interest to many more vendors than just IOT manufacturers.

I envision a hierarchy of devices (I've set this up using ENS, but that would be optional):

![EW-AI Device Hierarchy](https://adivate.net/doc/ewai/EWAI-DeviceDiagram.jpeg)

A "pool" is a group of the same devices from a single vendor (manufacturer)...e.g. Pool P = Sum( all Vendor X Device Type Y devices). There may be multiple pools per vendor. How Pools and Networks correlate I'm not quite sure yet (maybe Pool = Network, but I envision there could be multiple Pools on each network).

API handles multiple device and notification types (event, report) each with an associated JSON data payload. The JSON data payload structure and content could vary by event and device type (and even by Vendor). We cannot envision all the kinds of data that will go over the interface, and it should be flexible to handle whatever someone whats to capture. It will be up to the EW-AI Data Mgr to allow a JSON Schema to be registered against various vendors, devices, and event/report types to allow meaningful interpretation of the data. Example (fictional) shown below. The "data" element is the actual JSON PTD data payload portion:

    {
        "ewai": {
            "id": "did:ethr:0xD845B41AB4837E06Aa7335E31D98c9097a064891",
            "vendor": "vx.ocean.ewc",
            "timestamp": "2020-08-23T18:25:43.511Z",
            "type": " event | report",
            "data": {
                "power": 1,
                "duration": 47.4,
                "metrics": [
                    {
                        "acceleration": "47",
                        "sensor": "A"
                    },
                    {
                        "deceleration": "51",
                        "sensor": "B"
                    },
                    {
                        "specificity": "14.9",
                        "sensor": "C"
                    }
                ]
            }
        }
    }

In CVM, since we would be able to learn from devices and networks across companies, manufacturers and networks, we may discover patterns that were heretofore unknown (and unpredictable). E.g. we might learn that when Vendor X device X limits power to P, then Vendor Y device Y actually increases it's power consumption by 1.1*P, actually offsetting (and more) energy consumption to produce net energy waste. An example of this might help (wildly fictional): When home thermostat devices in homes are set to allow max temp Y when the ambient temperature is >Z, then we learn that consumers actually drive their cars MORE to the beach to cool off than we saved by limiting the thermostats (net energy waste, not gain). Again, this is a wildly fictional example, but it just may start ideas about what might be possible. This shows how IOT energy device data from 3 different vendors is cross analyzed (home thermostat IOT, car (EV) IOT, user Phone IOT (location data)).

FLOW

The (rough) general system flow would be as follows:

    - DATA PRODUCERS (Vendors, i.e. device manufacturers):
        1. Register their company with EW-AI Marketplace (via ENS)
        2. Register their device types (via ENS)
        3. Setup pool(s) of devices (optional, pools might allow for different trials on the same device) (via ENS again)
        4. Register their device specs (This really is what the IOT-X data pool is for, so the device/manufacturer specs aren't replicated a million times)
        5. Integrate EW-DOS with EW-AI
        6. Have devices send their PTD data into EW-AI API
        7. Define who can access their data, costs in OCEAN, etc

    - DATA CONSUMERS (these could be the same vendors, or even 3rd parties)
        1. Register with EW-AI Marketplace
        2. Search/Find IOT PTD data sets (this can also be done via filtering, grouping, aggregation, normalization, etc. search by manufacturer, device, type, data captured, etc)
        3. Have EW-AI prepare those sets for OCEAN (EW-AI handles all the details here)
        4. Apply learning
        5. Get results -> make their devices more efficient.

The flow above is simplified, eventually it would need to handle CVM marketplaces where vendors could permission other (selected) vendors/partners to learn from their data in aggregate ACROSS multiple vendor devices, find patterns across networks, etc...

2. FUTURE MONETIZATION:

By exposing energy and power consumption data sets to the OCEAN marketplaces, we might enable the following monetization Areas:

    a) provide IOT power datasets for a fee (i.e. enable buy/sell of energy data)

    b) provide EW-AI as a service to manufacturers of EW-DOS enabled devices and energy network providers

    c) provide architecture and analytics as a service (Actual AI algos) to IOT manufacturers of EW-DOS enabled devices

    d) Offer EW-AI integration and analysis/consulting services to IOT vendors

3. PROPOSED ARCHITECTURE & DELIVERABLES:

    1. EW-AI API - Thin client REST API. Suggested: implementation in Golang (but could also be typescript/node.js), JSON, Swagger Doc, etc. Ultimately, we'd have to optimize this for millions of TPS, probably using traditional cloud based architecture deployment. This would enable EW-AI to be integrated easily into many different EW-DOS clients. It should be noted that this same API could also be used to import legacy PTD data into this system, it is not limited to be called from new/active devices. This would allow a vast set of existing power consumption data to be imported and achieve the benefits of being setpu for OCEAN AI analysis.

    2. EW-AI DB - Back End Data Model/DB. Suggested: Mongo (but could be SQL if needed). This protoype would hand-code schema scripts, no UI for the DB is called for in this challenge project. (it would be possible to add that later of course).

    3. EW-AI Data Marketplace - This module contains two components (this module is much more than just a UI component, as it must setup, manage, stage and prepare EW-AI PTD data-sets for consumption by OCEAN algos):
    
        a) User Interface - These would provide the web based (at this time) UI which setup the EW-AI Data Marketplace. Suggested: a) website (angular/react.js), or b) Electron app (angular/react.js). The UI would be a prototype showing how it could all be used together, managed and tied to OCEAN. The UI for this prototype would likely be based off and/or forked from the OCEAN Commons Marketplace project. The UI module is the most open-ended in terms of definition at this time and is expected to evolve as things progress. Mobile clients could be added at a later time of course as needed.
        
        b) Data Mgr - This module contains the necessary components, interfaces, and logic to prepare and stage PTD data sets for analysis and consumption by the OCEAN protocol system, and is responsible for helping EW-AI users find, group, normalize, aggregate, associate sets of raw PTD data records together (sum, average, filter, group, etc), tie it in with external IOT-X data (extended IOT device meta data), stage the data sets for OCEAN analysis and allow application of OCEAN AI routines, compute-to-data as necessary, etc. It is expected that fully 50% (or more) of the work for this entire project will be involved in this subsystem.

    A rough guess on the amount of work divided across the 3 areas would be: 20% (API), 15% (DB), 65% (Data Marketplace).

    Important: The result/deliverables of this challenge project should be considered ALPHA level software. This is a fairly ambitious project and the goal is proof of concept.

![EW-AI Marketplace Diagram](https://adivate.net/doc/ewai/EWAI-Marketplace-SVM-V3.jpeg)

Prototype would demonstrate how data could be handled from multiple devices (e.g. multiple Vendors, Networks, Pools, etc) as shown in the device hierarchy diagram (the concept of device pools is not fully fleshed out yet though and will evolve based on feedback with IOT vendors). The IOT hierarchy needs to account for:

    - multiple vendors (manufacturers)
    - multiple networks (pools?)
    - multiple device types
    - one or more OCEAN algo's applied (very simple ones probably!)
   
## Team
* **Members**: R. John Anderson (Rob), Adivate.net (a division of Discovery Productions, Inc.)
* **Code Repositories**: https://github.com/Rjrunner44/
* **Website**: https://adivate.net
* **Team's Experience**: 25+ Years dev & entrepreneur, primarily asp.net, SQL based systems. Education: B.S. Physics. My speciality is really data abstraction, modeling and API development. I'm not an expert in cryptos, IOT, EW, or AI/OCEAN. I'm more of a jack of all trades full stack system integrator and architecture guy.

Most recent: Founded, developed, managed and sold an E-Commerce business. Developed shopping cart platform based on asp.net/SQL. Our customers were other dotnet developers and corporations (we developed a platform they would customize, offered source code, etc.). Grew business to 10,000 customers and $5M sales, mostly small-mid size businesses, but we also had bigger clients (Crocs, McDonalds, PGA Tour, Ed Hardy, ZGallerie, etc...). Operation had 70 employees (20 US, 50 Philippines) and 40 developers working for me at the time I sold the business in 2012. I then took a few years off to decompress and focus on photography (https://rjohnanderson.photography). 

Longer term: I have 30-years of experience in development, databases, E-commerce, embedded systems, real-time command & control systems, guidance and communications systems. I find projects which involve data management (REST API’s, etc.), analysis, retrieval, transformation and abstraction to be of particular interest. Proficient in several languages and dev platforms. I have also done: Product Marketing, Sales, Bus Dev, Investor Relations for a public NASDAQ company, and CEO management...so my business experience helps me to make common sense decisions when doing design and development. I typically work remote in rapid prototyping and other agile development environments, and this is how my last business was also setup.

## Development Roadmap
    - Total Estimated Duration: 6 months

### Milestone 1: Power Telemetry Data (PTD) Definition and REST API Spec
    - Estimated Duration: 4 weeks

### Milestone 2: Database Design & Spec
    - Estimated Duration: 4 weeks

### Milestone 3: EW-AI Data Mgr
    - Estimated Duration: 8 weeks

### Milestone 4: EW-AI Marketplace UI Client
    - Estimated Duration: 4 weeks

### Milestone 5: Apply AI Algo(s) to Data (for Demonstration)
    - Estimated Duration: 4 weeks. See notes below, as this milestone is going to depend on having data worth analyzing as I'm using simulated device data as input for the prior milestones. I'm hoping a partner will have an interest in providing actual PTD data samples that might show real-world application & utility.

# Additional Information/Notes:

    - Project idea genesis came from seeing EW and Vodafone partnership, which leads to IOT. I then thought there must be a way for all the EW-DOS enabled IOT device "power and energy data" to feed into OCEAN for AI consumption, learning and refinement of EW tech (feedback loop). This might also enable marketplaces, public and private in OCEAN for Energy Data for IOT.

    - This project is not for trading or buying/selling of energy contracts (that's a different market than the focus of this project).

    - I will almost certainly need some advice/input from 1) IOT person (Vodafone maybe?), 2) EW Dev, 3) OCEAN dev.

    - I would ideally like to get some "realistic" PTD to send into the system to model so we could demonstrate analysis and learning which is meaningful (i.e. not completely contrived just to prove concept). But at this time, I plan to use simulated EW-DOS devices and simulated PTD JSON data streams for development of the project architecture. This leads me to wonder if there is an EW-DOS device simulator (maybe that is a separate dev project to do) which allows devices to be mocked-up and simulated, power profiles simulated, which could be used to generate an EW-AI data stream.

    - Since I'm new to BOTH project (EW and OCEAN), I've set the schedule to be fairly conservative allowing learning time (for me). Hopefully things will go faster.

    - Since this project encompasses two projects (EW and OCEAN Projects), it might get more complicated than can be predicted/envisioned right now at the start.

    - Ultimately, we'd like to register JSON schema by device, so it could be extensible and cross-analyzed (even across different networks, devices and manufacturers). I'm not sure how far I can get into that in this prototype project.

    - If I fork from other projects to make some of this, are there specific license type(s) that I'm limited to using (or avoiding)?

    - Are there any specific open source platforms, projects or repositories I cannot utilize in making this?

    - Is EW-AI "part of" EW-DOS or is it separate (it might belong in the EW-DOS Utilities area). If separate, even non EW-DOS IOT devices might send data into it.

    - This project is a CONCEPTUAL PROTOTYPE (demonstrating end-to-end EW-DOS -> OCEAN connectivity). Not included: 

        * How EW-AI is on-boarded into EW-DOS,
        * How vendors/manufacturers are on-boarded/registered into EW-AI,
        * How devices are fully authenticated/secured (I will integrate with ENS and DID identifiers though obviously) and I realize full authentication will ultimately be required,
        * How various JSON Data payloads are handled in a full multi/cross vendor analysis (JSON Schema will be required, etc.). This project is focusing on the Single Vendor Marketplace (SVM) for now, although the architecture should not prevent Cross Vendor Marketplaces (CVM),
        * Performance tuning and optimizations,
        * IT/Production/Operational deployments, etc. (this is alpha software)

    - The whole project could also be done on dotnet core/MVC also (it could be ported to that platform later also).

    - I would be interested in follow-on projects for both EW and OCEAN








