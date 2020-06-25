# Energy Web Innovation Challenge Proposal
* **Project Name**: EW-AI (EW to OCEAN AI Bridge)
* **Project Proposer GitHub**: https://github.com/Rjrunner44/challenge.git
* **Energy Web Chain Payment Address**: 0x882001eb216Dc32435aB7202ac09EcdC053f3376

## Project Description

BUILD AN EW-TO-OCEAN BRIDGE ENABLING A POWER ANALYTICS AND INTELLIGENCE MARKETPLACE (A.I. LEARNING) FOR IOT EW-DOS ENABLED DEVICES (ENERGY ANALYTICS & LEARNING)

![EW-AI Header](https://adivate.net/doc/ewai/header2.jpg)

1. OVERVIEW

Imagine being able to do analysis and learning across clean energy and renewables devices, networks and industries, for example, by analyzing and learning from energy consumption and usage patterns across wind, solar, EV, hydro and geothermal networks by being able to apply AI learning to consumption patterns to improve overall grid IOT device efficiencies.  The application of AI techniques can potentially expose previously unseen patterns resulting in efficiency recommendations and improvements across clean energy and renewables networks.

This challenge project would create a conceptual prototype system for an EW to OCEAN API Bridge and subsystem (EW-AI) which enables the creation of OCEAN IOT Energy Data Marketplace(s) fed by millions/billions of EW-DOS enabled devices. The EW-DOS devices send Power Telemetry Data (PDT) about usage and consumption to the marketplace(s). OCEAN's data marketplaces would be an ideal way to apply AI learning to improve the energy efficiency of IOT devices and networks by studying patterns visible from their real-world consumption data. Applying OCEAN AI analysis would also allow algos to be developed and applied to energy data which may look for and spot unusual and heretofore unknown consumption patterns, and even potentially start automatically addressing their causes through learning techniques.

Project Premises and Overall Goal:

1) To improve the efficiency of IOT energy devices and networks, we need to learn from them by collecting and analyzing real-world consumption data analysis and apply AI techniques and algos,
2) To learn, we need to see patterns,
3) To get patterns, we need to have data,
4) To get data, we need EW-DOS IOT devices to send their Power Telemetry Data (PTD). Note that PTD (Power Telemetry Data) is a very open-ended concept. It could encompass many different JSON data payloads/datasets with information about the device's power metrics, usage and consumption data, event related data, etc. Important: This system would not be limited to only new device data sets, as it also would allow legacy PTD data importing (see EW-API further below).

![EW-AI Architecture Diagram](https://adivate.net/doc/ewai/EWAI-ArchDiagram-V5.jpeg)

This project would develop an end-to-end prototype system (Data Model, API, DB, UI) showing how EW-DOS enabled IOT devices could be aggregated to create energy OCEAN marketplace(s). It would demonstrate:

- Enabling analytics and learning from energy data consumption and usage data.
- Enabling AI Learning from Power Metrics and Consumption in Feedback Loop to IOT Developers & Manufacturers.
- Eventually the AI connection should result in specific recommendations based on analytics about suggestions that could be made to improve the power grid (of the IOT devices).
- For this conceptual proof of concept project, simply getting energy device data platformed and setup and staged for OCEAN analysis (making it available) for "energy & power analytics" (and learning) to be possible is the primary goal.
- EW-AI could be positioned into the new EW-DOS toolkit layer 

The system envisioned could enable two types of energy IOT data marketplaces, both private and public (a vendor could be a device manufacturer, a network, etc.):

> Private Single Vendor Marketplace (SVM): IOT devices publish their data (anon or not) for the benefit of that single manufacturer (e.g. Vendor X and their partners). The data from a single vendor's devices would be aggregated, normalized and used for pattern development and learning. In this type of marketplace, the data and benefits of learning and pattern recognition would only be available to Vendor X.
    
> Public Cross-Vendor Marketplace (CVM): IOT devices publish their data (anonymously) for the benefit of all to analyze and learn from. The Data from multiple vendors, networks and devices could be aggregated, normalized, and cross-analyzed for pattern development and learning. In this case, for example, data from Vendor X cars, Vendor Y smart meters, and Vendor Z solar panel IOT devices could be made available for CROSS NETWORK pattern analysis. To my knowledge, this type of cross network analysis and learning has never been possible before. As an example, maybe Vendor A wind turbine data could be cross analyzed with Vendor B solar data. The benefits of learning and pattern recognition would be available to all vendors who contributed the data. This in effect is a multi-tenant OCEAN energy data marketplace.

EW-AI would funnel, prepare (normalize), aggregate and stage PTD for OCEAN marketplace consumption and analytics/learning. Devices would identify (optionally) via ENS and be anonymized as necessary (there would likely be different requirements for SVM and CVM). This prototype will focus only on building a SVM implementation but the real benefit of an OCEAN AI powered energy data marketplace would be realized when able to look at cross vendor patterns (and cross device, cross network, etc.) using anonymous data sets so vendors could learn from others in total system aggregate consumption analysis.

In CVM (the long term ultimate holy grail goal), we may discover heretofore unknown (and unpredictable) patterns in energy consumption, usage, waste and optimization by analyzing and learning from data across multiple energy devices and networks (e.g. wind, EV, solar, hydro, geothermal etc.). For example, we might learn that when Vendor A device X limits power to P, then Vendor B device Y actually increases its power consumption by 1.1*P, actually offsetting (and more) total grid energy savings to produce net energy waste. In a wildly fictional example, we might learn that when consumers are encouraged to set their home thermostat smart meters to allow a max temp Y when the ambient temperature is >Z, those same consumers actually drive their EV cars to the beach to cool off in such a way that offsets any power savings achieved by limiting the thermostats (i.e., net energy waste, not gain). This type of analysis is only possible when you can access and analyze IOT energy device data across multiple vendors and networks (in this case home thermostat IOT, EV Car IOT, Phone IOT with location data). Of course, cross vendor cooperation and agreement would be required in order to achieve this goal, perhaps even spanning political and national boundaries.

IOT-X Data

- It should be possible in later iterations of this system to add/merge data external to the actual IOT devices themselves (IOT-X) into the system for cross-correlation and analysis. For example, add tire make and model into EV IOT PTD data in a correlated fashion. Such IOT-X data might enable learning about patterns and trends which go beyond pure PTD input data, to achieve broader learning and carbon cleansing. (e.g. the effect of specific tire brands, treads, etc. on energy consumption). This would open up the data marketplace to be of interest to many more vendors than just IOT manufacturers. In effect, IOT-X could be thought of as adding "Manufacturer Specifications" data to the PTD data to allow a broader analysis and understanding of the total system.

DEVICE HIERARCHIES

I envision a hierarchy of devices. The devices would potentially identify using DID's (https://www.w3.org/TR/did-core/), but that would be optional:

![EW-AI Device Hierarchy](https://adivate.net/doc/ewai/EWAI-DeviceDiagram-V2.jpeg)

A "pool" is a group of the same devices from a single vendor. There may be multiple pools per vendor or network. Pools are arbitrarily assigned as needed, perhaps to group sets of devices to measure and analyze their performance characteristics when using different device settings (a kind of A/B testing if you will for energy IOT devices). How Pools and Networks correlate I'm not quite sure yet (maybe Pool = Network, but I envision there could be multiple Pools on each network). Again, this project is to create a somewhat flexible system demonstrating proof of concept, not to limit specific Vendor implementations of it subsequently in supporting their own requirements.

The EW-AI API would handle multiple device and notification types (event, report) each with an associated JSON data payload. It is envisioned that a standard set of required header elements be present in the data (so we can organize it), with the "data" element being the actual JSON PTD data payload portion. The JSON data payload structure and content could vary by event and device type (and even by Vendor). We cannot envision all the kinds of data that will go over the interface and it should be flexible enough to handle whatever PTD someone wants to capture. It will be up to the EW-AI Data Manager to allow JSON Schemas to be registered against various vendors, devices, pools, networks and event/report types to allow meaningful interpretation of the data. Example (fictional) PTD snippet is shown below. It is envisioned that additional authentication data (and possibly encryption) will likely need to be added to this for any real-world production system.

    {
        "ewai": {
            "id": "did:ethr:0xD845B41AB4837E06Aa7335E31D98c9097a064891",
            "vendor": "vx.ocean.ewc",
            "pool": "Pool 1",
            "timestamp": "2020-08-23T18:25:43.511Z",
            "type": " event | report",
            "data": {
                "power": 1,
                "duration": 42.4,
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

FLOW

The (rough) general system flow would be as follows in a simplistic form for a SVM marketplace:

- DATA PRODUCERS (Vendors, i.e. device manufacturers):

* Register their company with EW-AI Marketplace (via ENS)
* Register their device types (via ENS)
* Setup pool(s) of devices (optional, pools might allow for different trials on the same device, via ENS again)
* Register their device specs (This really is what the IOT-X data pool is for, so the device/manufacturer specs aren't replicated a million times)
* Integrate EW-AI with EW-DOS, so devices can send their PTD data into EW-AI
* Define who can access their data, costs in OCEAN, privacy level settings, etc.

- DATA CONSUMERS (these could be the same vendors, but also even 3rd parties)

* Register with EW-AI Marketplace
* Search/Find IOT PTD data sets (this can also be done via filtering, grouping, aggregation, normalization, etc. search by manufacturer, device, type, network, data captured, etc.)
* Have EW-AI prepare those sets for OCEAN analysis (EW-AI handles all the details here)
* Apply desired analysis and learning algos
* Get results -> make their devices and networks more efficient.

The flow above is simplified, eventually it would need to handle CVM marketplaces where vendors could permission other (selected) vendors/partners to learn from their data in aggregate ACROSS multiple vendor devices, find patterns across networks, etc...

2. FUTURE MONETIZATION:

By exposing energy and power consumption data sets to the OCEAN marketplaces, we might enable the following monetization Areas:

a) Provide IOT power datasets for a fee (i.e. enable buy/sell of energy data)

b) Provide EW-AI as a service to manufacturers of EW-DOS enabled devices and energy network providers

c) Provide architecture and analytics as a service (actual AI algos) to IOT manufacturers of EW-DOS enabled devices

d) Offer EW-AI integration and consulting services to IOT vendors

3. PROPOSED ARCHITECTURE & DELIVERABLES:

3.1 EW-AI API - Thin client REST API microservice. Suggested: implementation in Golang (could also be done in typescript/node.js), JSON, Swagger Docs, etc. Ultimately, we'd have to optimize this for a high TPS rate using traditional cloud-based architecture deployment, but for this prototype project performance isn't the overriding objective. This API would enable EW-AI to be integrated easily into many different EW-DOS clients. One huge side benefit of this architecture is that it would also allow legacy power data to be imported into the ocean subsystem/marketplace by using this same API (it's not just limited to being called from new IOT EW-DOS devices). This would allow a vast set of existing power consumption data to be imported into the marketplace and achieve the learning benefits OCEAN AI can provide. Deliverable would be a containerized microservice architecture (i.e. docker images).

3.2 EW-AI DB - Back End Data Model/DB. Suggested: Mongo DB back end (but could be SQL if needed). This prototype would hand-code all schema db scripts; no UI for the DB is called for in this challenge project (it would be possible to add that later of course as/if needed).

3.3 EW-AI Data Marketplace - This module contains two components and is much more than just a UI component, as it must store, setup, manage, stage and prepare EW-AI PTD data sets for consumption by OCEAN algos:
    
a) User Interface - These would provide the web based (at this time) UI which setup the EW-AI Data Marketplace. Suggested: a) website (angular/react.js), or b) Electron app (angular/react.js). The UI would be a prototype showing how it could all be used together, managed and tied to OCEAN. The UI for this prototype would likely be based off and/or forked from the OCEAN Commons Marketplace project. The UI module is the most open-ended in terms of definition at this time and is expected to evolve as things progress. Mobile clients could be added at a later time of course as needed, but are beyond the scope of this challenge project.
        
b) Data Manager - This module contains the necessary components, interfaces, and logic to prepare (assemble, aggregate), stage, store and serve PTD data sets for analysis and consumption by the OCEAN protocol system, and is responsible for helping EW-AI users find, group, normalize, aggregate, associate sets of raw PTD data records together (sum, average, filter, group, etc.), tie it in with external IOT-X data (extended IOT device meta data), stage the data sets for OCEAN analysis and allow application of OCEAN AI routines, compute-to-data as necessary, etc. It is expected that fully 50% (or more) of the work for this entire project will be involved in this subsystem.

A rough guess on the amount of work divided across the 3 areas would be: 20% API, 15% DB, 65% Data Marketplace.

Important: The result/deliverables of this challenge project should be considered ALPHA level software. This is a fairly ambitious project and the goal is proof of concept, not production ready software.

![EW-AI Marketplace Diagram](https://adivate.net/doc/ewai/EWAI-Marketplace-SVM-V3.jpeg)

Prototype would demonstrate how data could be handled from multiple devices (e.g. multiple Vendors, Networks, Pools, etc.) as shown in the device hierarchy diagram (the concept of device pools is not fully fleshed out yet though and will evolve based on feedback with IOT vendors). The IOT hierarchy needs to account for:

- multiple vendors (manufacturers)
- multiple networks (pools?)
- multiple device types
- one or more OCEAN algo's applied (very simple ones probably, and compute to data support)
   
## Team
* **Members**: R. John Anderson (Rob), Adivate.net (a division of Discovery Productions, Inc.)
* **Code Repositories**: https://github.com/Rjrunner44/
* **Website**: https://adivate.net
* **Team's Experience**: 25+ Years dev & entrepreneur, primarily asp.net, SQL based systems. Education: B.S. Physics. My specialty is data abstraction, modeling and API development, full stack system integrations and architecture.

Most recent: Founded, developed, managed, operated and sold an E-Commerce business. Developed industry leading asp.net/SQL based shopping cart platform. Our customers were dotnet developers and corporations (we developed a platform they would customize, offered source code, etc.). Grew business to 10,000 customers, mostly SMB market, but we also had larger clients (Crocs, McDonalds, PGA Tour, Ed Hardy, ZGallerie, etc...). Business grew to about 70 employees (20 US, 50 Philippines) and 40 developers working for me at the time I sold the business in 2012. I then took a few years off to decompress (the business was 24/7/365 for 10 years solid). 

Longer term: I have 30-years of experience in development, databases, E-commerce, embedded systems and firmware development, real-time command & control systems and guidance and communications systems. I find projects which involve data management (REST API’s, etc.), analysis, retrieval, transformation and abstraction to be of particular interest. Proficient in several languages and dev platforms. I have also done: Product Marketing, Sales, Bus Dev, Investor Relations for a public NASDAQ company so my business experience helps me make common sense big picture decisions when doing design and development. I typically work remote in rapid prototyping and other agile development environments, and this is how my last business was also setup.

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

### Milestone 5: Consumption Demonstration & Algo Application

- Estimated Duration: 4 weeks. See notes below, as this milestone is going to depend on having data worth analyzing (see notes below)

# Additional Information/Notes:

- Project idea genesis came from seeing EW and Vodafone partnership, which led  me to think more about energy IOT. I then thought there must be a way for all the EW-DOS enabled IOT device "power and energy data" to feed into OCEAN for AI consumption, learning and refinement of EW tech (feedback loop). This might also enable marketplaces, public and private in OCEAN for Energy Data for IOT. Furthermore, after watching Chernobyl recently (really well done!), anything I can do to help clean energy projects and renewables get smarter is something I would find good and worth doing. I tend to only work on projects I am interested in and believe in and have passion about, and hence, this is why I’m interested in connecting EWT and OCEAN. 

- This project is not for trading or buying/selling of energy contracts (that's a completely different market).

- I'm not a EW or OCEAN expert, so I will almost certainly need some advice/input from 1) IOT person (Vodafone maybe?), 2) EW Dev, 3) OCEAN dev. I've therefore set the schedule to be fairly conservative allowing learning time (for me). Hopefully things will go faster, but since this project encompasses two projects (EW and OCEAN Projects), it might get more complicated than can be predicted/envisioned right now at the start.

- I'll be using simulated device PTD data as input for the early milestone development. I'm hoping a partner will have an interest in providing actual PTD data samples that might show real-world application & utility (maybe from EV, wind, solar, hydro, geothermal, etc.). I would ideally like to get some "realistic" PTD to send into the system to model so we could demonstrate analysis and learning which is meaningful (i.e. not completely contrived just to prove concept). But at this time, I plan to use simulated EW-DOS devices and simulated PTD JSON data streams for development of the project architecture. This leads me to wonder if there is an EW-DOS device simulator (maybe that is a separate dev project to do) which allows devices to be mocked-up and simulated, power profiles simulated, which could be used to generate an EW-AI data stream. 

- Ultimately for a full CVM implementation, we would need to register JSON schema by device, so it could be extensible and cross-analyzed (across different networks, devices and manufacturers). I'm not sure how far I can get into that in this prototype project.

- If I fork from other projects to build some of this, are there specific license type(s) that I'm limited to using (or avoiding)?

- Are there any specific open source platforms, projects or repositories I cannot utilize in making this?

- Is EW-AI "part of" EW-DOS or is it separate (it might belong in the EW-DOS Utilities or Toolkit area)?

- This project is a CONCEPTUAL PROTOTYPE demonstrating end-to-end EW-DOS -> OCEAN connectivity and should be considered to deliver ALPHA level software. Not included: 

* How EW-AI is on-boarded into EW-DOS,
* How vendors/manufacturers are on-boarded/registered into EW-AI,
* How devices are fully authenticated/secured (I will integrate with ENS and DID identifiers though obviously) and I realize full authentication will ultimately be required,
* How various JSON Data payloads are handled in a full multi/cross vendor analysis (JSON Schema will be required, etc.). This project is focusing on the Single Vendor Marketplace (SVM) for now, although the architecture should not prevent Cross Vendor Marketplaces (CVM),
* Performance tuning and optimizations,
* IT/Production/Operational deployments, etc. (this is alpha software)

- The whole project could also be done on the dotnet core/MVC tech stack also (andn it could be ported to that platform later also).










