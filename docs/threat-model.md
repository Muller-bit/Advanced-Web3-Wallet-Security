---

## 📄 docs/threat-model.md

```md
# Threat Model: Safe{Wallet} UI-Based Attacks

This document outlines realistic threats when interacting with Safe{Wallet} via web UIs.

---

## Assets at Risk

- Safe funds (ETH, ERC20, NFTs)
- Multisig owner signatures
- DAO treasury control

---

## Trust Assumptions

- Front-end UI is NOT trusted
- Wallet software is semi-trusted
- Hardware wallet is trusted for display integrity
- Blockchain data is trusted

---

## Primary Threats

### 1. Compromised Front-End

- UI displays benign transaction
- Wallet signs malicious calldata

### 2. Parameter Manipulation

- `to` address replaced
- `spender` changed in approve()
- Unlimited token approvals

### 3. Gas Refund Exploits

- Non-zero refundReceiver
- Gas siphoning attacks

### 4. Execution Substitution

- Execution calldata differs from signed intent
- Owners fail to re-verify on execution

---

## Mitigations

| Threat              | Mitigation                 |
| ------------------- | -------------------------- |
| UI spoofing         | Decode calldata in wallet  |
| Hidden approvals    | ABI decoding               |
| Hash mismatch       | Hardware hash verification |
| Execution tampering | Decode execTransaction     |

---

## Security Principle

> Any UI can lie.  
> Cryptographic verification cannot.
