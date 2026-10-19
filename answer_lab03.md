# Lab 03 — Hash, Merkle Tree & Digital Signatures

## Q1
Each extra leading hexadecimal zero multiplies the expected Proof-of-Work by approximately **16×**.

Reason: one hexadecimal digit represents 4 bits and has 16 possible values. The probability that one hex digit is exactly `0` is `1/16`, so requiring one additional leading zero makes a valid hash about 16 times rarer.

## Q2
Verifying a nonce that has already been found takes only **one SHA-256 hash call** in the toy PoW.

This shows the key asymmetry of Proof-of-Work: finding a valid nonce is computationally expensive because many guesses may be needed, while verifying a proposed nonce is very cheap.

## Q3
For `n = 1,000,000` transactions, a Merkle proof contains about **20 sibling hashes** because:

`ceil(log2(1,000,000)) = 20`

A Merkle proof therefore grows logarithmically with the number of transactions.

## Q4
One real application is **SPV (Simplified Payment Verification)** in Bitcoin. An SPV client can verify that a transaction is included in a block using a Merkle proof without downloading every transaction in that block.

## Lab 3.2 — Merkle Tree Result

All checks passed:

- `CHECK proof tx0: OK`
- `CHECK proof tx1: OK`
- `CHECK proof tx2: OK`
- `CHECK proof tx3: OK`
- `CHECK proof tx4: OK`
- `CHECK tamper detected: OK`
- `CHECK root recomputation: OK`
- `OVERALL: ALL CHECKS OK`

## Lab 3.3 — Sign, Verify & Recover

### Output
- **Address:** `0xc78667506C74aAc6c143225eCa19b1aBf487011D`
- **Same message gives identical signature:** `True`
- **Recovered address matches original:** `True`
- **Tampered message recovers a different address:** `True`

### Same-message signature question
Yes. Signing the same message twice with the same private key produced the same signature in this run.

This is explained by **RFC 6979**, which specifies deterministic nonce generation for ECDSA.

### Integrity explanation
The digital signature is bound to the exact message content. Changing even one character changes the message hash. Therefore, when the original signature is checked against the tampered message, it recovers a different address instead of the original signer. This demonstrates **integrity** because any modification to the signed message is detectable.
