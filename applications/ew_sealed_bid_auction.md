# Energy Web Innovation Challenge Proposal
* **Project Name**: EW Sealed-Bid Auction
* **Project Proposer GitHub**: https://github.com/BlockInfinity
* **Energy Web Chain Payment Address**: 0xed639a0A729dAa401C4eda9D1Ea28868da385765

## Project Description
We are working on a system as a part of [flexQgrid](https://flexqgrid.de/english/) where power plant operators can auction off energy futures tied to specific time slots using a blockchain protocol. The project's goal is to even out power consumption disparity by introducing price disparity between time slots. For this, we need a decentralized sealed-bid auction scheme.

There are many such schemes described in literature. However, they usually have at least one of the following weaknesses:
- The protocol is not actually a decentralized auction because it requires a trusted third party.
- The protocol requires that all bidding parties behave honestly.
- The protocol requires that the auctioneer behaves honestly.
- The protocol is computationally expensive or requires many rounds of communication.
- The protocol requires an unspecified circuit for a multi-party computation. Even if specified, such circuits are difficult to trust because verifying them is very difficult.

Often, the second bullet point is manifested as the protocol not being able to handle parties that stop responding. The third bullet point frequently is manifested as the decentralized auction not being censorship-resistant if the auctioneer dismisses bids.

We propose an auction scheme that only builds on simple cryptographic primitives so it is easy to understand.

### The Protocol
1. The auctioneer creates the auction. To do so, they inform the contract about the kind of auction to be held, the objects to be auctioned off, and a list of public keys to which only they know the corresponding secret keys. Furthermore, they pay some collateral.
2. Buyers submit their bids to the contract. These bids take the form of commitments. To submit a bid, collateral must be paid to the contract.

This concludes the auctioning period. The opening period begins.

3. Each bidder chooses an index of the list of public keys the auctioneer published. They then each encrypt the opening to their commitment using their chosen public key and submit the ciphertext to the contract.

This concludes the opening period. The evaluation period begins.

4. The auctioneer decrypts all openings and checks whether they actually open the commitments. For each commitment that cannot be opened, the auctioneer passes the commitment's ID and the linked secret key to the contract. The contract then checks whether the commitment really cannot be opened. If so, the commitment is disregarded.
5. The auctioneer determines the auction's result and passes it to the contract. They also pass to the contract the list of secret keys the corresponding public keys to which the winners chose to encrypt their openings with.
6. The contract determines whether the information given to it in the previous step can be correct.

This concludes the evaluation period. The slashing period begins.

7. Each bidder that should be a winner but has not been declared a winner passes their opening to the contract.
8. The contract checks whether the bidder really should be a winner. If so, the auction fails and the auctioneer's collateral is paid to the bidder.

This concludes the slashing period. The payout period begins.

9. If the objects that were to be auctioned off live on the blockchain and have been given to the contract in step 1, the contract sends them to the winners after it received payment.
10. The auctioneer receives their collateral back. All users who submitted valid openings receive their collateral back. Winning users only receive their collateral back after payment.

This concludes the payout period. The open-ended timeout period begins.

11. The auctioneer receives the collateral of all winners who did not pay.

We intend to use building blocks from the EW stack as far as possible and to make the auction executable on the EW chain.

### Privacy Considerations
Note that the protocol does not ensure the privacy of everyone involved. Most notably, the privacy of the winners is violated because their bids are made public. However, we reckon that as payments were to be made on-chain anyway so that the contract can check their validity, it is reasonable to assume that they would be publicly known regardless.

Furthermore, the privacy of non-winning bidders might get violated. This only happens if a fraudulent user or an auction winner were to choose the same public key. Note that the fraudulent user would lose their collateral. This is to discourage bad actors from using up all available public keys in order to force the auctioneer to publish all secret keys. It is possible to compensate users for privacy violations by giving them the fraudulent user's collateral. Alternatively, this problem can be avoided by having users reserve public keys. However, this results in more blockchain transactions.

## Team
* **Members**: Christoph Michelbach, Matthias Stumpp, Magnus Gödde
* **Code Repositories**: https://github.com/BlockInfinity
* **Website**: https://blockinfinity.com
* **Team's Experience**:
We are experienced in computer science, cryptography, and the energy industry. We design and implement smart contract architectures and dapps with a strong focus on Ethereum and the energy sector. Among other things, we are currently investigating scenarios of the application of blockchain in flexibility management of energy in the collaborative research project [flexQgrid](https://flexqgrid.de/english/). We would be glad to incorporate the results of this challenge into flexQgrid.

## Development Roadmap
* Total Estimated Duration: 10 weeks

### Milestone 1: Assessment of Details
* Estimated Duration: 2 weeks
* Goal: Weighing the advantages and disadvantages of various details (such as whether public keys need to be reserved) in order to finalize the protocol.

### Milestone 2: Contract Implementation for a Simple Auction
* Estimated Duration: 3 weeks
* Goal: Implementing a contract as described above capable of handling a simple auction type (e.g. a single-object first-price auction).

### Milestone 3: User Interface
* Estimated Duration: 2 weeks
* Goal: Implementing a user interface (web app) for interacting with the auctioning contract.

### Milestone 4: Generalization
* Estimated Duration: 3 weeks
* Goal: Generalizing the implementations to allow for more advanced auction types.

# Additional Information
We are submitting two applications to this challenge: The [EW Sealed-Bid Auction](https://github.com/energywebfoundation/challenge/pull/11) and the [EW Gas Relay](https://github.com/energywebfoundation/challenge/pull/12).
