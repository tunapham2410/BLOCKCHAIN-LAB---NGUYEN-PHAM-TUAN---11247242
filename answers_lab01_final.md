# Lab 01 — Your First Wallet

## Student Information
- **Wallet address:** `0x00ec36985cFB333a446FE9678d8e4fc358434254`
- **Network:** TrustKeys L1 TestNet
- **Chain ID:** `11968`

## Evidence to attach
1. Screenshot showing the received testnet airdrop balance.
2. Screenshot showing the successful transaction sent to a classmate.
3. Do **not** include any seed phrase or private key.

## Step Completion Record
- **Step 1 — Create wallet:** Completed.
- **Step 2 — Back up seed offline:** Completed privately. Seed phrase is not included in this submission.
- **Step 3 — Join class group:** Completed.
- **Step 4 — Receive airdrop:** Completed.
- **Step 5 — Send coin to classmate:** Completed. Classmate confirmed receipt and sent coin back.
- **Step 6 — MetaMask + dapp:** Bonus; not required for the pass condition.

## Transaction Notes
- **Date:** `19/10/2026`
- **Airdrop balance received:** `0.49586 TRUSTK`
- **Partner address:** `0x3D0785ce2a09c6aFb0fd3947E0cdC6bC9e4745d9`
- **Partner address (masked):** `0x3D0785...4745d9`
- **Amount sent:** `0.01 TRUSTK`
- **Received back:** `Yes`
- **Transaction status:** `Broadcast transaction success`
- **Transaction hash shown in screenshot:** `0x0df5ae...6da940e1`

## Wrap-up Answers

### 1. Where does your coin balance actually live — in the app, or on the chain? How do you know?
The coin balance lives **on the blockchain**, not inside the wallet app. The wallet reads the balance from the blockchain through the RPC endpoint.

### 2. You created a wallet with no email/password. What single thing must you protect, and why?
I must protect the **seed phrase/private key** because it controls access to the wallet and all funds associated with it. Anyone who obtains it can recreate the wallet and control its assets.

### 3. You had coin but sending still deducted a little extra. What was that, and what coin paid it?
The extra amount was the **gas fee**, which is paid using the network's **native coin**.

### 4. Your app.dem.chat wallet and MetaMask showed the same address for the same key. Why must that be true?
The address is derived **deterministically** from the same cryptographic key, so any compatible wallet using the same key computes the same address.

### 5. A DM says “verify your wallet — paste your 12 words here to keep your airdrop.” What do you do?
I should **ignore and report the message as a scam** and never share the seed phrase.
