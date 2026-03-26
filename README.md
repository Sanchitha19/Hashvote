#  Voteblock — Blockchain Voting System

A secure, tamper-proof voting application built with Python, implementing a custom blockchain with SHA-256 hashing, proof-of-work consensus, and a Tkinter-based GUI.

---

##  Features

- **Blockchain-backed Votes** — Every vote is stored as a block with SHA-256 hashing and proof-of-work mining
- **Tamper Detection** — Chain validation ensures no vote can be altered after casting
- **Thread-safe Voting** — Concurrent vote casting handled safely with threading locks
- **Voter Authentication** — Voter ID-based login with registration support
- **One Vote Per Voter** — Prevents double voting with persistent voter tracking
- **Time-bound Election** — Configurable election timer with auto-close and result announcement
- **Persistent Storage** — Blockchain and voter data saved locally as JSON

---

##  Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3 |
| GUI | Tkinter |
| Hashing | SHA-256 (`hashlib`) |
| Consensus | Proof-of-Work |
| Concurrency | `threading` |
| Storage | JSON / `.txt` files |

---

##  Installation

### Prerequisites

- Python 3.7+

No external dependencies required — uses Python standard library only.

### Clone the Repository

```bash
git clone <YOUR_GIT_URL>
cd voteblock
```

### Run the Application

```bash
python voting.py
```

---

##  Usage

### 1. Register a Voter ID
- Click **Register Voter ID** on the login screen
- Enter a unique Voter ID and click **Register**

### 2. Login
- Enter your registered Voter ID and click **Login**

### 3. Cast Your Vote
- Select a candidate from the list
- Click **Vote** to cast your vote
- Each voter can vote only once

### 4. Election Timer
- The election runs for a configurable duration (default: 120 seconds)
- Once time expires, results are announced automatically

---

##  Configuration

You can modify the following constants in `voting.py`:

```python
ELECTION_DURATION = 120  # Election duration in seconds
```

To change candidates, update the list inside `VotingApp.__init__`:

```python
self.candidates = ["Alice", "Bob", "Charlie"]
```

---

## Project Structure

```
voteblock/
│
├── voting.py             # Main application
├── blockchain_data.json  # Persisted blockchain (auto-generated)
├── voter_ids.txt         # Registered voter IDs (auto-generated)
└── voted_users.json      # Tracks who has voted (auto-generated)
```

---

##  How the Blockchain Works

1. A **Genesis Block** is created at startup
2. Each vote is added as a new **Block** containing the vote data, previous block's hash, and a mined nonce
3. **Proof-of-Work** mining ensures each block hash starts with a required number of leading zeros (difficulty = 2)
4. **Chain validation** checks both hash integrity and chain linkage to detect tampering

---

##  Sample Output

```
Election Results
----------------
The winner is Alice!
```

---

## 👤 Author

Developed and maintained by **Sanchitha**
