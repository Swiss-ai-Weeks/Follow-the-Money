# P2P Fraud Detection Challenge: Your Mission Briefing

## Welcome, Digital Detective! 🕵️‍♂️

You have been recruited to join Viseca's elite fraud detection task force. Your mission is to uncover hidden patterns in a sea of peer-to-peer transactions and help protect hard-earned savings from sophisticated fraudsters.

### Why This Dataset Exists

This dataset mixes synthetic and real fully anonymized data.

- **Safe to Explore**: a safe playground to test the most exciting new methodologies or well-tested, reliable ML tactics.
- **Realistic Yet Simplified**: The dataset captures the essence of real payment patterns while keeping things manageable.
- **Perfectly Balanced**: It is balanced so you have enough cases to explore and detect interesting patterns, while still maintaining a high class imbalance (a key feature and challenge in fraud detection).
- **Realistic Fraud Patterns**: Some subtle fraud patterns have been embedded to test your detection skills, while keeping the complexity manageable for an engaging hackathon.

## Your Data

Data is the most important tool for detectives and AI/ML researchers. Real data present complex, multidimensional challenges. Here, the schema is simpler than what you would find in Viseca's data lakes, but it is complete and broad enough for interesting feature engineering.

### Core Tables

**Customers** (`customers.csv`)
Your everyday people with ages, genders, and cities

**Accounts** (`accounts.csv`)
Each belongs to a customer and can be active or inactive

**P2P Transactions** (`p2p_transactions.csv`) - **Your Main Target!**
The peer-to-peer payments: friend splitting dinner, paying rent, sending gifts

### Additional Info to Know Better Our Customers

**Cards** (`cards.csv`)
Credit cards belonging to our customers and linked to accounts with different tiers: Standard, Gold, Platinum

**Card Transactions** (`card_transactions.csv`)
Traditional payments: buying on-line, swiping cards at stores or withdrawing cash

**Merchants** (`merchants.csv`)
The shops and services where people spend money


### Your Columns (Detailed Schema)

**Customers** (`customers.csv`)
- **customer_id**: Unique anonymized customer identifier (format: CUXXXX)
- **address_valid_from**: Start date of current address validity
- **age_cat**: Age category: '18-29', '30-39', '40-49', '50-59', '60+'
- **gender**: Customer gender
- **city**: City of residence
- **country**: Country code (currently all 'CH' for Switzerland)

**Accounts** (`accounts.csv`)
- **account_id**: Unique anonymized account identifier (format: ACXXXX)
- **customer_id**: Reference to customer_id in customers.csv
- **is_active**: Indicates whether the account is currently active.
- **open_date**: Account opening date.
- **fraud**: Fraud indicator: 'false' for legitimate, 'generic' or 'phishing' for victims. *Note:* This is for training/testing purposes and cannot be used as a feature for modeling.

**P2P Transactions** (`p2p_transactions.csv`) - **Your Main Target!**
- **p2p_id**: Unique P2P transaction identifier (format: TRXXXX)
- **timestamp**: Transaction timestamp
- **sender_account_id**: Account ID of the sender
- **receiver_account_id**: Account ID of the receiver
- **amount**: Transaction amount in CHF
- **currency**: Transaction currency (typically 'CHF')
- **is_fraud**: Binary fraud indicator (0=legitimate, 1=fraudulent). To increase realism, some labels are false positives or negatives, reflecting the uncertainty present in real-world data. *Note:* This is your actual target.
- **is_fraud_truth**: Ground truth fraud label, with no false positives or negatives. *Note:* This is for reference only and should not be used for training or testing.

### Additional Customer Information

**Cards** (`cards.csv`)
- **card_id**: Unique anonymized card identifier (format: CAXXXX)
- **account_id**: Reference to account_id in accounts.csv
- **customer_id**: Reference to customer_id in customers.csv
- **is_active**: Indicates whether the card is currently active.
- **product_type**: Card product type: 'GOLD', 'Platinum', 'Standard'
- **first_usage_date**: First date the card was used
- **expiry_date**: Card expiration date
- **fraud**: Fraud indicator (same as accounts.csv)

**Card Transactions** (`card_transactions.csv`)
- **trx_id**: Unique transaction identifier (format: TRXXXX)
- **account_id**: Reference to account_id in accounts.csv
- **customer_id**: Reference to customer_id in customers.csv
- **card_id**: Reference to card_id in cards.csv
- **merchant_id**: Reference to merchant_id in merchants.csv
- **trx_currency**: Transaction currency (typically 'CHF')
- **trx_amount_chf**: Transaction amount in CHF
- **trx_city**: City where transaction occurred (anonymized)
- **trx_country**: Country where transaction occurred
- **is_card_present**: Whether card was physically present
- **is_purchase**: Whether transaction was a purchase
- **is_cash**: Whether transaction was a cash withdrawal
- **trx_date**: Transaction date
- **limit_exhaustion**: Credit limit exhaustion rate: the percentage of the credit card's available limit that has been used. For example, if a card has a CHF 5,000 limit and CHF 3,500 has been spent, the exhaustion rate is 70% (3,500/5,000). Higher rates may indicate financial stress or potentially suspicious spending patterns.

**Merchants** (`merchants.csv`)
- **merchant_id**: Unique anonymized merchant identifier (format: MEXXXX)
- **merchant_group**: Broad merchant category group
