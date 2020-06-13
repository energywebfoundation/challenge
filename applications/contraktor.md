# Energy Web Innovation Challenge

* **Project Name**: Contraktor
* **Project Proposer GitHub**: https://github.com/wslyvh/contraktor
* **Energy Web Chain Payment Address**: 0x5ac9a43C424bf764d06242Acac446344738e2050

**Contraktor** is a smart contract explorer - browse and visualize smart contracts, to understand the risks and value before transacting with them.

# Why

Smart contracts are complex instruments that offer the possibility to have self-enforcing contracts including transparent, tamper-proof and immutable information. They can not only facilitate and verify transactions in financial services, but also revolutionize the energy sector. Potential use-cases are:

- to authenticate and verify the origin of critical equipment to ensure safe operation and stability
- to issue and track renewable energy certificates, certificates of origin or international I-REC's
- or to facilitate the operation of decentralized peer-to-peer energy distribution networks. 

Smart contracts that are facilitating such cases possess the authority to allocate high-value resources between complex systems. Often even working autonomously. This makes smart contracts an essential, and critical component in these systems and increases demand to comply with transparency and trust in the ledger and its information.

# What

Smart contracts need to be open, transparent and for everyone to verify. Users should be able to understand the risks and value of smart contracts before they transact with them and without having to be, or rely on software developers. **Contraktor** allows anyone to visualize, verify and interact with the smart contract's resources and state without having any implementation logic in place. Making it easy to verify, or use for further integration or consumption.

# How

**Contraktor** is a stand-alone application that automatically generates a UI from the smart contract's specification ('ABI'). These specifications are pulled from a block explorer (e.g. Etherscan), but will be managed on a more decentralized source, such as IPFS ultimately. Increased decentralization will increase transparency.

The goal is to create a universally shared and open-source registry of verified smart contracts. Maintained and inspected by a diverse community of experts. Allowing anyone to visualize, interact and monitor these contracts through a common application that is understandable by anyone.

## Development roadmap
An initial prototype of **Contraktor UI** was developed during the [ETH Global hackathon](https://hack.ethglobal.co/showcase/contraktor-recd9C6u3pLojsiTI). The prototype allows to visualize and browse verified smart contracts on different public Ethereum (test-) networks. It contains a registry of common DeFi projects, such as Aave, Compound, Uniswap and ENS to explore related smart contracts and deployments. This makes it easy for DeFi users the assess the risks and value of smart contracts before they transact with them. 

- Repo: https://github.com/wslyvh/contraktor
- Live demo: https://contraktor.netlify.app/ 

This proposal is to extend on that idea and bring it to the next level on the Energy Web Chain.

### Total
Total Estimated Duration: 10-14 weeks 

### Milestone #1: Create EWC-compatible MVP 

~1-2 weeks - development 

- Making it chain-agnostic (EWC compatible), incl. all data sources (EWC explorer, RPC & API endpoints, etc.)
- Overall product improvements & feedback from the hackathon's prototype. 
- Support for 'known' unverified contracts through proxy/factory contracts.

### Milestone #2: Design & UX

~3-4 weeks - product management + UX 

- Work with UX/designer to research and improve overall usability and experience of the application.
- Conducting user interviews to create persona's and user journeys.
- Create mock-ups and prototypes to perform usability testing.
- Apply and translate learnings and designs into the application.

### Milestone #3: Personal dashboards

~2 weeks - development 

- User access management allowing anyone to register for an account.
- Contract Control Center to keep track of favourites contracts and bookmarks. 
- Custom endpoints to retrieve data from external, custom nodes or RPC endpoints.

### Milestone #4: Monitoring

~2 weeks - development 

- Build in logs and monitoring to keep track of a deployed smart contract's transactions, balance, and events.
- Filter by transaction failures, events, or state changes for quick responses.
- Notifications to subscribe to any of those events and changes.

### Milestone #5: Increase decentralization & transparency

~2 weeks - product- & community management + development

- Decentralize the solution - host on IPFS, allowing the community to help and curate the projects and contracts
- Re-compile smart contract code to verify it corresponds with deployed bytecode 

Plus any additional time for porting other components and technologies that help towards more decentralization and transparancy can be discussed. Some examples:
- Ethereum's Sourcify, that indexes contract metadata with IPFS and Swarm hashes, to the Energy Web Chain
- The Graph, decentralized GraphQL endpoints for distributed querying on smart contracts
- 3Box, for decentralized user profiles and account management 

# Who

**Wesley van Heije** – independent engineering & tech lead

Building product & teams with a successful track record and over 12 years of experience on delivering enterprise-grade products & solutions for leading international organizations, such as Microsoft, Shell, Accenture, Roche, ConsenSys, Komgo. 

- LinkedIn: https://www.linkedin.com/in/wesleyvanheije/
- Github: https://github.com/wslyvh/
- Twitter: https://twitter.com/wslyvh

Recent blockchain experiences and achievements
- Blockchain tech lead for Shell 
- Won two grants for our work on DAO's @ ETH Berlin
- Co-founder Blockchain Netherlands foundation - a non-profit foundation who aims to connect the Dutch Blockchain ecosystem
- Tech Lead for Komgo, a blockchain-based trade & commodities platform
- Contributing & building open-source tools for the Ethereum ecosystem
- Founder Ethereum NL community
- Won a grant for our work with zero-knowledge proofs @ Blockchaingers (Odyssey) hackathon
- Blockchain & Smart Contract development for a Dutch startup
- Top-performer on the Ethereum Academy Program. Graduating in Dubai and participating in the Smart Dubai hackathon.
