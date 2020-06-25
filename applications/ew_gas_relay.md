# Energy Web Innovation Challenge Proposal
* **Project Name**: EW Gas Relay
* **Project Proposer GitHub**: https://github.com/BlockInfinity
* **Energy Web Chain Payment Address**: 0x910D495CfADE5f31DC1dE6814530D8B780696Fd1

## Project Description
Enabling producers and consumers of energy to perform blockchain transactions in the classical sense requires them to operate funded addresses in order to pay for transaction fees. This constitutes a substantial hurdle for many. It can therefore be desirable for the provider of a decentralized application to pay for the gas costs of its users. Additionally, doing so yields a neat separation between secrets that are used for authorization of operations and secrets that are used for paying for the operational costs of the service. Without this separation, the provider of a decentralized app might be required to hold keys controlling both contract operations and user's funds (or funds that could be interpreted as the user's, e.g. if sent to the user's address just to pay for gas). In many countries, having control over user's funds requires expensive licensing from financial supervisory authorities (e.g. BaFin in Germany). Separating these responsibilities avoids such legal and regulatory complications.

Our proposal consists of a contract similar to [ERC-725](https://github.com/ethereum/EIPs/issues/725). ERC-725 enables users to be represented on-chain as a contract. This means that the owner of an ERC-725 contract can execute arbitrary functions of other contracts as if those calls were coded into the contract. Therefore, spontaneous acting of contracts is possible. This does not yet solve the problem as the caller of the ERC-725 `execute()` function needs to be the ERC-725 contract's owner. Therefore, the user's EOA still needs to cover the gas costs and their EOA needs to be funded.

However, the `execute()` function can be extended by introducing a signature:

    function execute(uint256 _operationType, address _to, uint256 _value, bytes calldata _data, bytes calldata _signature) external

This function is not only callable by the owner but by anyone. Before the call described by the other arguments is processed, the contract must check whether `_signature` is a valid signature issued by the owner over (`keccak256` of):

    abi.encodePacked(_operationType, _to, _value, _data, address(this), executionNonce)

The current execution nonce can be retrieved by calling this function that is also to be added to the interface:

    function executionNonce() public pure returns (uint256)

Our idea is that the user can then create their transaction, sign it using their EOA, and send it to a funding node. The funding node is unable to manipulate the user's call. The only authority it has is to either wrap the transaction it received into a call to the extended `execute()` function and send it to the network (or back to the user for later use) or not to do anything. Of course, it may make that decision dependent on whether the wrapped transaction actually interacts with the decentralized application the funding node supports. The set of funding nodes is open and no authorization or registration is required to operate one.

If a funding node also creates compliant decentralized identity contracts on behalf of its users, users may perform operations on the blockchain without ever controlling any funds at any step in the process. This also eliminates the possibility of users stealing funds, e.g. if funds otherwise were to be transferred to the user's EOA or decentralized identity contract shortly before their transaction interacting with the decentralized application was executed.

The implementation will be fully compatible with the EW chain and feature a web demo app where newly created unfunded accounts can be used to execute transactions.

## Team
* **Members**: Christoph Michelbach, Alexander Kaiser
* **Code Repositories**: https://github.com/BlockInfinity
* **Website**: https://blockinfinity.com
* **Team's Experience**:
We are experienced in computer science, cryptography, and the energy industry. We design and implement smart contract architectures and dapps with a strong focus on Ethereum and the energy sector. Among other things, we are currently investigating scenarios of the application of blockchain in flexibility management of energy in the collaborative research project [flexQgrid](https://flexqgrid.de/english/). We would be glad to incorporate the results of this challenge into flexQgrid.

## Development Roadmap
* Total Estimated Duration: 5 weeks

### Milestone 1: Standardization
* Estimated Duration: 1 week
* Goal: Refining the proposal to work with various identity contracts.

### Milestone 2: Contract Implementation
* Estimated Duration: 1 week
* Goal: Creating the reference implementations of this extension of various identity contracts.

### Milestone 3: Funding Node Implementation
* Estimated Duration: 1 week
* Goal: Creating the reference implementation of a funding node.

### Milestone 4: Web App
* Estimated Duration: 2 weeks
* Goal: Creating a web demo app displaying the project's capabilities.

# Additional Information
We are submitting two applications to this challenge: The [EW Sealed-Bid Auction](https://github.com/energywebfoundation/challenge/pull/11) and the [EW Gas Relay](https://github.com/energywebfoundation/challenge/pull/12).
