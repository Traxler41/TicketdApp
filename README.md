# 🎟️ NFT Ticketing System (Solidity + Foundry)

A decentralized ticketing system where each ticket is minted as an **ERC721 NFT**.
Users can purchase tickets for events, and each ticket is represented as a unique on-chain asset.

---

## 🚀 Overview

This project demonstrates a **real-world use case of NFTs** beyond digital art—**event ticketing**.

### Core Idea:

* Each ticket = 1 NFT
* Ownership = Proof of attendance
* Fully on-chain minting + payment

---

## 🧱 Architecture

```
User → TicketingSystem → MintNft → NFT Minted
```

### Flow:

1. Admin creates an event
2. Admin activates the event
3. User buys ticket (pays ETH)
4. NFT is minted to user

---

## 📦 Smart Contracts

### 🔹 MintNft.sol

ERC721 NFT contract responsible for minting tickets.

**Features:**

* One NFT minted per transaction
* Stores token metadata (IPFS URI)
* Tracks total supply
* Emits mint events

---

### 🔹 TicketingSystem.sol

Handles event logic and ticket purchasing.

**Features:**

* Event creation & management
* Ticket purchase with ETH
* NFT minting via external contract
* Payment tracking per user

---

## 🧪 Testing (Foundry)

Tests are written using Foundry.

### Run tests:

```
forge test
```

### Test Coverage Includes:

* NFT name & symbol validation
* Event creation
* Event activation
* Ticket purchase flow

---

## 📂 Project Structure

```
src/
├── MintNft.sol
├── TicketingSystem.sol

test/
├── TestMintNft.t.sol
├── TestTicketingSystem.t.sol
```

---

## 🌐 IPFS Integration

NFT metadata is stored on IPFS.

### Example tokenURI:

```
ipfs://<metadataCID>
```

### Metadata JSON structure:

```json
{
  "name": "Match Ticket",
  "description": "Official NFT Ticket",
  "image": "ipfs://<imageCID>",
  "attributes": [
    { "trait_type": "Event", "value": "EL CLASSICO" },
    { "trait_type": "Seat", "value": "A12" },
    { "trait_type": "Date", "value": "2026-05-01" }
  ]
}
```

---

## ⚙️ Tech Stack

* Solidity (0.8.x)
* Foundry
* OpenZeppelin Contracts
* IPFS (Pinata / Web3.Storage)

---

## 🔐 Key Features

* ✅ NFT-based ticket ownership
* ✅ Decentralized event management
* ✅ ETH-based payments
* ✅ Smart contract interaction (contract → contract)
* ✅ Gas-efficient custom errors

---

## ⚠️ Current Limitations

This is an early-stage version.

* Same metadata used for all tickets
* No seat allocation system
* No limit on tickets per event
* No resale or transfer restrictions
* No entry validation (QR / scanning)
* Mint function not restricted (can be improved)

---

## 🔮 Future Improvements

### 🎟️ Ticket System Enhancements

* Dynamic metadata per ticket (eventId + ticketId)
* Seat allocation system
* Event capacity limits

### 🔐 Security & Logic

* Restrict NFT minting to TicketingSystem only
* Prevent duplicate ticket purchases
* Add withdrawal system for event organizer

### 📱 Real-world Features

* QR-based ticket validation system
* Mobile/web frontend (Wallet Connect)
* Ticket resale marketplace

---

## 🧠 Learnings from this Project

* ERC721 NFT standard implementation
* Contract-to-contract interaction
* Handling ETH payments in smart contracts
* Using IPFS for decentralized storage
* Writing tests using Foundry

---

## 🛠 Setup & Installation

```bash
git clone <your-repo-link>
cd ticketdApp
forge install
forge build
```

---

## ▶️ Usage

1. Deploy `MintNft.sol`
2. Deploy `TicketingSystem.sol` with NFT contract address
3. Create event via `setEvent()`
4. Activate event via `setActivateEvent()`
5. Users call `buyTicket()` with ETH
6. NFT is minted to user wallet

---

## 👤 Author

Built as a first step into **Web3 development and real-world NFT applications**.

---

## 📜 License

MIT
