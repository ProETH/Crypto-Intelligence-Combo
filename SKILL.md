# Crypto Intelligence Combo

## Purpose

Crypto Intelligence Combo is a modular AI Skill designed to help an AI Agent retrieve, verify, explain, compare, and organize cryptocurrency and exchange information.

The Skill does not depend on one exchange or one trading strategy. It identifies the user's request, selects the appropriate capability, retrieves the required information from suitable sources, verifies important facts, and returns a clear answer.

---

## Core Workflow

For every request:

1. Identify the user's intent.
2. Classify the request into the appropriate capability.
3. Identify the required data.
4. Select the most relevant and authoritative source.
5. Prefer official sources for exchange rules, announcements, fees, product conditions, and account policies.
6. Check the publication or update date when information can change.
7. Cross-check important or potentially sensitive information when possible.
8. Separate confirmed facts from analysis, estimates, and assumptions.
9. Do not invent missing information.
10. Return a concise, useful, and explainable answer.

---

# Capabilities

## 1. Announcements

Use for:

- Exchange announcements
- New product announcements
- Trading changes
- Maintenance
- Promotions
- Token-related announcements
- Network updates
- Policy changes

### Required behavior

Prefer the official announcement source.

Report:

- What changed
- Affected asset/product
- Effective date
- Important conditions
- Whether the information is confirmed

---

## 2. Listings & Delistings

Use for:

- New token listings
- Delistings
- Trading-pair changes
- Trading suspension
- Deposit suspension
- Withdrawal suspension

### Required behavior

Do not infer a delisting from rumors or price movement.

Look for an official announcement and distinguish:

- Confirmed
- Announced but not effective
- Rumored/unverified
- No official announcement found

---

## 3. Spot Trading

Use for:

- Spot prices
- Trading pairs
- Buy/sell information
- Open orders
- Order types
- Trading rules
- Minimum order requirements
- Spot trading conditions

### Required behavior

When answering a current trading-condition question, prioritize current exchange documentation or current market data.

Clearly distinguish market data from exchange rules.

---

## 4. Futures

Use for:

- Futures prices
- Funding rates
- Open interest
- Long/short ratios
- Futures trading rules
- Contract specifications
- Leverage information
- Margin requirements

### Required behavior

Identify:

- Contract type
- Trading pair
- Relevant timeframe
- Current versus historical information

Do not treat funding rate, open interest, or long/short ratios as guaranteed predictions of price direction.

---

## 5. Trading Bots

Use for:

- Spot Grid
- Futures Grid
- DCA bots
- Arbitrage bots
- Reverse Grid
- Other automated trading products

### Required behavior

When asked about a bot, explain:

- How it works
- Supported market
- Entry/exit logic
- Required conditions
- Fees
- Limits
- Main risks
- Important configuration parameters

Do not assume that a feature available on one platform is available on another platform.

---

## 6. Fees & Limits

Use for:

- Trading fees
- Maker/taker fees
- Withdrawal fees
- Deposit requirements
- Minimum order size
- Maximum order size
- P2P fees
- Bot fees
- VIP discounts

### Required behavior

Fees and limits are dynamic.

Always prefer the latest official information.

When calculating profitability, consider:

- Trading fees
- Spread
- Estimated slippage
- Withdrawal fees when relevant
- Other known costs

Never describe a trade as profitable based only on price difference when execution costs are unknown.

---

## 7. Deposits & Withdrawals

Use for:

- Supported deposit networks
- Withdrawal networks
- Minimum withdrawal
- Withdrawal fees
- Deposit confirmations
- Suspended networks
- Deposit/withdrawal troubleshooting

### Required behavior

Verify the exact:

- Asset
- Network
- Platform
- Deposit/withdrawal direction

Never assume that two networks with similar names are interchangeable.

---

## 8. P2P

Use for:

- P2P market overview
- Payment methods
- Advertisements
- Merchant information
- P2P order conditions
- P2P fees
- Buying/selling through P2P

### Required behavior

Explain the difference between:

- Advertised price
- Actual executable price
- Payment method
- Limits
- Merchant conditions

Never assume that a P2P advertisement guarantees availability.

---

## 9. Earn & Staking

Use for:

- Savings
- Staking
- Yield products
- Flexible products
- Locked products
- Auto-subscription
- Redemption
- Rewards

### Required behavior

Clearly distinguish:

- Estimated APY/APR
- Fixed versus variable rewards
- Lock-up period
- Redemption conditions
- Eligibility requirements

Do not present estimated yield as guaranteed profit.

---

## 10. Airdrops & Promotions

Use for:

- Airdrops
- Campaigns
- Trading competitions
- Rewards
- Referral promotions
- Token giveaways

### Required behavior

Verify:

- Start date
- End date
- Eligibility
- Required actions
- Reward amount
- Distribution method
- Geographic restrictions when applicable

Prefer official campaign information.

---

## 11. Wallets & Networks

Use for:

- Wallet compatibility
- Supported networks
- Token contracts
- Network fees
- Deposits
- Withdrawals
- Contract addresses

### Required behavior

Always verify the network and contract address before presenting them as correct.

Do not assume that the same token symbol represents the same asset across different networks.

---

## 12. Market Data

Use for:

- Current price
- Market capitalization
- Trading volume
- Price changes
- Liquidity
- Volatility
- Market comparisons

### Required behavior

Identify:

- Asset
- Market
- Quote currency
- Timeframe

When comparing assets, use consistent timeframes and metrics.

---

## 13. Token & Project Research

Use for:

- What a token does
- Token utility
- Supply
- Circulating supply
- Tokenomics
- Unlocks
- Ecosystem
- Partnerships
- Supported networks
- Project fundamentals

### Required behavior

Separate:

- Official project claims
- Verified market data
- Third-party information
- Analyst interpretation

Do not present promotional claims as independently verified facts.

---

## 14. Crypto News

Use for:

- Latest crypto news
- Market-moving events
- Project news
- Regulatory news
- Exchange news
- Macro events affecting crypto

### Required behavior

Prioritize recent and reliable sources.

For breaking news:

1. Verify the publication date.
2. Check the original source when possible.
3. Cross-check important claims.
4. Distinguish confirmed news from rumors.

Do not treat social-media speculation as confirmed information.

---

## 15. Security

Use for:

- Account security
- Phishing
- Scam warnings
- Wallet safety
- Suspicious transactions
- API security
- 2FA
- Withdrawal protection

### Required behavior

Prioritize official security documentation.

Never request or expose:

- Passwords
- Private keys
- Seed phrases
- API secrets
- Authentication codes

If a user provides sensitive credentials, advise them not to share them.

---

## 16. Research & Comparison

Use for:

- Exchange comparisons
- Token comparisons
- Product comparisons
- Bot comparisons
- Network comparisons
- Fee comparisons
- Feature comparisons

### Required behavior

Define the comparison criteria before judging.

Use consistent metrics.

Clearly distinguish facts from subjective evaluation.

When information is incomplete, say so.

---

# Source Selection Rules

Use the source that best matches the question.

### Exchange rules and products

Prefer:

1. Official exchange documentation
2. Official announcements
3. Official support pages

### Blockchain information

Prefer:

1. Blockchain explorers
2. Official project documentation
3. Reliable blockchain data providers

### Market information

Prefer:

1. Reliable market-data providers
2. Exchange market data
3. Multiple sources when important

### News

Prefer:

1. Original announcement
2. Reputable news source
3. Secondary reporting only when necessary

---

# Freshness Rules

Information should be treated as time-sensitive when it involves:

- Fees
- Trading limits
- Product availability
- Bot conditions
- Listings
- Delistings
- Promotions
- P2P advertisements
- Interest rates
- Staking rewards
- Network support
- Exchange policies

For these topics, prefer the newest reliable source.

If the date cannot be verified, explicitly state that the information may have changed.

---

# Verification Rules

For important claims, use the following hierarchy:

### Level 1 — Confirmed

Directly supported by an authoritative source.

### Level 2 — Cross-checked

Supported by multiple reliable sources.

### Level 3 — Reported

Reported by a credible third party but not independently confirmed.

### Level 4 — Speculative

Rumor, interpretation, or unverified claim.

Never present Level 3 or Level 4 information as confirmed fact.

---

# Answer Format

When appropriate, structure answers as:

```text
Answer:
[Direct answer]

Details:
[Important supporting information]

Conditions:
[Relevant requirements or limitations]

Risk:
[Important risks or uncertainty]

Source:
[Relevant source]

For simple questions, do not unnecessarily use the full structure.


---

Current Information Rule

When the user asks:

"today"

"now"

"currently"

"latest"

"recent"

"is it available"

"did they announce"

"has it been delisted"

"what are the current fees"


the Agent should retrieve current information instead of relying only on stored knowledge.


---

No-Hallucination Rule

If the required information cannot be verified:

Do not guess.

Instead say:

"I could not verify this."

"No official announcement was found."

"The available information is outdated."

"This requires checking the current platform data."


Never create fake announcements, fees, limits, dates, token addresses, or platform features.


---

Platform-Agnostic Design

Crypto Intelligence Combo should not be permanently tied to one exchange.




Always identify the platform specified by the user before retrieving platform-specific information.


---

Agent Decision Logic

The Agent should follow:

USER QUESTION
      ↓
INTENT IDENTIFICATION
      ↓
CAPABILITY SELECTION
      ↓
DATA REQUIREMENTS
      ↓
SOURCE SELECTION
      ↓
DATA RETRIEVAL
      ↓
DATE / FRESHNESS CHECK
      ↓
VERIFICATION
      ↓
ANALYSIS
      ↓
CONCISE ANSWER

If verification fails:

VERIFICATION FAILED
      ↓
DO NOT GUESS
      ↓
EXPLAIN WHAT IS UNKNOWN


---

Important Principles

1. Accuracy is more important than completeness.


2. Current information is preferred for changing conditions.


3. Official sources are preferred for platform-specific rules.


4. Important claims should be cross-checked when possible.


5. The Agent must distinguish facts from analysis.


6. The Agent must not invent missing data.


7. The Agent should answer directly before adding unnecessary detail.


8. Platform-specific information must never be assumed.


9. Financial information must not be presented as guaranteed returns.


10. The Skill is designed to assist an AI Agent, not replace human judgment.




---

Risk Notice

Cryptocurrency markets and exchange policies change rapidly.

Information about prices, fees, limits, products, promotions, trading rules, and network support may become outdated.

This Skill provides research and information assistance only and does not constitute financial advice.

Users should independently verify important trading, withdrawal, security, and financial decisions using the latest official information.
