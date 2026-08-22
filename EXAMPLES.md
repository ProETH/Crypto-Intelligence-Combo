# Crypto Intelligence Combo — Examples

This file demonstrates how an AI Agent should use Crypto Intelligence Combo to classify crypto-related questions, select the correct capability, retrieve appropriate information, verify important claims, and produce a concise answer.

---

## Example 1 — Exchange Announcement

### User

What is the latest announcement from CoinW about BTC?

### Skill Behavior

- Classify as `Announcements`.
- Search the latest official CoinW announcements.
- Verify the publication date.
- Identify whether the announcement affects BTC trading, deposits, withdrawals, or another service.
- Do not rely on old announcements if a newer one exists.

### Expected Output

{
  "intent": "announcement",
  "capability": "Announcements",
  "status": "verified",
  "answer": "Summarize the latest confirmed BTC-related announcement.",
  "source_required": true
}

---

## Example 2 — Delisting Check

### User

Is CoinW going to delist TOKENX?

### Skill Behavior

- Classify as `Listings & Delistings`.
- Search official CoinW announcements.
- Check for trading suspension or delisting notices.
- Verify the effective date if a notice exists.
- Do not treat rumors as confirmation.

### Expected Output

{
  "intent": "delisting_check",
  "capability": "Listings & Delistings",
  "status": "verified_or_unverified",
  "answer": "State whether an official delisting announcement was found.",
  "effective_date": null,
  "source_required": true
}

---

## Example 3 — Spot Grid Bot

### User

What are the current conditions for Spot Grid on CoinW?

### Skill Behavior

- Classify as `Trading Bots`.
- Identify CoinW Spot Grid documentation.
- Retrieve supported assets, parameters, fees, limits, and conditions.
- Check that the information is current.
- Explain the main risks.

### Expected Output

{
  "intent": "spot_grid_conditions",
  "capability": "Trading Bots",
  "platform": "CoinW",
  "market": "Spot",
  "information_required": [
    "supported_assets",
    "grid_parameters",
    "fees",
    "limits",
    "conditions",
    "risks"
  ],
  "source_required": true
}

---

## Example 4 — Futures Funding Rate

### User

What is the current funding rate for BTC futures?

### Skill Behavior

- Classify as `Futures`.
- Identify BTC futures contract.
- Retrieve the current funding rate.
- Include the relevant funding interval when available.
- Do not interpret the funding rate as a guaranteed directional signal.

### Expected Output

{
  "intent": "funding_rate",
  "capability": "Futures",
  "asset": "BTC",
  "market": "Futures",
  "time_sensitive": true,
  "answer": "Current BTC funding rate with relevant interval and source."
}

---

## Example 5 — Futures Open Interest

### User

Is BTC open interest increasing?

### Skill Behavior

- Classify as `Futures`.
- Retrieve current and relevant historical open interest.
- Define the comparison timeframe.
- Compare OI movement with price movement.
- Avoid claiming that rising OI automatically means bullish or bearish continuation.

### Expected Output

{
  "intent": "open_interest_analysis",
  "capability": "Futures",
  "asset": "BTC",
  "metrics": [
    "open_interest",
    "price"
  ],
  "timeframe": "specified_or_recent",
  "interpretation": "context_dependent"
}

---

## Example 6 — Trading Fees

### User

How much are the current Spot trading fees?

### Skill Behavior

- Classify as `Fees & Limits`.
- Identify the exchange.
- Retrieve current maker/taker fees.
- Check VIP level if relevant.
- Distinguish standard fees from discounted fees.

### Expected Output

{
  "intent": "spot_fees",
  "capability": "Fees & Limits",
  "platform": "specified_exchange",
  "fee_type": [
    "maker",
    "taker"
  ],
  "time_sensitive": true,
  "source_required": true
}

---

## Example 7 — Withdrawal Fee

### User

How much does it cost to withdraw USDT?

### Skill Behavior

- Classify as `Fees & Limits` and `Deposits & Withdrawals`.
- Identify the exchange.
- Identify the network.
- Retrieve the current withdrawal fee and minimum withdrawal.
- Never give one fee without identifying the network when fees differ by network.

### Expected Output

{
  "intent": "withdrawal_fee",
  "capability": "Deposits & Withdrawals",
  "asset": "USDT",
  "network_required": true,
  "information_required": [
    "withdrawal_fee",
    "minimum_withdrawal"
  ]
}

---

## Example 8 — Network Compatibility

### User

Can I deposit USDT using TRC20?

### Skill Behavior

- Classify as `Wallets & Networks` and `Deposits & Withdrawals`.
- Identify the platform.
- Verify that USDT deposits support TRC20.
- Confirm that the receiving address and network match.
- Warn against sending an asset through an unsupported network.

### Expected Output

{
  "intent": "network_support",
  "capability": "Wallets & Networks",
  "asset": "USDT",
  "network": "TRC20",
  "verification_required": true
}

---

## Example 9 — P2P Market

### User

What are the best USDT P2P offers right now?

### Skill Behavior

- Classify as `P2P`.
- Identify the user's fiat currency and payment method if provided.
- Retrieve current advertisements.
- Compare price, limits, payment method, and merchant conditions.
- Make clear that advertisements can change quickly.

### Expected Output

{
  "intent": "p2p_market",
  "capability": "P2P",
  "asset": "USDT",
  "time_sensitive": true,
  "comparison_fields": [
    "price",
    "limits",
    "payment_method",
    "merchant_conditions"
  ]
}

---

## Example 10 — Earn Product

### User

What is the current APY for USDT Earn?

### Skill Behavior

- Classify as `Earn & Staking`.
- Identify the exact Earn product.
- Retrieve current APY/APR.
- Check whether the rate is fixed or variable.
- Check redemption and lock-up conditions.
- Never describe APY as guaranteed profit.

### Expected Output

{
  "intent": "earn_rate",
  "capability": "Earn & Staking",
  "asset": "USDT",
  "information_required": [
    "apy",
    "product_type",
    "lockup",
    "redemption_conditions"
  ],
  "time_sensitive": true
}

---

## Example 11 — Airdrop

### User

Is there currently an airdrop for TOKENX?

### Skill Behavior

- Classify as `Airdrops & Promotions`.
- Search official project and exchange announcements.
- Verify start/end dates.
- Verify eligibility and required actions.
- Reject unverified social-media claims.

### Expected Output

{
  "intent": "airdrop_check",
  "capability": "Airdrops & Promotions",
  "asset": "TOKENX",
  "verification": "official_source_required",
  "status": "confirmed_or_unverified"
}

---

## Example 12 — Token Research

### User

What is TOKENX and what is its utility?

### Skill Behavior

- Classify as `Token & Project Research`.
- Retrieve official documentation.
- Check token utility, supply, circulating supply, ecosystem, and supported networks.
- Separate official claims from independently verified information.

### Expected Output

{
  "intent": "token_research",
  "capability": "Token & Project Research",
  "asset": "TOKENX",
  "research_fields": [
    "utility",
    "total_supply",
    "circulating_supply",
    "tokenomics",
    "ecosystem",
    "networks"
  ]
}

---

## Example 13 — Token Unlock

### User

Does TOKENX have a token unlock soon?

### Skill Behavior

- Classify as `Token & Project Research`.
- Retrieve the unlock schedule from reliable sources.
- Verify the date and amount.
- Compare the unlock amount with circulating supply when data is available.
- Clearly label estimates.

### Expected Output

{
  "intent": "token_unlock",
  "capability": "Token & Project Research",
  "asset": "TOKENX",
  "information_required": [
    "unlock_date",
    "unlock_amount",
    "percentage_of_circulating_supply"
  ],
  "verification_required": true
}

---

## Example 14 — Market Data

### User

What is BTC's current market cap and 24-hour volume?

### Skill Behavior

- Classify as `Market Data`.
- Retrieve current BTC price, market cap, and 24-hour volume.
- Use consistent data sources.
- State that market data changes continuously.

### Expected Output

{
  "intent": "market_data",
  "capability": "Market Data",
  "asset": "BTC",
  "metrics": [
    "price",
    "market_cap",
    "24h_volume"
  ],
  "time_sensitive": true
}

---

## Example 15 — Crypto News

### User

Why did BTC suddenly drop today?

### Skill Behavior

- Classify as `Crypto News` + `Market Data`.
- Retrieve recent BTC price movement.
- Search recent market-moving news.
- Check macro, regulatory, liquidation, ETF, exchange, and major project events when relevant.
- Do not claim causation without evidence.

### Expected Output

{
  "intent": "market_move_explanation",
  "capabilities": [
    "Crypto News",
    "Market Data"
  ],
  "asset": "BTC",
  "time_sensitive": true,
  "causation": "evidence_required"
}

---

## Example 16 — Security

### User

I received a message asking for my Binance API key. Is it safe?

### Skill Behavior

- Classify as `Security`.
- Warn that API credentials are sensitive.
- Recommend not sharing private credentials.
- Recommend checking the message through official channels.
- Never request the API key from the user.

### Expected Output

{
  "intent": "security_warning",
  "capability": "Security",
  "risk_level": "high",
  "action": "do_not_share_credentials"
}

---

## Example 17 — Exchange Comparison

### User

Which is cheaper for Spot trading, CoinW or Binance?

### Skill Behavior

- Classify as `Research & Comparison` + `Fees & Limits`.
- Retrieve current standard maker/taker fees for both.
- Check whether VIP tiers materially change the comparison.
- Compare the same fee categories.
- Mention that effective cost can also depend on spread and volume.

### Expected Output

{
  "intent": "exchange_fee_comparison",
  "capabilities": [
    "Research & Comparison",
    "Fees & Limits"
  ],
  "comparison": [
    "CoinW",
    "Binance"
  ],
  "metrics": [
    "maker_fee",
    "taker_fee",
    "discounts",
    "other_costs"
  ]
}

---

## Example 18 — Bot Comparison

### User

Which is better for a sideways market: Spot Grid or DCA?

### Skill Behavior

- Classify as `Research & Comparison` + `Trading Bots`.
- Explain the mechanics of both.
- Compare sideways, trending, and strongly bearish conditions.
- Include fees and execution considerations.
- Do not claim one strategy is universally better.

### Expected Output

{
  "intent": "bot_strategy_comparison",
  "capabilities": [
    "Trading Bots",
    "Research & Comparison"
  ],
  "strategies": [
    "Spot Grid",
    "DCA"
  ],
  "comparison_fields": [
    "market_condition",
    "execution",
    "fees",
    "risk",
    "capital_usage"
  ]
}

---

## Example 19 — Current Feature Availability

### User

Does CoinW currently support Spot Reverse Grid?

### Skill Behavior

- Classify as `Trading Bots`.
- Search current CoinW documentation and announcements.
- Verify whether the feature is currently available.
- Do not assume that historical availability means current availability.

### Expected Output

{
  "intent": "feature_availability",
  "capability": "Trading Bots",
  "platform": "CoinW",
  "feature": "Spot Reverse Grid",
  "time_sensitive": true,
  "status": "confirmed_or_unknown"
}

---

## Example 20 — No Official Confirmation

### User

People are saying CoinW will delist TOKENX. Is it true?

### Skill Behavior

- Classify as `Listings & Delistings`.
- Search official announcements.
- Search recent reliable reports if necessary.
- If no official confirmation exists, explicitly state that.
- Do not convert rumors into facts.

### Expected Output

{
  "intent": "rumor_verification",
  "capability": "Listings & Delistings",
  "asset": "TOKENX",
  "official_confirmation": false,
  "answer_status": "unconfirmed"
}

---

## Example 21 — Ambiguous Question

### User

What are the fees?

### Skill Behavior

The question is incomplete.

The Agent should determine what fee is being requested instead of guessing.

Possible interpretations:

- Spot trading fee
- Futures trading fee
- Withdrawal fee
- P2P fee
- Bot fee
- VIP fee

### Expected Output

{
  "intent": "fee_question",
  "status": "needs_clarification",
  "possible_types": [
    "spot_trading",
    "futures_trading",
    "withdrawal",
    "p2p",
    "bot",
    "vip"
  ]
}

---

## Example 22 — Cross-Source Verification

### User

I saw that TOKENX has a $500M market cap. Is that correct?

### Skill Behavior

- Classify as `Market Data`.
- Retrieve current market cap from reliable sources.
- Compare sources if values differ materially.
- Check circulating supply and current price if needed.
- Explain discrepancies rather than choosing a number arbitrarily.

### Expected Output

{
  "intent": "market_data_verification",
  "capability": "Market Data",
  "asset": "TOKENX",
  "claim_to_verify": "500M market cap",
  "verification_required": true
}

---

## Example 23 — Research Before Trading

### User

I'm thinking about buying TOKENX. What should I know first?

### Skill Behavior

Use multiple capabilities:

- Token & Project Research
- Market Data
- Tokenomics
- Token Unlocks
- News
- Security

The Agent should summarize:

- What the project does
- Current market data
- Supply and unlocks
- Recent important news
- Major risks
- Information gaps

Do not automatically recommend buying.

### Expected Output

{
  "intent": "pre_trade_research",
  "capabilities": [
    "Token & Project Research",
    "Market Data",
    "Crypto News",
    "Security"
  ],
  "decision": "research_summary",
  "financial_advice": false
}

---

## Example 24 — Full Multi-Capability Request

### User

Check TOKENX. Tell me whether it is listed on CoinW, its current price, the latest announcement, upcoming unlocks, and whether there is a Spot Grid bot for it.

### Skill Behavior

Break the request into independent tasks:

TOKENX
├── Listing status
├── Current market data
├── Latest announcement
├── Token unlocks
└── Spot Grid availability

Use the appropriate capability for each task.

### Expected Output

{
  "intent": "multi_research",
  "asset": "TOKENX",
  "tasks": [
    {
      "capability": "Listings & Delistings",
      "task": "listing_status"
    },
    {
      "capability": "Market Data",
      "task": "current_price"
    },
    {
      "capability": "Announcements",
      "task": "latest_announcement"
    },
    {
      "capability": "Token & Project Research",
      "task": "upcoming_unlocks"
    },
    {
      "capability": "Trading Bots",
      "task": "spot_grid_availability"
    }
  ],
  "verification_required": true
}

---

## Example 25 — Unknown Information

### User

What will CoinW's trading fees be next month?

### Skill Behavior

- Classify as `Fees & Limits`.
- Determine whether an official future fee schedule exists.
- If no confirmed schedule exists, do not predict the fee as fact.

### Expected Output

{
  "intent": "future_fee_question",
  "capability": "Fees & Limits",
  "status": "future_information",
  "answer": "Only provide a confirmed future fee if an official source publishes it."
}

---

# Example Decision Matrix

| User Request | Capability |
|---|---|
| Latest CoinW announcement | Announcements |
| Is TOKENX being delisted? | Listings & Delistings |
| Current BTC Spot price | Market Data |
| BTC funding rate | Futures |
| BTC open interest | Futures |
| Spot Grid conditions | Trading Bots |
| Reverse Grid availability | Trading Bots |
| Spot trading fees | Fees & Limits |
| USDT withdrawal fee | Deposits & Withdrawals |
| Is TRC20 supported? | Wallets & Networks |
| Best USDT P2P offer | P2P |
| Current Earn APY | Earn & Staking |
| Current airdrop | Airdrops & Promotions |
| TOKENX tokenomics | Token & Project Research |
| TOKENX unlock | Token & Project Research |
| Why did BTC fall? | Crypto News + Market Data |
| Is this API-key request safe? | Security |
| CoinW vs Binance fees | Research & Comparison |
| Grid vs DCA | Research & Comparison |

---

# Expected Agent Principles

The examples demonstrate five core behaviors:

1. Classify before searching.
2. Use the correct capability for the question.
3. Prefer authoritative and current sources.
4. Verify important information before presenting it as fact.
5. Never invent information that cannot be verified.
