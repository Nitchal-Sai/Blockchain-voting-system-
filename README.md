# ⛓ ChainVote – Blockchain Voting System

A fully client-side decentralized voting system that simulates blockchain technology using the **Web Crypto API (SHA-256)** and **Proof-of-Work** mining.

## 🚀 Features

- **SHA-256 Hashing** via the browser's native `crypto.subtle` API
- **Proof-of-Work Mining** – each vote is "mined" into a block
- **Immutable Ledger** – votes are chained via `previousHash`
- **Chain Validation** – detect tampered or invalid blocks
- **Tamper Demo** – see blockchain integrity in action
- **Wallet Simulation** – Ethereum-style address generation
- **Double-vote Prevention** – each wallet can only vote once
- **Live Results** – real-time tally with percentage bars
- **Blockchain Explorer** – inspect every block's hash, nonce, and data

## 📁 Project Structure

```
blockchain-voting/
├── index.html              # Main entry point
├── package.json            # NPM config + dev server scripts
├── README.md
├── css/
│   └── style.css           # All styles (dark theme, animations)
└── js/
    ├── crypto.js           # SHA-256, wallet generation, proof-of-work
    ├── blockchain.js       # Block & Blockchain classes
    ├── ui.js               # DOM rendering helpers
    └── app.js              # Bootstrap, event handlers, candidate data
```

## 🛠 Getting Started

### Option A – Just open in a browser
```
Open index.html directly in any modern browser (Chrome, Firefox, Edge, Safari).
No build step needed!
```

### Option B – Dev server (recommended for development)
```bash
npm install
npm run dev        # live-server with hot reload on :3000
# OR
npm start          # serve static files on :3000
```

## 🗳 How to Use

1. **Connect Wallet** – Click the button in the header to generate a simulated wallet address.
2. **Cast Vote** – Go to "Cast Vote", select a candidate, and click "Submit Vote to Blockchain".
3. **Watch Mining** – A mining animation shows the proof-of-work in progress.
4. **Explore Blocks** – Go to "Blockchain" to inspect every mined block.
5. **Tamper Demo** – Click "Tamper Demo" to corrupt a block and then "Validate Chain" to see the integrity check fail.
6. **View Results** – Go to "Results" to see live vote tallies.

## 🔐 Blockchain Concepts Used

| Concept            | Implementation                                               |
|--------------------|--------------------------------------------------------------|
| Hashing            | `crypto.subtle.digest('SHA-256', ...)`                       |
| Block chaining     | Each block stores `previousHash`                             |
| Proof of Work      | Mining loop finds `hash.startsWith('00')`                    |
| Immutability       | Changing a block breaks all subsequent `previousHash` values |
| Double-vote guard  | `Set<voterId>` prevents duplicate votes                       |
| Consensus          | Simulated Proof of Authority (single node demo)              |

## 📦 Dependencies

All runtime code is **zero-dependency vanilla JS**. Dev dependencies are optional:

| Package       | Purpose                    |
|---------------|----------------------------|
| `live-server` | Hot-reload dev server      |
| `serve`       | Production-like static server |
| `eslint`      | JavaScript linting         |
| `jest`        | Unit testing framework     |

## ⚠ Disclaimer

This is a **client-side educational simulation**. For a production blockchain voting system, you would use:
- A real distributed blockchain (Ethereum, Hyperledger, etc.)
- Smart contracts for vote logic
- Zero-knowledge proofs for voter privacy
- Hardware-based key management

## 📄 License

MIT
