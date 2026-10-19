# Lab 02 — Seeing the Hash Chain on a Live Blockchain

## Run result

All three required checks passed:

- `CHECK chainId == 11968: OK`
- `CHECK hash links: OK`
- `CHECK tip tx count: OK`

Run details:

- **Tip height:** `718041`
- **Tip hash:** `0xfd85d434062114ba36c2e600e63cfec4568f133f425305c1daa78be366afd881`
- **Tip parentHash:** `0x9ccb7e24e2d6156cb4bdf7037eb74e5077370458dc40f07a21132bf82615b7b1`
- **Previous block hash:** `0x9ccb7e24e2d6156cb4bdf7037eb74e5077370458dc40f07a21132bf82615b7b1`
- **Transactions in tip block:** `1`

## Q1
Yes. The `parentHash` of the tip block is exactly equal to the hash of the block immediately below it.

- Tip block `parentHash`:
  `0x9ccb7e24e2d6156cb4bdf7037eb74e5077370458dc40f07a21132bf82615b7b1`

- Previous block `hash`:
  `0x9ccb7e24e2d6156cb4bdf7037eb74e5077370458dc40f07a21132bf82615b7b1`

Therefore, the blocks are correctly linked by hash.

## Q2
If one byte inside block `#(tip−2)` were secretly changed, that block's hash would also change because cryptographic hashes are highly sensitive to input changes. The `parentHash` stored in the following block would then no longer match the modified block's hash. Honest nodes would detect the broken hash link and reject the tampered history.

## Q3
The block **3 rows above the bottom** is block `718038`.

With tip block `718041`, its confirmations are:

`718041 - 718038 + 1 = 4 confirmations`

So the answer is **4 confirmations**.

## Q4
The 97-byte `extraData` suggests a **Proof-of-Authority (PoA)** consensus family. In PoA, approved validators produce blocks, whereas Bitcoin's Proof-of-Work requires miners to compete by performing computational work.
