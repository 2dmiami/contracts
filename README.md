# 2d.miami: Memory Hunters - NFT Metaverse Smart Contract

## Table of Contents
1. [Introduction](#introduction)
2. [Smart Contract Overview](#smart-contract-overview)
3. [Features](#features)
4. [Usage](#usage)
5. [Getting Started](#getting-started)
6. [Smart Contract Functions](#smart-contract-functions)

---

## 1. Introduction

Welcome to the smart contract for "2d.miami: Memory Hunters," a groundbreaking metaverse gaming experience set in a dystopian future. This smart contract is designed to enable the creation and management of NFT Avatars and in-game assets, as well as facilitate airdrops as rewards for players. It supports three tiers of minting: Legendary, Rare, and Common, each with its own set of benefits and airdrop incentives.

### Key Features
1. **NFT Avatars**
    - Three-tier minting system: Legendary, Rare, and Common.
    - Whitelist functionality for Legendary and Rare mints.
    - One-time minting for Legendary mints per wallet address.
    - Public minting for Common NFTs.
2. **Airdrop Rewards**
    - Airdrop of ERC20 tokens.
    - Airdrop of Non-Fungible Tokens (ERC721).
    - Airdrop of Semi Non-Fungible Tokens (ERC1155).

---

## 2. Smart Contract Overview

This smart contract is built on the Arbitrum blockchain and utilizes the ERC-721 standard for NFT Avatars. It's an integral part of the "2d.miami: Memory Hunters" game, providing a customizable and secure solution for creating and distributing NFTs and rewards within the metaverse. The Airdrop contract is also built under the NFT Avatar smart contract to verify that wallet addresses are holders and what tier was minted.

---

## 3. Features

### NFT Avatars
3.1. **Three-tier Minting**
- **Legendary Avatars**: Reserved for whitelisted addresses, allowing one-time minting per wallet address. These avatars come with special in-game benefits and periodic airdrops.
- **Rare Avatars**: Also for whitelisted addresses, enabling multiple mintings. These avatars come with airdrops of points or hidden stories.
- **Common Avatars**: Open to the public, allowing anyone to mint NFTs. These avatars come with airdrops of points that can be used for various in-game benefits.

3.2. **Whitelist Management**
- Admins can add or remove addresses from the whitelist.
- Whitelist addresses have exclusive access to Legendary and Rare mints.

3.3. **Unique NFTs**
- Legendary Avatars are unique and limited to one per wallet address.
- Rare and Common Avatars can be minted multiple times.

### Airdrop Rewards
3.4. **Airdrop of ERC20 Tokens**
- Admins can send tokens to holders based on the tier of their Avatar.
- Note that 2dmiami will not launch with an ERC20 token. This airdrop functionality is placed here for future use.
3.5. **Airdrop of Non-Fungible Tokens (ERC721)**
- Admins can send unique NFTs to holders as rewards.
3.6. **Airdrop of Semi Non-Fungible Tokens (ERC1155)**
- Admins can send semi-unique NFTs to holders based on the tier of their Avatar.
- Note that 2dmiami will not launch with an ERC1155 token. This airdrop functionality is placed here for future use.

---

## 4. Usage

To use this smart contract, you'll need to deploy it on the Arbitrum blockchain. Once deployed, you can interact with the contract through Ethereum wallet software or by utilizing web3.js or ethers.js libraries in your DApp. To deploy Airdrop, you'll need the smart contract address from NFT Avatar and deploy it on the Arbitrum blockchain. Every function in this smart contract airdrop needs a smart contract address like ERC20, ERC721, ERC1155 to interact and it is following what token you want to transfer. Make sure the wallet address and token ID Avatar are valid. All functions are only runnable by admin.

---

## 5. Getting Started

### Prerequisites
- Ethereum development environment.
- Knowledge of Solidity and Ethereum smart contracts.

### Deployment
1. **Deploy the Contract**
    ```bash
    yarn deploy --network <your network>
    ```
2. **Verify the Contract**
    ```bash
    yarn verify <smart contract address> --network <your network>
    ```
3. **Update Config**
    Copy the smart contract address that pops up and paste it into `config/CollectionConfig.ts` on the property `contractAddress` (string).

### Integration
Integrate the smart contract with your "2d.miami: Memory Hunters" game by using the contract's functions in your codebase.

---

## 6. Smart Contract Functions

### NFT Avatar
Below are the key functions provided by the smart contract:
- `mintLegendary()`: Allows whitelisted addresses to mint Legendary NFTs (one-time per address).
- `mintEpic()`: Allows whitelisted addresses to mint Epic NFTs (multiple times).
- `mintRare()`: Allows the public to mint Rare NFTs.
- `toggleMint()`: Admin function to open mint feature.
- `setMerkleRoot()`: Admin function to set merkle root for Legendary and Epic mint.
- `setBaseUri()`: Admin function to set metadata NFT Avatar.
- `withdraw()`: Admin function to draining all the fund in smart contract.
- `getAddressAlreadyClaimed()`: public function to check a wallet address is already mint by the tier function mint.
- `exist()`: public function to check a token ID is exist ar already minted before.

### Airdrop
Below are the key functions provided by the smart contract:
- `setAmountErc20ByTier()`: setup amount token ERC20 by tier of avatar minting.
- `setAmountErc1155ByTier()`: setup amount token ERC1155 by tier of avatar minting.
- `airdropToken()`: airdrop token function in ERC20 to single wallet
- `batchAirdropToken()`: airdrop token function in ERC20 to many wallets.
- `airdropTokenToByTier()`: airdrop token function in ERC20 to single wallet and the amount is already determined
- `batchAirdropTokenByTier()`: airdrop token function in ERC20 to many wallets and the amount is already determined
- `airdropNFT721()`: airdrop NFT function in ERC721 to single wallet
- `batchAirdropNFT721()`: airdrop NFT function in ERC721 to many wallets.
- `airdropNFT1155()`: airdrop NFT function in ERC1155 to single wallet
- `batchAirdropNFT1155()`: airdrop NFT function in ERC1155 to many wallets.
- `airdropNFT1155ByTier()`: airdrop NFT function in ERC1155 to single wallet and the amount is already determined
- `batchAirdropNFT1155ByTier()`: airdrop NFT function in ERC1155 to many wallets and the amount is already determined

---


**Disclaimer:** This README provides a high-level overview of the NFT Metaverse Smart Contract. Detailed implementation and security considerations should be thoroughly reviewed before deployment in a production environment.
