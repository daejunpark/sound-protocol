---
title: Sound Protocol 2.0
description: A permissionless NFT factory which enables customizations for auction formats, payments, metadata, and on-chain registries.
author: Sound Protocol Team
status: Draft
--- 

## Abstract

Sound Protocol 2.0 enables creators to permissinonlessly deploy gas-efficient NFTs (minimal, non-upgradeable proxies) from a factory contract. Initially, the NFTs will follow the 721a format. The protocol enables support for customizing auction formats, payments, metadata, and on-chain registry management.

## Contracts

- `SoundCreatorV1.sol`
  - Upgradeable via [UUPSUpgradeable](https://docs.openzeppelin.com/contracts/4.x/api/proxy#UUPSUpgradeable)
  - Deploys [minimal proxies (clones)](https://eips.ethereum.org/EIPS/eip-1167) of `Sound721aV1.sol` & initializes them with customizable configurations.
- `Sound721aV1.sol`
  - Logic contract for the proxies deployed from SoundCreatorV1
  - Extended version of the [721a implementation](https://www.azuki.com/erc721a)
- `SoundXyzRegistryV1.sol`
  - Upgradeable via [UUPSUpgradeable](https://docs.openzeppelin.com/contracts/4.x/api/proxy#UUPSUpgradeable)
  - Stores registry of NFTs by sound.xyz artists
  - Requires signature from sound.xyz to register NFTs