# Rewards Pool Calculator

The **Rewards Pool Calculator** helps liquidity providers on Polymarket evaluate LP rewards opportunities across all market outcome brackets — including **competition level indicators** that show at a glance where the edge is.

![Rewards Pool Calculator](https://raw.githubusercontent.com/polymarkethelper/gitbook/main/.gitbook/assets/rewards-calculator.png)

---

## Background: Polymarket LP Rewards

Polymarket runs a **liquidity provider (LP) rewards program** that incentivizes traders to place limit orders. LPs earn a share of a daily rewards pool proportional to:
1. The amount of liquidity provided
2. How close to the current price their orders are placed
3. How long their orders remain active

---

## What the Panel Shows

### Competition Level Indicators

Each market outcome bracket is color-coded to show how competitive the LP environment is:

| Color | Meaning |
|---|---|
| 🟢 **Green** | Low competition — fewer LPs on this side, easier to earn rewards |
| 🔴 **Red** | High competition — crowded side, harder to capture a meaningful share |

This color system lets you instantly spot where the best LP opportunities are without manually calculating pool share.

### Per-Bracket Data

For each outcome bracket (e.g., >$800M, >$1B, >$1.5B):

| Field | Description |
|---|---|
| **Current probability %** | Polymarket's current price for this outcome |
| **% change** | Recent movement (▲ = price rising) |
| **Daily rewards** | Total rewards pool allocated per day (e.g., $800/day) |
| **Sponsored** | Additional sponsored rewards if applicable |
| **Remaining** | How much of the reward pool is still unclaimed (~$422 left) |
| **Buy Yes / Buy No** | Current bid prices with competition color indicator |

---

## How to Use It

**Step 1:** Look for **green brackets** — these are the lowest-competition LP opportunities right now

**Step 2:** Check the **daily rewards** and **remaining pool** — higher rewards + more remaining = better opportunity

**Step 3:** Consider the **probability** — providing liquidity near 99¢ on a near-certain outcome is low risk but also low edge; brackets with 40–60% probability carry more adverse selection risk

**Step 4:** Place limit orders in Polymarket's order book at your chosen bracket

---

## Understanding Competition & Risk

| Situation | What It Means |
|---|---|
| Green YES + high daily rewards | Best LP opportunity — low competition, meaningful payout |
| Red on both sides | Crowded market — LP earnings will be split among many providers |
| High remaining pool | Earlier in the reward period — more to earn |
| Near-zero remaining | Pool almost exhausted for this period |

---

## Trade-offs for LP Providers

| Tighter to market price | Further from market price |
|---|---|
| Higher rewards weight | Lower rewards weight |
| More adverse selection risk | Less exposure to informed traders |
| Orders fill more often | Orders fill less often |

{% hint style="info" %}
LP rewards are separate from PolyHelper's own [points & airdrop program](../rewards/program.md). You can earn both simultaneously.
{% endhint %}

---

## Markets Where This Feature Activates

Available on all Polymarket markets that have an active LP rewards program.
