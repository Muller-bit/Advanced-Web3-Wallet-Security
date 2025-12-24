# Safe{Wallet} Transaction Security Checklist

Use this checklist **before every signature and execution**.

---

## ✅ Signature Phase Checklist

- [ ] `to` address verified on Etherscan
- [ ] Contract source verified
- [ ] Function decoded and expected
- [ ] Parameters match intent
- [ ] Token approval amount reasonable
- [ ] `value` is correct (usually 0)
- [ ] `operation` = CALL (0)
- [ ] Gas fields are zero or expected
- [ ] Safe nonce is correct

### Hardware Wallet

- [ ] Safe hash independently calculated
- [ ] Hash matches device exactly

---

## ✅ Execution Phase Checklist

- [ ] Transaction sent to Safe contract
- [ ] Outer call = `execTransaction`
- [ ] Nested `to` address verified
- [ ] Nested calldata unchanged
- [ ] Execution matches signed intent

---

## 🚨 Red Flags (Immediate Reject)

- Unlimited approvals without reason
- Unknown contract address
- Hash mismatch
- Non-zero refundReceiver
- UI-only confirmation without decoding

---

## Final Rule

> If one checklist item fails — do not sign.
