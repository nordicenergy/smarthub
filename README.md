<h1 align="center">
  <br>
  <a href="https://www.smarthub.org/"><img src="https://www.smarthub.nordicenergy.io/content/uploads/logo-brand.png
  " alt="Nordic Energy SmartHub" width="150"></a>
  <br>
  Nordic Energy SmartHub
  <br>
  <br>
</h1>

**SmartHub** is a set of toolkits that together provide a system for issuance and management of Energy Attribute
 Certificates (EACs). This repository is an entry point to Smarthub systems. It has a goal of explaining briefly the whole system and providing you with insight and info where to explore next.

<p align="center">
  <a href="https://travis-ci.com/nordicenergy/smarthub"><img src="https://img.shields.io/travis/com/nordicenergy/smarthub/master"/></a>
  <a href="https://github.com/renovatebot/renovate"><img src="https://badges.renovateapi.com/github/nordicenergy/smarthub"/></a>
</p>

## Table of Contents
- [Packages](#packages)
- [Installation](#installation)
- [Energy Attribute Certificates](#energy-attribute-certificates)
- [Key modules and components](#key-modules-and-components)
- [Deployment](#deployment)
- [Contribution guidelines](#contribution-guidelines)

## Packages

### SDK Releases

| Package | Stable | Canary | Description |
| --- | --- | --- | --- |
| [`@smarthub/device-registry`](/packages/device-registry) | [![npm](https://img.shields.io/npm/v/@smarthub/device-registry.svg)](https://www.npmjs.com/package/@smarthub/device-registry) | [![npm](https://img.shields.io/npm/v/@smarthub/device-registry/canary)](https://www.npmjs.com/package/@smarthub/device-registry) | Contracts and client for the Device Registry |
| [`@smarthub/market-matcher-core`](/packages/market-matcher-core) | [![npm](https://img.shields.io/npm/v/@smarthub/market-matcher-core.svg)](https://www.npmjs.com/package/@smarthub/market-matcher-core) | [![npm](https://img.shields.io/npm/v/@smarthub/market-matcher-core/canary)](https://www.npmjs.com/package/@smarthub/market-matcher-core) | Matching rules and logic for market-matcher |
| [`@smarthub/market`](/packages/market) | [![npm](https://img.shields.io/npm/v/@smarthub/market.svg)](https://www.npmjs.com/package/@smarthub/market) | [![npm](https://img.shields.io/npm/v/@smarthub/market/canary)](https://www.npmjs.com/package/@smarthub/market/canary) | Contracts and client for the Smarthub Marketplace |
| [`@smarthub/smarthub`](/packages/smarthub) | [![npm](https://img.shields.io/npm/v/@smarthub/smarthub.svg)](https://www.npmjs.com/package/@smarthub/smarthub) | [![npm](https://img.shields.io/npm/v/@smarthub/market/canary)](https://www.npmjs.com/package/@smarthub/market/canary) | Contracts and client Smarthub Issuer of certificates |
| [`@smarthub/smarthub-backend-client`](/packages/smarthub-backend-client) | [![npm](https://img.shields.io/npm/v/@smarthub/smarthub-backend-client.svg)](https://www.npmjs.com/package/@smarthub/smarthub-backend-client) | [![npm](https://img.shields.io/npm/v/@smarthub/smarthub-backend-client/canary)](https://www.npmjs.com/package/@smarthub/smarthub-backend-client) | Client library for off-chain data source |
| [`@smarthub/smarthub-backend`](/packages/smarthub-backend) | [![npm](https://img.shields.io/npm/v/@smarthub/smarthub-backend.svg)](https://www.npmjs.com/package/@smarthub/smarthub-backend) | [![npm](https://img.shields.io/npm/v/@smarthub/smarthub-backend/canary)](https://www.npmjs.com/package/@smarthub/smarthub-backend) | Example backend for storing off-chain meta-data |
| [`@smarthub/user-registry`](/packages/user-registry) | [![npm](https://img.shields.io/npm/v/@smarthub/user-registry.svg)](https://www.npmjs.com/package/@smarthub/user-registry) | [![npm](https://img.shields.io/npm/v/@smarthub/user-registry/canary)](https://www.npmjs.com/package/@smarthub/user-registry) | Contracts and client for the User Registry |
| [`@smarthub/utils-general`](/packages/utils-general) | [![npm](https://img.shields.io/npm/v/@smarthub/utils-general.svg)](https://www.npmjs.com/package/@smarthub/utils-general) | [![npm](https://img.shields.io/npm/v/@smarthub/utils-general/canary)](https://www.npmjs.com/package/@smarthub/utils-general) | Utilities |

### Applications, Infrastructure and Demo

| Package | Description |
| --- | --- |
| [`@smarthub/smarthub-ui`](/packages/smarthub-ui) | UI for Smarthub |
| [`@smarthub/market-matcher`](/packages/market-matcher) | Off-chain agent for demand and supply matching |
| [`@smarthub/solar-simulator`](/packages/solar-simulator) | Solar production and consumption simulator |
| [`@smarthub/event-listener`](/packages/event-listener) | Listens to Smarthub events, triggers actions on-chain and sends notifications |
| [`@smarthub/migrations`](/packages/migrations) | Deployment and configuration utilities |

## Installation

Make sure have latest `yarn` package manager installed.

```shell
yarn
```

## Build

```shell
yarn build
```

## Test

```shell
yarn test
```

## Run demo

Make sure you have created a `.env` file in the root of the monorepo and that all necessary variables are set.
Use [`.env.example`](.env) as an example of how the `.env` file should look.

After you have the `.env` file created, run the following command:

```shell
yarn run:smarthub
```

Visit the UI at: http://localhost:3000.

## Energy Attribute Certificates
Energy Attribute Certificates, or EACs, is an official document which guarantees that produced energy comes from a renewable source. There are different standards that regulate how data is stored and validated. In Europe, this document is called Guarantee of Smarthub (GO), in North America, it's called Renewable Energy Certificate (REC), and in parts of Asia, Africa, the Middle East, and Latin America governing standard is International REC (I-REC). Standards do vary, but they all share the same core principles.

The main purpose of EACs is to act as an accounting vehicle to prove that consumed energy came from a renewable source. EACs are mostly used to address sustainability reports regarding [Scope 2 emissions](https://en.wikipedia.org/wiki/Carbon_emissions_reporting#Scope_2:_Electricity_indirect_GHG_emissions).

## Key modules and components
Overview of architecture

### Key repositories

This section lists key entry points to start your journey with Smarthub.

1. [migrations](https://github.com/nordicenergy/smarthub/tree/master/packages/migrations) - repository with build scripts that enable easy deployment of smart contracts to EWC, Volta or a local blockchain. Often used to demo and get to know features and capabilities of Smarthub.
2. [smarthub-backend](https://github.com/nordicenergy/smarthub/tree/master/packages/smarthub-backend) - Smarthub combines on and off-chain data storage. This repository is used to act as a backend service for off-chain data storage. You'll need this to run `migrations` (store data), and `smarthub-ui` to display stored data.
3. [smarthub-ui](https://github.com/nordicenergy/smarthub/tree/master/packages/smarthub-ui) - frontend of the system needed to view data stored in smart contracts (on-chain) and in the backend (off-chain). To interact Smarthub frontend you'll need [MetaMask](https://metamask.io).

### Other components

1. [user-registry](https://github.com/nordicenergy/smarthub/tree/master/packages/user-registry) - high-level library to interact with user registry. Can be used to i. a. create new user or set user's role in the system.
2. [device-registry](https://github.com/nordicenergy/smarthub/tree/master/packages/device-registry) - high-level library for creating and managing electricity producing and consuming devices. Depends on [user-registry](https://github.com/nordicenergy/smarthub/tree/master/packages/user-registry), because only user with Device Manager role can be owner of device.
3. [smarthub](https://github.com/nordicenergy/smarthub/tree/master/packages/smarthub) - a heart of Smarthub systems, contains logic for storing and transferring Energy Attribute Certificates (as a form of unique [ERC721](http://erc721.org/) tokens).
4. [market](https://github.com/nordicenergy/smarthub/tree/master/packages/market) - a library that allows to create demand (for buyers), supply (for sellers) and agreements between buyers and sellers. It also extends the `Certificate` from [smarthub](https://github.com/nordicenergy/smarthub/tree/master/packages/smarthub) and creates `PurchasableCertificate`s that can be sold on the marketplace.
5. [market-matcher](https://github.com/nordicenergy/smarthub/tree/master/packages/market-matcher) - the most important part of marketplace, guarantees automatic matching of supply and demand between sellers and buyers. Matching rules can be highly customized and afterwards the algorithm can be tested by running matching simulator.
6. [utils-general](https://github.com/nordicenergy/smarthub/tree/master/packages/utils-general) - Contains logic for more straightforward interaction with contracts, such as watching events. It is also a base layer for other libraries to build upon. It provides a foundation for things like off-chain data storage that is universal for all entities.
7. [solar-simulator](https://github.com/nordicenergy/smarthub/tree/master/packages/solar-simulator) - This service simulates smart-meter readings based on example solar data from whole year in 15-mins intervals. Also allows you to generate the config based on data from public I-REC registry.
8. [event-listener](https://github.com/nordicenergy/smarthub/tree/master/packages/event-listener) - Event listeners listen to events on the blockchain and react accordingly.

## Deployment

For deployment instructions please refer to [Deployment](https://github.com/nordicenergy/smarthub/wiki/Smarthub-Deployment) wiki page.

## Contribution guidelines

If you want to contribute to Smarthub, be sure to follow classic open source contribution guidelines (described below).

1. Commiting a change
    - Fork the repository
    - Make a change to repo code
    - Commit the change to the `master` branch
2. Pull request
    - Open a pull request from your fork `master` branch
    - Request code reviews from [@nordicenergy](https://github.com/nordicenergy)
    - Once the PR is approved and the build passes, it will be merged to the master branch
