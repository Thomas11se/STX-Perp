

# STX-Perp Smart Contract

## 📄 Overview

**STX-Perp** is a smart contract for trading **options** and **perpetuals (perps)** on the Stacks blockchain using STX tokens. The contract enables the creation, purchase, and exercise of options contracts and sets up foundational logic and data structures for perpetual futures.

> 🔐 This contract is written in **Clarity**, the smart contract language for Stacks, and is designed to be modular and easily extendable.

---

## 📦 Features

### ✅ Options Trading

* **Create Option** – Define a new call or put option with expiry, strike price, amount, and premium.
* **Buy Option** – Purchase the option by paying the premium to the option creator.
* **Exercise Option** – Settle the option before expiry; transfers STX based on direction (call or put).
* **Option Expiry Check** – Determine if an option has expired.

### 🧮 Perpetual Positions (Foundational Logic)

* **Position Management** – Data structure for tracking long/short positions, margin, leverage, liquidation state.
* **Funding Rate Support** – Variable to store and apply funding rates over time.
* **Liquidation Logic Placeholder** – Constants and fields prepared for later implementation of margin and liquidation enforcement.

---

## 🧠 Smart Contract Structure

### Constants

* Owner, error codes, leverage/margin rules, funding rate precision.

### Data Variables

* Price feeds, funding rate, total open interest (long/short).

### Maps

* `options`: Stores each option contract.
* `positions`: Stores each perpetual position.
* `user-balances`: Tracks user STX balances (used conceptually here).
* `user-positions`: Maps user to their open position IDs.

### Public Functions

| Function             | Description                           |
| -------------------- | ------------------------------------- |
| `create-option`      | Create a new option contract.         |
| `buy-option`         | Buy an option by paying the premium.  |
| `exercise-option`    | Exercise an option to receive payout. |
| `get-option`         | View option details by ID.            |
| `get-next-option-id` | View the next available option ID.    |
| `is-option-expired`  | Check if an option has expired.       |

---

## ⚠️ Error Codes

| Code   | Meaning                  |
| ------ | ------------------------ |
| `u100` | Not authorized           |
| `u101` | Invalid amount or input  |
| `u102` | Option not found         |
| `u103` | Option expired           |
| `u104` | Insufficient STX balance |
| `u105` | Position not found       |
| `u106` | Insufficient margin      |
| `u107` | Position liquidated      |
| `u108` | Invalid leverage         |

---

## 💡 Future Improvements

* Add order book or AMM support for option pricing and matching.
* Implement real-time STX oracle integration.
* Finalize and activate perpetual margin and liquidation mechanics.
* Add funding payments, PnL tracking, and auto-liquidation logic.
* Add user portfolio and position history tracking.

---

## 🔧 Requirements

* Stacks blockchain environment (Clarinet or similar)
* STX tokens for interaction
* Block-height-based expiry awareness

---

## 📜 License

MIT License. Use and modify freely with attribution.

---
