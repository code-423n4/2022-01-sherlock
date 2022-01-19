# ✨ So you want to sponsor a contest

This `README.md` contains a set of checklists for our contest collaboration.

Your contest will use two repos:

- **a _contest_ repo** (this one), which is used for scoping your contest and for providing information to contestants (wardens)
- **a _findings_ repo**, where issues are submitted.

Ultimately, when we launch the contest, this contest repo will be made public and will contain the smart contracts to be reviewed and all the information needed for contest participants. The findings repo will be made public after the contest is over and your team has mitigated the identified issues.

Some of the checklists in this doc are for **C4 (🐺)** and some of them are for **you as the contest sponsor (⭐️)**.

---

## Marketing details

- https://sherlock.xyz/img/logo.svg
- @sherlockdefi
- @evert0x @jack\_\_sanford
- https://discord.com/invite/MABEWyASkp
- https://sherlock.xyz
- We have Watsons doing security work for Sherlock Protocol

---

# Contest setup

## ⭐️ Sponsor: Provide contest details

Under "SPONSORS ADD INFO HERE" heading below, include the following:

- [ ] Name of each contract and:
  - [ ] lines of code in each
  - [ ] external contracts called in each
  - [ ] libraries used in each
- [ ] Describe any novel or unique curve logic or mathematical models implemented in the contracts
- [ ] Does the token conform to the ERC-20 standard? In what specific ways does it differ?
- [ ] Describe anything else that adds any special logic that makes your approach unique
- [ ] Identify any areas of specific concern in reviewing the code
- [ ] Add all of the code to this repo that you want reviewed
- [ ] Create a PR to this repo with the above changes.

---

# Sherlock contest details

- $76,000 worth of ETH main award pot
- $4,000 worth of ETH gas optimization award pot
- Join [C4 Discord](https://discord.gg/code4rena) to register
- Submit findings [using the C4 form](https://code4rena.com/contests/2022-01-sherlock-contest/submit)
- [Read our guidelines for more details](https://docs.code4rena.com/roles/wardens)
- Starts January 20, 2022 00:00 UTC
- Ends Janaury 26, 2022 23:59 UTC

This repo will be made public before the start of the contest. (C4 delete this line when made public)

[ ⭐️ SPONSORS ADD INFO HERE ]

Code can also be viewed at https://github.com/sherlock-protocol/sherlock-v2-core @ `25b0897c236a`

Docs are available at https://docs.sherlock.xyz

An audit has been performed on `8ae51c5a2ec`, (unaudited) fixes have been included up until `4f022062a502`

## Areas of concern

- Previous audit fixes have not been re-audited
- This PR has been included in `Sherlock.sol` after the audit https://github.com/sherlock-protocol/sherlock-v2-core/pull/7/files
- `SherBuy.sol` is unaudited
- `SherClaim.sol` is unaudited

## Contracts

> Lines are calculated using `solidity-coverage`

| Contract                               | Lines | Info                                             |
| -------------------------------------- | ----- | ------------------------------------------------ |
| `Sherlock.sol`                         | 152   | Main contract using ERC721                       |
| `managers/AaveV2Strategy.sol`          | 28    | Contract to move stakers funds to AaveV2         |
| `managers/Manager.sol`                 | 14    | Abstract contract used by all managers           |
| `managers/SherDistributionManager.sol` | 27    | Contract for SHER incentives                     |
| `managers/SherlockClaimManager.sol`    | 155   | Using UMA to handle payouts                      |
| `managers/SherlockProtocolManager.sol` | 179   | Managing protocol coverage and protocol payments |
| `SherBuy.sol`                          | 39    | Standalone contract together with `SherClaim`    |
| `SherClaim.sol`                        | 18    | Standalone contract together with `SherBuy`      |
