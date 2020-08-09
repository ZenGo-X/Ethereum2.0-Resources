# Ethereum 2.0 resources

## Introduction

Ethereum 2.0 is the next step in the evolution of the Ethereum platforms. It brings with it many changes, including Proof-of-Stake, Sharding, new client implementations, new cryptography and much more.

There are a lot of write ups, and lot of information regarding Eth 2.0. This repository aims to be a curated list and concise of links to the best Ethereum 2.0 resources out their.

## Generally on Eth 2.0

Ethereum 2.0 introduces several important changes to the way the current system is operated:

- Proof-of-Stake: Instead of the current mechanism of Proof-of-work, where dedicated hardware is requires to participate in the consensus protocol and generate blocks, Eth 2.0 switches to Proof-of-Stake. Validators (miners) are chosen to propose and to attest to blocks according to their proportional holdings of Eth. Validators who deviate from the protocol will be punished -- slashed.
- Sharding: Instead of a single monolithic chain, several chains (shards) will run in parallel. They will run independently from each other, and moving information from one shard to another will require special lock-step transactions
- eWasm execution: Instead or in addition to the currently running Ethereum-Virtual-Machine, Eth 2.0 is planned to allow execution of Web Assembly instructions, in attempt to popularize smart contract languages that do not require any specialized skills.

The transformation to Eth 2.0 is done in several stages, each introducing another aspect of the upgraded platform.

- Phase 0: The beacon chain. The beacon chain is the backbone of the proof-of-stake and sharding protocols of Eth 2.0. The beacon chain will only hold information on the current set of validators, and links to blocks on all future shards.
- Phase 1: Shards. During this stage, several Shards will operate as independent but linked blockchains. Validators will be assigned (pseudo) randomly to shards, and will attest to blocks on each shard. The head of the shards are linked to the beacon chain
- Phase 2: Execution. Only at this stage will the platform be fully operational, enabling transfers and smart contract execution.

## Knowledge bases

- ConsenSys: https://consensys.net/knowledge-base/ethereum-2
- BeaconChain: https://kb.beaconcha.in
- Calculator + resources: https://docs.google.com/spreadsheets/d/15tmPOvOgi3wKxJw7KQJKoUe-uonbYR6HF7u83LR5Mj4/edit#gid=1548910165

## Staking

- Requires 32 ETH to begin staking
  ETH 2 only begins to “work” when there are enough validators and enough locked ETH on the chain

* Misbehaviour will result in slashing
  - Minor slashing for liveness: About 50% uptime is requires to be profitable
  - Massive slashing for double spend attempts

- Staked ETH will be locked up at least until stage 1.5

### Staking walkthrough

Currently, Eth 2.0 testn

The easiest way to participate in staking on the latest testnet _medalla_ is by following the official Ethereum 2.0 launchpad

- Ethereum org Launchpad: https://medalla.launchpad.ethereum.org

Read the blog on the using the launchpad:
Blog: https://blog.ethereum.org/2020/07/27/eth2-validator-launchpad/

Prysm guide: https://prylabs.network/participate

## Keys

Unlike Ethereum 1.0, where each address had only one pair of public in private keys, validators in Ethereum 2.0 have two pairs:

- A validator key signing blocks
- A withdrawal key for depositing and withdrawing funds

The separation is to increase security. The validator key needs to be kept “hot” to always be available to sign blocks, while the withdrawal can be kept in cold storageBoth keys are derived from the same mnemonic by following the spec of EIP-2333.

Keys use the BLS12-381 curve, which makes signature aggregation more efficient. Required to allow multiple validators to attest on a block.

Blog on Ethereum keys: https://blog.ethereum.org/2020/05/21/keys/

Beaconchain: https://kb.beaconcha.in/ethereum-2-keys

EIP: https://eips.ethereum.org/EIPS/eip-2333

BLS for the rest of us: https://hackmd.io/@benjaminion/bls12-381

Key generation and deposit repository: https://github.com/ethereum/eth2.0-deposit-cli

## Consensus

- Intro to sharding and beacon chain: https://ethos.dev/beacon-chain/
- Gasper paper (Eth 2.0 consensus): https://arxiv.org/abs/2003.03052

## Block explorers

- Etherscan: https://beaconscan.com
- Beacon Chain: https://beaconcha.in

### Validator stats

- Eth2stats: https://eth2stats.io/medalla-testnet

## Ethereum 2.0 client implementations

- Prysm (Go): https://github.com/prysmaticlabs/prysm
- Lighthouse (Rust) https://github.com/sigp/lighthouse
- Teku (Java): https://github.com/PegaSysEng/teku
- LodeStart (TypeScript): https://github.com/ChainSafe/lodestar
- Trinity (Python): https://github.com/ethereum/trinity

## Forums

- Eth research: https://ethresear.ch
- Ethereum magicians: https://ethereum-magicians.org

More Docs
Roadmap https://docs.ethhub.io/ethereum-roadmap/ethereum-2.0
Economics: https://docs.ethhub.io/ethereum-roadmap/ethereum-2.0/eth-2.0-economics/

Eth 2.0 spec https://github.com/ethereum/eth2.0-specs

Annotated spec https://benjaminion.xyz/eth2-annotated-spec/

Ethereum blog https://blog.ethereum.org/2020/06/02/the-state-of-eth2-june-2020/

Sharding FAQ https://eth.wiki/sharding/Sharding-FAQs

Sharding research links https://notes.ethereum.org/@serenity/H1PGqDhpm?type=view
