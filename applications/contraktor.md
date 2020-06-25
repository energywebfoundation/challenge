# Energy Web Innovation Challenge

* **Project Name**: Contraktor
* **Project Proposer GitHub**: https://github.com/wslyvh/contraktor
* **Energy Web Chain Payment Address**: 0x5ac9a43C424bf764d06242Acac446344738e2050

**Contraktor** is a smart contract explorer - browse and verify smart contracts, to understand the risks and value before interacting with them.

# Why

Smart contracts are complex instruments that offer the possibility to have self-enforcing code that include transparent, tamper-proof and immutable information. They can not only facilitate and verify transactions in financial services, but also revolutionize the energy sector. Potential use-cases are:

- to issue and track renewable energy certificates, certificates of origin or international I-REC's
- to facilitate the operation of decentralized peer-to-peer energy distribution networks
- to create decentralized co-ordination mechanisms of distributed energy resources 
- Or to authenticate and verify the origin of critical equipment to ensure safe operation and stability

Smart contracts that are facilitating such cases possess the authority to allocate high-value resources between complex systems. Often even working autonomously. This makes smart contracts an essential, and critical component in these systems. This increases the demand for transparency, trust in the ledger and its information.

# What

Smart contracts need to be open, transparent and for everyone to verify. Users should be able to understand the risks and value of smart contracts before they transact with them and without having to be, or rely on blockchain engineers. **Contraktor** is providing the tools for users, developers and organizations to visualize, verify and interact with a smart contract's resources and state without having any implementation logic in place. Making it easy for further integration or consumption, without holding any tokens or crypto currency.

# How

**Contraktor UI** is a stand-alone application that automatically generates a UI from the smart contract's specification ('ABI'). These specifications are pulled from a block explorer (e.g. Etherscan) or can be managed on a more decentralized, public source, such as the Registry. Increased decentralization will increase transparency.

The **Registry** is a universally shared and open-source registry of verified smart contracts. Maintained and inspected by a diverse community of experts. Allowing anyone to visualize, interact and monitor these contracts through a common application that is understandable by anyone. This would allow for a new smart contract marketplaces where contracts can be used, shared, deployed or audited. Audits could tap into DID's to add more trust and transparency to the contracts in the registry.

The **API gateway** is the glue in between that connects it all together. This allows to interact with any the chain's resources, its smart contracts and the registry through common (REST/GraphQL) endpoints for further integration with other IT or enterprise systems. Reducing the friction between applications built on the blockchain and developers or end-users. 

## Development roadmap
An initial prototype of **Contraktor UI** was developed during the [ETH Global hackathon](https://hack.ethglobal.co/showcase/contraktor-recd9C6u3pLojsiTI). The prototype allows to visualize and browse verified smart contracts on different public Ethereum (test-) networks. It contains a registry of common DeFi projects, such as Aave, Compound, Uniswap and ENS to explore related smart contracts and deployments. This makes it easy for DeFi users the assess the risks and value of smart contracts before they transact with them. 

- Repo: https://github.com/wslyvh/contraktor
- Live demo: https://contraktor.netlify.app/ 

This proposal is to extend on that idea and bring it to the next level on the Energy Web Chain.

**Prototype**
![Contraktor UI](./contraktor-example.gif)

### Milestone #1: EWC-compatible MVP 
~1-2 weeks - development 

- Making it chain-agnostic (EWC compatible), incl. all data sources (EWC explorer, RPC & API endpoints, etc.)
- Overall product improvements & feedback from the hackathon's prototype
- Support for 'known' unverified contracts through proxy/factory contracts.

### Milestone #2: Product Management
~2 weeks - product management + UX 

- Work with UX/designer to research and improve overall usability, product and experience
- Conducting user interviews to create persona's and user journeys
- Create mock-ups and prototypes to perform usability testing
- Apply and translate learnings and designs into the product.

### Milestone #3: Registry
~2-3 weeks - development + product & community management

- Create a public, decentralized registry for smart contract's sources, that re-compiles its code to verify it corresponds with deployed bytecode 
- Integrate with **Contraktor UI** to visualize, interact, share and re-deploy contracts 
- Allow for extensions in terms of comments, automated smart contract anaylysis (e.g. Slither or MythX), audits and attestations (with DID's) from the community and experts. 

*Need community feedback to prioritse integrations. Could be opened up for other developers to help build on top of this. 

### Milestone #4: Integrations
~2 weeks - development 

- CLI plugins (truffle & builder) that automatically upload verified contract's source with their deployed instances
- Create an API gateway that allow for easy integration with tradition IT and enterprise system through OpenAPI & GraphQL endpoints
- Abstracting away the complexities of interacting with blockchain, such as nonce, key and account management to reduce friction.

### Milestone #5: Personal dashboards
~2-3 weeks - development 

- User access management to allow anyone to keep track of their favourites contracts and bookmarks
- Build in logs and monitoring to filter and track a deployed smart contract's transactions, events or state changes
- Add notifications and webhooks that allow registered users to subscribe to these events and changes to quickly respond or further integrate with their systems.

### Total
Total Estimated Duration: 9-12 weeks 

# Who

**Wesley van Heije** – independent engineering & tech lead

Building product & teams with a successful track record and over 12 years of experience on delivering enterprise-grade products & solutions for leading international organizations, such as Microsoft, Shell, Accenture, Roche, ConsenSys, Komgo. 

- LinkedIn: https://www.linkedin.com/in/wesleyvanheije/
- Github: https://github.com/wslyvh/
- Twitter: https://twitter.com/wslyvh

Recent blockchain experiences and achievements
- Blockchain tech lead for Shell 
- Won two grants for our work on DAO's @ ETH Berlin
- Co-founder Blockchain Netherlands foundation 
- Enterprise Tech Lead for ConsenSys
- Tech Lead for Komgo, a blockchain-based trade & commodities platform
- Contributing & building open-source tools for the Ethereum ecosystem
- Won a grant for our work with zero-knowledge proofs @ Blockchaingers (Odyssey) hackathon
- Top-performer on the Ethereum Academy Program. Graduating in Dubai and participating in the Smart Dubai hackathon.

For Product Management & UX:

**Marko Prljic** - IC Product Manager / Principal Design Consultant

Creating great digital products that meet end-user needs with a focus on customer insights, data, growth, and unique user experience.

- LinkedIn: http://linkedin.com/in/markoprljic
- Github: https://github.com/markoprljic
- Twitter: http://twitter.com/markoprljic
- Dribbble: http://markoprljic.dribbble.com

Recent experiences and achievements
- 10+ years in digital customer experience, digital product and program management, digital platforms and digital consulting
- 7+ years of leadership experience leading and managing creatives and fostering harmonious collaboration with product, engineering, and marketing teams
- Design Principal at ConsenSys 
- Contributing & designing open-source tools for the Ethereum ecosystem
- Active member of several open-source initiatives that help drive and fund public goods, such as Panvala and Giveth.