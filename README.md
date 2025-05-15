# 🧠 Crypto Data Collection for Fraud Detection

This repository contains the code and documentation for collecting and integrating both on-chain and off-chain cryptocurrency data. The purpose is to build a dataset of 10,000–50,000 crypto transactions and related off-chain insights to support the development of an AI-driven fraud detection model.

---

## 🚩 Problem Statement

Fraud and scams are prevalent in the crypto ecosystem. To combat this, we aim to collect structured data that captures patterns in wallet behavior, transaction history, and scam-related discussions. This dataset will serve as the foundation for training machine learning models for fraud prediction.

---

## 📊 Data Scope

### ✅ On-Chain Data (10K–50K Transactions)

**Objective:**
Collect wallet and transaction data from Ethereum and related blockchains using public APIs.

**Sources:**

* [Etherscan API](https://etherscan.io/)
* [Glassnode API](https://glassnode.com/)
* [The Graph Studio](https://thegraph.com/studio)

**Key Columns Collected:**

* `Sender`
* `Receiver`
* `Amount`
* `Time`
* `Trade_Frequency`
* `Withdrawal_Speed`
* `Trade_Volume`
* `Contract_Address`
* `Interaction_Type`
* `Connected_Wallet`
* `Scam_Flag`
* `Interaction_Count`

### 🌐 Off-Chain Data (Contextual Behavioral Insights)

**Objective:**
Enrich on-chain data with user-reported fraud signals and behavioral metadata from community platforms.

**Sources:**

* Twitter (via Tweepy)
* Telegram public groups (via Bot API)
* Reddit (`r/CryptoCurrency`)
* Bitcointalk forums
* [CryptoScamDB](https://cryptoscamdb.org/)
* [BadBitcoin.org](https://www.badbitcoin.org/)

**Key Columns Collected:**

* `IP_Address` *(if publicly available)*
* `Timestamp`
* `User_ID`
* `Withdrawal_Amount`
* `Login_Time`
* `Post_ID`
* `Platform`
* `Text`
* `Fraud_Signal`

---

## ⚙️ Methodology

* Scripts written in Python using libraries such as `requests`, `etherscan-python`, `tweepy`, `praw`, and `BeautifulSoup`.
* Transaction filtering: based on recent blocks or known scam-associated addresses.
* Off-chain posts filtered by keywords like *"crypto scam"*, *"rug pull"*, etc.
* Where possible, off-chain mentions were linked to on-chain wallet addresses for contextual analysis.

---

## 📁 Deliverables

* `crypto_fraud_dataset.csv` — Combined dataset with 10K–50K structured entries.
* Cleaned and deduplicated data.
* Unavailable fields (e.g., `IP_Address`, `Login_Time`) marked as `"N/A"`.
* `source_log.csv` — Metadata file showing source mapping for each row.
* Python scripts and notebooks used for data collection and preprocessing.

---

## 🚀 How to Use

1. Clone the repository

   ```bash
   git clone https://github.com/yourusername/crypto-data-fraud-detection.git
   cd crypto-data-fraud-detection
   ```

2. Install dependencies

   ```bash
   pip install -r requirements.txt
   ```

3. Run data collection scripts

   ```bash
   python collect_onchain_data.py
   python collect_offchain_data.py
   ```

---

## 🛡️ License

This project is licensed under the MIT License. Use the data responsibly and attribute sources where appropriate.

---

## 🙌 Acknowledgements

Thanks to the contributors of Etherscan, Glassnode, The Graph, CryptoScamDB, and the open crypto community for enabling public data access.


