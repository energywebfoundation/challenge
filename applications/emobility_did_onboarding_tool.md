# Energy Web Innovation Challenge Proposal
* **Project Name**: E-Mobility DID onboarding tool 
* **Project Proposer GitHub**: https://github.com/adamstaveley
* **Energy Web Chain Payment Address**: `0x579de91c99223a2C74eB96908CBeFB216c39395e`

## Project Description

### Introduction

Sales numbers of Electric Vehicles over the last months and years clearly show: E-Mobility is on the rise and battery-electric vehicles will replace internal combustion engine cars over the next 10 years as the favorite means of individual transport. The more electric vehicles are sold, the more charging infrastructure is being installed: at home, along public roads and at any destination that drivers want to reach with their cars. All these new assets will have an enormous impact on the energy and mobility system of the future and this project is about supporting companies in this sector with the right digital tools.

In contrast to fueling a traditional ICE car, charging an electric car is a highly digital process: e.g. finding the preferred charging station, controlling the charging session or limiting the maximum capacity that one electric vehicle can consume at a certain point in time. The success of E-Mobility depends on the connectivity of assets like Charge Points, Electric Vehicles and related services like a user interface, payment solutions, green energy certification to name only some of them. A lot of great work in that regard was already done by the Electric Vehicle Charging community, but much more can be achieved if we introduce the benefits of blockchain technology (e.g. digital identities) to Electric Vehicle charging.

With building the Open Charging Network on the Energy Web Chain the two team members of this project proposal already have reached an important milestone to make this a reality. It provides open source, decentralized messaging based on a de-facto standard e-mobility protocol (OCPI - Open Charge Point Interface), empowered by decentralized identities of providers (e.g. Charge Point Operators (CPO) and eMobility Service Providers (eMSP)) and their assets (Charge Points and Electric Vehicles) on the Energy Web Chain. It reduces costs for communication around controlling charging sessions (start, stop, monitoring, etc.) and unlocks future use-cases that are based on blockchain technology (e.g. green energy certification with EW Origin or Smart Charging based on EW Flex). More can be found on docs.openchargingnetwork.org.

### Challenge

In order to get Charge Point Operators and eMobility Service Providers and their assets successfully onboarded to the Open Charging Network, they must register themselves on the OCN Registry (a smart contract on the Energy Web Chain), implement an OCPI API and enable message signing with their decentralized identity (ethereum based key-pair linked the OCN registry on the Energy Web Chain).

From our experience over the last three years helping the front-runners in eMobility to get their digital connectivity done right, we learned that many of the Charge Point Operators and eMobility Service Providers are overloaded with work and there are many challenges kept unsolved. One of the biggest challenges is the correct implementation of the communication standard OCPI and therefore being able to connect to the Open Charging Network. It is a de-facto standard adopted by the majority of the e-mobility industry but because of its early stage of development and community-approach it leaves room for interpretation. This causes CPOs, eMSPs and other service providers to interpret and implement it very differently, which creates a lot of hassle in establishing connections to each other and to the Open Charging Network and its value-added services. 

To enable e-mobility use-cases based on decentralized identities on the Open Charging Network and the Energy Web Chain, we therefore see this “API implementation problem” as the most important blocker which needs to be removed. 

### Solution

In this project we will build an “E-Mobility DID onboarding tool” that helps CPOs and eMSPs to get their OCPI and OCN API implementation done right. The tool gives guidelines on how to implement the API correctly and analyses existing OCPI and OCN API implementations, for example assuring correctness of point of interest data as well as the validity of message signatures using Energy Web Chain wallets. Based on this analysis it provides automated feedback to developers and IT Ops where discrepancies are and what needs to be changed to ensure connectivity on the Open Charging Network. As soon as this is achieved the players and their assets are available via their DID on the Energy Web Chain and are usable to other players on the network.

By using this tool, onboarding of new operators and their assets can be accelerated, therefore helping to unlock those assets for further blockchain use-cases like green energy certification (EW Origin) and smart charging for grid stability (EW Flex). These in particular require robust API connections to function properly, our tool therefore provides the necessary foundation work to bring the operators of electric vehicles and charging points to the Energy Web Chain.

### Project & Outlook

With this innovation project we will deliver a first version of such a testing tool to showcase the value proposition to first customers and to confirm technical feasibility. We’re in the process of onboarding a first customer to run a pilot project in August. 

After the value proposition and the technical feasibility is confirmed, we will look into how to implement a commercial model which serves the EV charging community best. To ensure the high quality of assets on the Open Charging Network and the Energy Web Chain DID we are convinced that community-driven quality assurance is needed, instead of having one centralized gateway. To enable this, we will provide the E-Mobility DID Onboarding Tool to operators of the Open Charging Network, which can be compared with blockchain node operators. These OCN Node Operators provide the service to onboard assets of CPOs and eMSPs to the Open Charging Network and the Energy Web DID. By using the E-Mobility DID Onboarding Tool they would additionally ensure the quality of those assets (“decentralized quality assurance”) which improves the overall network quality and opens up additional revenue streams for OCN Node Operators.


## Team

* **Members**: Adam Staveley, Christopher Burgahn
* **Code Repositories**: https://github.com/adamstaveley, https://bitbucket.org/shareandcharge
* **Team's Experience**: 
    * Adam Staveley: https://www.linkedin.com/in/adam-staveley-6a249692/
        * 3 years experience in developing software solutions in the e-mobility space for leading companies like innogy eMobility Solutions, Volkswagen, EVBox, etc.
        * One of the important experts europe-wide for the OCPI protocol and its implementation
        * Lead Developer of the open source Open Charging Network
        * Skill set: OCPI, Ethereum, Solidity, TypeScript/JavaScript/Node.JS, Kotlin
        * Responsible for software development in the team
    * Christopher Burgahn: https://www.linkedin.com/in/christopherburgahn/
        * 10 years experience in founding companies in various sectors
        * Specialized in identifying customer needs and designing and delivering (digital) products 
        * Product Owner of the Open Charging Network
        * Large europe-wide network in e-mobility sector
        * Responsible for product ownership and business development

## Development Roadmap
* Total Estimated Duration: 8 weeks

### Technical Architecture

* Estimated Duration: 1 week
* Aim: Document outlining the technical architecture of the testing tool that follows the already-identified requirements

### Pilot Version 
* Estimated Duration: 3 weeks
* Aim: Version v0.1 testing tool for one OCPI module (locations module) ready, incl. type checkers, format checkers, mock requests, detailed error logging and a self-service frontend

### Testing
* Estimated Duration: 3 weeks
* Aim: Application of testing tool with 2 partners to ensure value proposition and technical feasibility

### Evaluation and Future Roadmap
* Estimated Duration: 1 week
* Aim: Evaluation of testing phase and decisions on next steps to ensure commercialization
