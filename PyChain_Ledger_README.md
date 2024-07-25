# PyChain Ledger

## Overview

The PyChain Ledger is a blockchain-based ledger system designed to facilitate financial transactions for a wide range of users, including banking institutions, peer-to-peer transactions, businesses, and other entities. Blockchain technology provides a secure, transparent, and tamper-proof way to record transactions, ensuring data integrity and security.

### Potential Use Cases for Blockchain:

- **Banking Institutions:** Securely transfer funds and record transactions between banks.
- **Peer-to-Peer Transactions:** Enable individuals to directly transfer money or assets without intermediaries.
- **Businesses:** Track and record business transactions, contracts, and supply chain data.
- **Other Entities:** Record ownership of assets, manage identity verification, and store other critical data.

In this particular example, we focus on using monetary values to demonstrate how transactions can be securely recorded on the blockchain.

## Features

1. **Transaction Records:** Allows users to store transaction records consisting of a sender, receiver, and amount.
2. **Block Difficulty:** Supports adjustable difficulty levels for mining new blocks.
3. **Block Validation:** Ensures the integrity of the blockchain by validating the chain of blocks.
4. **User-Friendly Interface:** Utilizes Streamlit for a user-friendly web interface to interact with the blockchain.

## Purpose and Importance

### Transaction Records

Each transaction record is an instance of the `Record` data class, which includes:
- **Sender:** The entity sending the funds.
- **Receiver:** The entity receiving the funds.
- **Amount:** The amount of funds transferred.

Storing transaction records in a blockchain ensures that the data is tamper-proof and transparent, providing a secure way to track financial transactions.

### Block Difficulty

The difficulty level determines how hard it is to mine a new block. A higher difficulty requires more computational effort, enhancing the security of the blockchain by making it harder for malicious actors to alter the blockchain.

### Block Validation

Block validation is a critical feature in any blockchain system. It ensures that the chain of blocks is consistent and that no data has been tampered with. This process verifies that each block's hash is correct and that each block points to the correct previous block.

## Code Explanation

### Record Data Class

```python
@dataclass
class Record:
    sender: str
    receiver: str
    amount: float
```
The `Record` class defines the structure of a transaction, making it easy to create and manage transaction records.

### Block Data Class

```python
@dataclass
class Block:
    record: Record
    creator_id: int
    prev_hash: str = "0"
    timestamp: str = datetime.datetime.utcnow().strftime("%H:%M:%S")
    nonce: int = 0
    difficulty: int = 4
```
Each `Block` contains:

- **Record:** The transaction record.
- **Creator ID:** Identifier for the creator of the block.
- **Previous Hash:** The hash of the previous block in the chain.
- **Timestamp:** When the block was created.
- **Nonce:** A number used for the proof-of-work algorithm.
- **Difficulty:** The difficulty level at the time of block creation.

### PyChain Class

```python
@dataclass
class PyChain:
    chain: List[Block]
    difficulty: int = 4
```
The `PyChain` class manages the blockchain:

- **Chain:** A list of `Block` instances.
- **Difficulty:** The difficulty level for mining new blocks.

Key methods include `proof_of_work`, `add_block`, and `is_valid`.

## Screenshots

### Block Difficulty 1
![Block Difficulty 1](images/Difficulty_1.png)

### Block Difficulty 2
![Block Difficulty 2](images/Difficulty_2.png)

### Block Difficulty 3
![Block Difficulty 3](images/Difficulty_3.png)

### Block Difficulty 4
![Block Difficulty 4](images/Difficulty_4.png)

### Block Difficulty 5
![Block Difficulty 5](images/Difficulty_5.png)

### The PyChain Ledger
![The PyChain Ledger](images/The_PyChain_Ledger.png)

### Block Validation
![Block Validation](images/Block_Validation.png)

### Terminal Printouts
![Terminal Printouts](images/Terminal_Printouts.png)

## Explanation of the Records in the Ledger

The ledger displays a table with the following columns:

- **Record:** Shows the transaction details.
- **Creator ID:** Identifies who created the block.
- **Previous Hash:** The hash of the preceding block, ensuring the chain’s integrity.
- **Timestamp:** The time the block was created.
- **Nonce:** The nonce value used in the proof-of-work algorithm.
- **Difficulty:** The difficulty level at the time of block creation.

## Validation Purpose and Importance

The validation process ensures that the blockchain remains secure and tamper-proof. By validating each block, we ensure that:

- **No blocks have been altered.**
- **Each block correctly references the previous block.**
- **The integrity of the entire blockchain is maintained.**

## Introduction

The goal of this project is to create a robust blockchain system that demonstrates the principles of decentralization, security, and data integrity. By leveraging Python and Streamlit, this project provides a practical example of how blockchain technology can be used to securely record transactions.

## Technologies Used

- **Python:** The programming language used for the implementation.
- **Streamlit:** A web application framework for creating a user-friendly interface.
- **Dataclasses:** Used for creating structured data types.
- **Pandas:** Utilized for data manipulation and display.
- **Hashlib:** Used for hashing functions.

## Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone git@github.com:AlexC3105/FinTech_Mod-18_Challenge.git
   cd FinTech_Mod-18_Challenge
```

2. **Install the required libraries:**
   ```bash
   pip install streamlit pandas dataclasses hashlib
```
- **streamlit:** A web application framework for creating a user-friendly interface.
- **pandas:** Utilized for data manipulation and display.
- **dataclasses:** Used for creating structured data types (built-in for Python 3.7+).
- **hashlib:** Used for hashing functions (built-in for Python 3.x).

3. **Run the Streamlit application:**
   ```bash
   streamlit run pychain.py
```

4. **Interact with the application through your web browser.**

## Future Improvements

- **Enhanced Security:** Implement additional security features such as digital signatures.
- **Smart Contracts:** Integrate smart contract functionality to automate complex transactions.
- **Scalability:** Improve the system’s scalability to handle a larger volume of transactions.
- **User Authentication:** Add user authentication to secure access to the ledger.

## Conclusion

The PyChain Ledger project provides a hands-on demonstration of blockchain technology, showcasing its potential for secure, transparent, and tamper-proof transaction recording. This project serves as a foundational example for further exploration and development in the field of blockchain.

## Author

Alexandr Climenco