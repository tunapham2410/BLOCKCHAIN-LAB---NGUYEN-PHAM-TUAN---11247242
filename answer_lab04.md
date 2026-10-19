# Lab 04 — Real Bitcoin Blocks: PoW, Fees & Merkle Root

## Run Results

- `CHECK header hash == block id: OK`
- `CHECK PoW hash < target: OK`
- `CHECK fee calculation: OK`
- `CHECK Merkle root: OK`
- `OVERALL: ALL CHECKS OK`

Observed values:

- Block height: `840000`
- bits: `0x17034219`
- target leading zero hex digits: `19`
- approximate work: `2^78.30`
- transaction count: `3050`
- first non-coinbase tx fee: `673200000 sat`
- vsize: `187 vB`
- fee rate: `3,600,000.00 sat/vB`

## Q1
The target has about **19 leading zero hexadecimal digits**.

From the run, one valid header represents approximately **2^78.30** units of expected hashing work.

The smaller the target, the harder it is to find a valid block hash below that target.

## Q2
Verifying the Proof-of-Work is cheap because Bitcoin only needs to double-SHA256 the 80-byte block header and compare the result with the target.

Finding a valid header is expensive because SHA-256 is unpredictable and preimage-resistant, so miners must try a huge number of nonce/header combinations until one hash falls below the target. This creates the asymmetry: **hard to find, easy to verify**.

## Q3
Block **840,000** was mined on Bitcoin's fourth halving day, when **Runes** also launched. This caused intense competition for limited block space and pushed fees extremely high.

The observed transaction paid about **6.732 BTC** in fees for only **187 vB**, or about **3,600,000 sat/vB**. This shows that Bitcoin fees are determined by a **mempool auction / market demand for block space**, not by a fixed protocol fee.

## Q4
The coinbase outputs total:

`4,075,061,499 sat`

The block subsidy is:

`312,500,000 sat`

Difference:

`4,075,061,499 - 312,500,000 = 3,762,561,499 sat`

The difference comes from the **transaction fees paid by all transactions included in the block**. The miner receives the block subsidy plus those collected transaction fees.

## Q5
The recomputed Merkle root exactly matches the Merkle root stored in the block header.

This proves that the transaction list used in the calculation is consistent with the set of transactions committed to by the block header. Because cryptographic hashes have strong avalanche behavior, modifying, removing, inserting, or reordering a transaction would change the Merkle root and cause the comparison to fail.
