# Bookmaker Odds

This feature literally robs sportsbooks.

**Bookmaker Odds** compares Polymarket prices against real sportsbook odds from up to 19 books — showing you the edge without opening a single sportsbook site. If the books think an outcome is more likely than Polymarket does, you've found a mispricing.

![Bookmaker Odds Comparison](https://raw.githubusercontent.com/polymarkethelper/gitbook/main/.gitbook/assets/bookmaker-odds.png)

---

## What the Panel Shows

### Poly vs Books vs Edge

For each market outcome, the panel shows three columns:

| Column | Description |
|---|---|
| **Poly** | Current Polymarket implied probability (market price) |
| **Books** | Sportsbook implied probability aggregated from up to 9 major books |
| **Edge** | Difference: Books% − Poly% |

**Positive edge** (+) = Polymarket is underpriced vs books → potential value buying YES  
**Negative edge** (−) = Polymarket is overpriced vs books → potential value buying NO

### h2h 3-Way Markets
For football (soccer) and other 3-outcome markets, all three outcomes are shown:
- **Win (YES)** — home team or named team wins
- **Draw** — match ends level
- **Loss** — away team or opposing side wins

Each row displays the full Poly / Books / Edge breakdown.

### Sportsbooks Included

Up to 19 books are aggregated: Pinnacle, DraftKings, FanDuel, BetMGM, William Hill, Betfair, Matchbook, Unibet, Betsson, BetOnline, Bet365, Caesars, PointsBet, Bovada, MyBookie, BetRivers, WynnBet, Circa Sports. The panel shows how many books are available for each specific market.

---

## How to Use It

### Finding Mispriced Markets

1. Open any sports market on Polymarket
2. Check the Edge column — look for outcomes where **Books > Poly** (positive edge)
3. A consistent positive edge across multiple outcomes in the same market means Polymarket is systematically underpriced on that side

### The Core Inefficiency

Sportsbooks price events with significant resources: full-time traders, proprietary models, and sharp bettor action. When their consensus probability differs from Polymarket's market price, one of them is wrong — and historically, the sharp money in sportsbooks is often the more informed signal.

This doesn't guarantee profit, but it gives you a data-driven basis for identifying mispricings.

### Example Trade Setup

```
Real Madrid vs Oviedo — h2h 3 way:
Real Madrid Win:  Poly 77.5%  Books 77.7%  Edge -0.2%  → Fairly priced
Draw:             Poly 14.5%  Books 14.3%  Edge +0.2%  → Slight value on Draw
Oviedo Win:       Poly 7.5%   Books 8.1%   Edge -0.6%  → Books see Oviedo as more likely
```

In this example, the books price Oviedo's win at 8.1% vs Polymarket's 7.5% — a 0.6% edge suggesting Oviedo is underpriced on Polymarket.

---

## Limitations

{% hint style="warning" %}
Sportsbooks build a margin (vig) into their prices. The "Books" probability shown is **vig-adjusted** — but small edges (under 1%) may be within the margin of error. Focus on larger edges for higher-conviction trades.
{% endhint %}

- Sportsbook lines move quickly — edges can appear and disappear in minutes
- Books may have different information than Polymarket traders (team news, injuries, lineup changes)
- Polymarket sometimes prices non-win outcomes differently because the market structure differs from traditional betting

---

## Markets Where This Panel Activates

- Soccer / football match winner markets
- NBA, NFL, MLB, NHL game winner markets
- UFC fight outcome markets
- Any sports market where sportsbook odds are available for comparison
