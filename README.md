# Thunder Loan Smart Contract Audit

## Overview

Thunder Loan is a flash loan protocol inspired by Aave and Compound. This repository contains the security audit of Thunder Loan, analyzing its smart contracts for vulnerabilities, optimizations, and adherence to best security practices. The audit also covers the ThunderLoanUpgraded contract and its integration with the TSwap price oracle.

## Scope of Audit

The audit focuses on:

- **Security vulnerabilities**: Identifying potential exploits, reentrancy attacks, and access control issues.
- **Gas optimizations**: Improving contract efficiency and reducing transaction costs.
- **Logic verification**: Ensuring the implementation aligns with intended functionality.
- **Upgrade security**: Reviewing the ThunderLoanUpgraded contract for safe migration.
- **Compliance checks**: Verifying adherence to Solidity best practices.

### In-Scope Contracts

- **Interfaces**:
  - IFlashLoanReceiver.sol
  - IPoolFactory.sol
  - ITSwapPool.sol
  - IThunderLoan.sol
- **Protocol Contracts**:
  - AssetToken.sol
  - OracleUpgradeable.sol
  - ThunderLoan.sol
- **Upgraded Protocol**:
  - ThunderLoanUpgraded.sol

## Audit Methodology

1. **Manual Code Review**: Analyzing smart contract code line by line.
2. **Static Analysis**: Using tools to detect vulnerabilities and inefficiencies.
3. **Dynamic Testing**: Simulating real-world interactions to uncover unexpected behaviors.
4. **Fuzz Testing**: Running randomized inputs to identify edge cases.
5. **Formal Verification (if applicable)**: Ensuring correctness of key functions.

## Findings Summary

| Severity      | Count |
| ------------- | ----- |
| Critical      | X     |
| High          | X     |
| Medium        | X     |
| Low           | X     |
| Informational | X     |

A detailed report of findings and recommendations is included in the **Audit Report**.

## Tools Used

- Slither
- Mythril
- Foundry (for fuzz testing)
- Hardhat/Echidna
- Manual review

## Known Issues

- **getCalculatedFee may result in zero fees for small flash loans.** This is an accepted limitation.
- **First depositor advantage in assetToken distribution.** A large initial deposit is planned to mitigate this.
- **Incompatibility with certain ERC-20 tokens.** Fee-on-transfer, rebasing, and ERC-777 tokens may cause issues; only vetted tokens will be added.

## Disclaimer

This audit does not guarantee the absence of vulnerabilities. It is the responsibility of the Thunder Loan team to implement fixes and conduct further testing before deployment.
