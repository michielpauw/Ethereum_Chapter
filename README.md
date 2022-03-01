# Ethereum

December 2013: Vitalik Buterin proposes extending blockchain technology beyond financial transactions, and introduces the idea of 'smart contracts'. This is the origin of Ethereum.

Ether is the native cryptocurrency of Ethereum.

## Smart Contracts

The fundamental building blocks of Ethereum applications are called Smart Contracts. They are a piece of code written in Solidity that is run on every node of the Ethereum Virtual Machine. A token (currency) is also a smart contract. A user pays 'gas' (a certain amount of Ether) to deploy and/or execute smart contracts. These fees are used to compensate Ethereum miners for the energy required to verify a transaction.

- Autonomous
- Decentralized
- Trustless
- Transparent

### Examples

- A savings account from which funds can only be withdrawn when the user has turned 18
- A voting system, that sends a token to a user (an address) that has won the vote
- Business payrolls
- NFTs

### Tokens

Smart contracts that represent something tangible or intangible within the ecosystem are called tokens.

- Payment tokens (any sort of cryptocurrency)
- Security tokens (stocks or shares)
- Utility tokens (access to products and services that are blockchain based)

In general: fungible tokens are divisible and non-unique, whereas non-fungible tokens are unique and indivisable.

### More on smart contracts
https://www.youtube.com/watch?v=pWGLtjG-F5c

## Technology and Tools

- Written using Go programming language
- Geth is the command line tool for running an Ethereum node
- Clef is a command line tool for signing transactions and user account management
- Account: combination of account address, a public key, and a private key
- Test Ethereum networks are available, but this week we will work locally

## Hands on! Create your own Smart Contract

- Go to remix.ethereum.org (https://remix-ide.readthedocs.io/en/latest/)
- Look around in the default workspace. There are already three contracts in the contracts directory. Have a look at these contracts, and see if you can compile one (right click -> compile)
- If successfull, you will see a green check mark on the middle icon on the left. If not, have a look at what the error may be (often it's because you use the wrong compiler)
- Click on the bottom icon of the three (Deploy & Run Transactions).
- See if you can Deploy the Smart Contract you just compiled. This will not actually deploy it to any (test) network, but it will give you a way of seeing how the contract will behave
- Try to create your own Smart Contract. For an example of a token representing a currency, you can look here: https://github.com/CodeWithJoe2020/ERC20Token/blob/main/ERC20.sol (maybe create LionCoin?)
- If you want to discover further, have a look at the following video: https://www.youtube.com/watch?v=GDq7r1n9zIU
-
