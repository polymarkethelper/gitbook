# How It Works

## Technical Overview

PolyHelper is a **browser extension** built on the Chrome Extensions (Manifest V3) standard. It works by injecting lightweight UI components into Polymarket pages — adding new informational panels to the existing interface without altering or replacing any native functionality.

---

## Architecture

```
Polymarket Page (polymarket.com)
         │
         ▼
  PolyHelper Extension
  ┌─────────────────────────────────────┐
  │                                     │
  │   Content Scripts                   │
  │   └─ Detect current market type     │
  │   └─ Inject sidebar panels          │
  │                                     │
  │   Background Service Worker         │
  │   └─ Fetch data from APIs           │
  │   └─ Cache and refresh data         │
  │                                     │
  │   Data Sources                      │
  │   └─ Crypto price feeds             │
  │   └─ Sports data APIs               │
  │   └─ News aggregation (X/Twitter)   │
  │   └─ Polling averages               │
  │   └─ Macro economic indicators      │
  │   └─ Geopolitical intelligence      │
  │                                     │
  └─────────────────────────────────────┘
         │
         ▼
  Enhanced Polymarket UI
  (Your panels, your data, your edge)
```

---

## Smart Market Detection

PolyHelper automatically detects the **type of market** you're viewing and loads the relevant data panels. You don't need to configure anything manually.

| Market Type | Auto-loaded Panels |
|---|---|
| Crypto / Token | Crypto Context Panel, Price Charts, Live News |
| Sports (NBA, NFL, etc.) | Sports Intel, Live News |
| Politics / Elections | Polls Intel, Live News, Top Holders PnL |
| Stocks / Equities | Stocks Context, Macro Intel |
| Geopolitics / Military | Pentagon Tracker, Conflict Radar, Military Maps |
| AI / Technology | AI Arena, Live News |
| Entertainment / Box Office | Box Office Projections |
| Weather | Weather Forecast |
| Bonds / Finance | Bonds Tracker, Macro Intel |

---

## Data Flow

1. **You open a Polymarket market page**
2. PolyHelper's content script detects the market category
3. Relevant panels are injected into the sidebar
4. The background service worker fetches live data from multiple APIs
5. Data is rendered in real-time inside the panels
6. Panels refresh automatically as new data becomes available

---

## Privacy & Security

PolyHelper is designed with user privacy as a priority:

- **No wallet access** — the extension never reads your private keys or seed phrase
- **No trade execution** — PolyHelper is purely informational; it cannot place, modify, or cancel orders
- **No personal data collection** — usage data is not sold or shared with third parties
- **Open permissions** — the extension only requests the permissions it needs to function on Polymarket

{% hint style="warning" %}
PolyHelper will **never** ask for your wallet's seed phrase, private key, or password. If you see such a request, it is not from PolyHelper.
{% endhint %}

---

## Panel System

Each panel in PolyHelper is an independent module. You can:

- **Expand / collapse** individual panels
- **Scroll** through panel content independently
- **Interact** with some panels (e.g., filter comments, view detailed charts)

Panels are loaded lazily — only the panels relevant to the current market are fetched and rendered, keeping performance impact minimal.

---

## Keeping Data Fresh

PolyHelper uses a smart caching and refresh system:

| Data Type | Refresh Rate |
|---|---|
| Crypto prices | Every 30 seconds |
| Sports scores | Live / every 60 seconds |
| News feed | Every 2–5 minutes |
| Poll averages | Every 6–12 hours |
| Economic indicators | Daily |
| Military maps | Every few hours |

---

## Next Steps

Now that you understand how PolyHelper works, explore all the available analytics tools:

- [Overview of all features →](../features/overview.md)
- [Crypto Context Panel →](../features/crypto-context.md)
- [Earn reward points →](../rewards/program.md)
