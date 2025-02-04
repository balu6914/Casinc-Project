# **Existing System Documentation**

## **1. Overview**

The existing system is a **roulette-based casino game** that operates on **Node.js (backend) and Vanilla JS (frontend)**. It currently **does not use smart contracts** for payment management, relying instead on a centralized Web3-based payment system. However, this system has faced multiple **security vulnerabilities** in the past, leading to hacks and unauthorized fund withdrawals.

## **2. Functionalities & Features**

### 🎰 **Game System (Roulette)**

- Players **deposit funds** before playing.
- Users can **place bets** on different outcomes.
- Winning amounts are **stored in a separate winnings account** before being withdrawn.
- **Admins review withdrawal requests** before processing payments.

### 💰 **Payment System (Off-Chain Web3 Transactions)**

- Users can **deposit funds** into their accounts.
- Betting transactions are **processed off-chain** using a **centralized payment system**.
- Winnings are **locked for a period before withdrawal** (to prevent abuse).
- Withdrawals require **admin approval** before funds are released.

### 🔒 **Admin Controls (Multisig Security)**

- **Admins can set game parameters** (e.g., bet multipliers, limits).
- **Admins manually approve withdrawal requests** to prevent fraud.
- A **multisig mechanism** is used for sensitive operations.

### 💬 **Chat System**

- Users can interact using a **real-time chatbox** powered by WebSockets.
- Chat **rules and moderation features** are enforced (e.g., no begging, no advertising).
- Users must **accept chat rules** before participating.

### 🎲 **Provably Fair Mechanism**

- Uses **HMAC_SHA256 hashing** to ensure **fairness and transparency** in game outcomes.
- The **client seed, server seed, and nonce** generate random numbers for bets.
- Players can **verify game fairness** by reviewing past hashes.

## **3. Existing Tech Stack**

| **Component**              | **Technology Used**                          |
| -------------------------- | -------------------------------------------- |
| **Frontend**               | **Vanilla JS** (Legacy)                      |
| **Backend**                | **Node.js (Express.js)**                     |
| **Database**               | **MongoDB** (Primary)                        |
| **Blockchain**             | **Web3 (No Smart Contract)**                 |
| **Realtime Communication** | **WebSockets (socket.io)**                   |
| **Authentication**         | **Session-based Auth (Likely JWT-based)**    |
| **Hosting**                | **Unknown (Likely Self-Hosted / VPS-Based)** |

## **4. Current Issues & Challenges**

1. **Security Vulnerabilities**
   - Multiple past hacks due to centralized payment system.
   - **No smart contract usage** to ensure trustless transactions.
2. **Outdated Frontend**

   - Vanilla JS is **harder to maintain and scale** compared to modern frameworks.

3. **Admin-Dependent Withdrawals**

   - **Manual approval required** for every withdrawal, adding delays.

4. **Database Scalability Concerns**
   - MongoDB is used, but **no caching layer (Redis)** to handle high loads efficiently.
