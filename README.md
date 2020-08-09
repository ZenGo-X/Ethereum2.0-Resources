# Ethereum 2.0 resources

## Introduction

Ethereum 2.0 is the next step in the evolution of the Ethereum platforms. It brings with it many changes, including Proof-of-Stake, Sharding, new client implementations, new cryptography and much more.

There are a lot of write ups, and lot of information regarding Eth 2.0. This repository aims to be a curated and concise list of links, with minor introductions.

## Generally on Eth 2.0

Ethereum 2.0 introduces several important changes to the way the current system is operated:

- Proof-of-Stake: Instead of the current mechanism of Proof-of-work, where dedicated hardware is requires to participate in the consensus protocol and generate blocks, Eth 2.0 switches to Proof-of-Stake. Validators (miners) are chosen to propose and to attest to blocks according to their proportional holdings of Eth. Validators who deviate from the protocol will be punished -- slashed.
- Sharding: Instead of a single monolithic chain, several chains (shards) will run in parallel. They will run independently from each other, and moving information from one shard to another will require special lock-step transactions
- eWasm execution: Instead or in addition to the currently running Ethereum-Virtual-Machine, Eth 2.0 is planned to allow execution of Web Assembly instructions, in attempt to popularize smart contract languages that do not require any specialized skills.

The transformation to Eth 2.0 is done in several stages, each introducing another aspect of the upgraded platform.

- Phase 0: The beacon chain. The beacon chain is the backbone of the proof-of-stake and sharding protocols of Eth 2.0. The beacon chain will only hold information on the current set of validators, and links to blocks on all future shards.
- Phase 1: Shards. During this stage, several Shards will operate as independent but linked blockchains. Validators will be assigned (pseudo) randomly to shards, and will attest to blocks on each shard. The head of the shards are linked to the beacon chain
- Phase 2: Execution. Only at this stage will the platform be fully operational, enabling transfers and smart contract execution.

A good all-in-one intro to Eth2.0: https://ethos.dev/beacon-chain/

## Staking

The change to proof-of-stake, mandates a change in block generation process. Validators lock-up Eth (stake), and are then allowed to sign and propose blocks. At first, the system is "bootstrapped". A minimal number of validators is required. A small number of validator could give an advantage to the adversary, and break the system.

To mitigate this, the beacon chain only begins generating blocks after enough Eth is locked, and enough validators have sight up.

To participate in Eth 2.0 staking as an independent validator, the process is as follows:

1. Obtain 32 Eth
2. Generate keys for Eth validation and deposit
3. Deposit 32 Eth in a special depositing smart contract
4. Run a beacon chain client
5. Run a validator client

- Each user can run more that one validator. Each validator requires 32 ETH.

- Validators expected to behave according to the protocol. This requires them to be online for voting, and to not attempt to sign and invalid block. To enforce these rules, validators who deviate from the protocol are slashed:
  - Minor slashing for liveness: About 50% uptime is requires to be profitable
  - Massive slashing for double spend attempts: an attempt to double spend might lead to slashing of all 32 ETH

Important to note that at the moment, depositing ETH into the smart contract is non-reversible. Staked ETH will be locked up at least until stage 1.5, but will still gain staking rewards and/or slashing.

### Staking walk-through

You can experiment with participating in staking on Eth 2.0, by joining the latest testnet.
The testnet requires Goerli Eth in order to participate.

The easiest way to participate in staking on the latest testnet _medalla_ is by following the official Ethereum 2.0 launchpad

- Ethereum org Launchpad: https://medalla.launchpad.ethereum.org

- Launchpad explanatory Blog: https://blog.ethereum.org/2020/07/27/eth2-validator-launchpad/

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

- Gasper paper (Eth 2.0 consensus): https://arxiv.org/abs/2003.03052

## Knowledge bases

Links to good aggregators of knowledge with additional information on topics above and more

- ConsenSys: https://consensys.net/knowledge-base/ethereum-2
- BeaconChain: https://kb.beaconcha.in
- Ethhub: https://docs.ethhub.io/ethereum-roadmap/ethereum-2.0/eth-2.0-phases/
- Calculator + resources: https://docs.google.com/spreadsheets/d/15tmPOvOgi3wKxJw7KQJKoUe-uonbYR6HF7u83LR5Mj4/edit#gid=1548910165

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

## Sharding

- Sharding FAQ: https://eth.wiki/sharding/Sharding-FAQs
- Sharding research links: https://notes.ethereum.org/@serenity/H1PGqDhpm?type=view

## Spec

- Eth 2.0 spec: https://github.com/ethereum/eth2.0-specs
- Annotated spec: https://benjaminion.xyz/eth2-annotated-spec/

## Economics

- Economics: https://docs.ethhub.io/ethereum-roadmap/ethereum-2.0/eth-2.0-economics/

## Blogs

- Ethereum blog: https://blog.ethereum.org/
