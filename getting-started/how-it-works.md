# How It Works

## Technical Overview

PolyHelper is a **browser extension** built on the Chrome Extensions (Manifest V3) standard. It works by injecting lightweight UI components into Polymarket pages — adding new informational panels to the existing interface without altering or replacing any native functionality.

---

## Architecture

<div style="font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif;max-width:580px;margin:0 auto;padding:8px">

  <div style="background:#eef2ff;border:1.5px solid #c7d2fe;border-radius:12px;padding:14px 20px;display:flex;align-items:center;gap:10px">
    <span style="font-size:20px">🌐</span>
    <div>
      <div style="font-weight:700;color:#3730a3;font-size:14px">polymarket.com</div>
      <div style="color:#6366f1;font-size:11px">Prediction market platform</div>
    </div>
  </div>

  <div style="text-align:center;color:#a5b4fc;font-size:22px;line-height:1;padding:6px 0">↓</div>

  <div style="background:#0f172a;border-radius:16px;padding:20px;border:1px solid #1e293b">
    <div style="font-size:10px;text-transform:uppercase;letter-spacing:1.5px;color:#475569;margin-bottom:14px;font-weight:600">PolyHelper Extension</div>

    <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:10px">
      <div style="background:#1e293b;border-radius:10px;padding:14px;border:1px solid #334155">
        <div style="font-size:12px;font-weight:700;color:#60a5fa;margin-bottom:6px">⚡ Content Scripts</div>
        <div style="font-size:11px;color:#64748b;line-height:1.7">Detect market type<br>Inject sidebar panels</div>
      </div>
      <div style="background:#1e293b;border-radius:10px;padding:14px;border:1px solid #334155">
        <div style="font-size:12px;font-weight:700;color:#60a5fa;margin-bottom:6px">⚙️ Background Worker</div>
        <div style="font-size:11px;color:#64748b;line-height:1.7">Fetch data from APIs<br>Cache &amp; refresh data</div>
      </div>
    </div>

    <div style="background:#1e293b;border-radius:10px;padding:14px;border:1px solid #334155">
      <div style="font-size:12px;font-weight:700;color:#60a5fa;margin-bottom:12px">📡 Data Sources</div>
      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:6px">
        <div style="background:#0f172a;border-radius:7px;padding:8px;text-align:center;font-size:10px;color:#94a3b8;border:1px solid #1e293b">₿ Crypto feeds</div>
        <div style="background:#0f172a;border-radius:7px;padding:8px;text-align:center;font-size:10px;color:#94a3b8;border:1px solid #1e293b">🏆 Sports APIs</div>
        <div style="background:#0f172a;border-radius:7px;padding:8px;text-align:center;font-size:10px;color:#94a3b8;border:1px solid #1e293b">📰 News / X</div>
        <div style="background:#0f172a;border-radius:7px;padding:8px;text-align:center;font-size:10px;color:#94a3b8;border:1px solid #1e293b">📊 Polling data</div>
        <div style="background:#0f172a;border-radius:7px;padding:8px;text-align:center;font-size:10px;color:#94a3b8;border:1px solid #1e293b">📈 Macro econ</div>
        <div style="background:#0f172a;border-radius:7px;padding:8px;text-align:center;font-size:10px;color:#94a3b8;border:1px solid #1e293b">🌍 Geopolitics</div>
      </div>
    </div>
  </div>

  <div style="text-align:center;color:#a5b4fc;font-size:22px;line-height:1;padding:6px 0">↓</div>

  <div style="background:linear-gradient(135deg,#3b82f6 0%,#4f46e5 100%);border-radius:12px;padding:16px 20px;display:flex;align-items:center;gap:10px">
    <span style="font-size:20px">✅</span>
    <div>
      <div style="font-weight:700;color:#fff;font-size:14px">Enhanced Polymarket UI</div>
      <div style="color:#bfdbfe;font-size:11px">Your panels · Your data · Your edge</div>
    </div>
  </div>

</div>

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

## Customization — Settings Panel

Don't need a specific tool? You can turn off any feature individually. PolyHelper is fully customizable.

**How to open Settings:**
Look for the **gear icon ⚙️** in the right-side tab bar of the extension — click it to open the Settings panel.

<figure><img src="../.gitbook/assets/settings-panel.png" alt="PolyHelper Settings Panel"><figcaption>Settings panel — toggle any feature on or off</figcaption></figure>

Features are organized into three categories:

**Market Data**
| Feature | Description |
|---|---|
| Charts | Real-time charts from resolution source |
| LP Rewards | Daily reward rates on market rows |
| Top Holders PnL | PnL breakdown for top holders |
| Crypto Context | Market data, derivatives, ETFs for crypto events |
| Stock Context | Company analytics, earnings, holdings for stock events |
| Weather Context | Current conditions & forecast for weather events |
| Macro Intel | Economic indicators & release dates for macro events |

**Social**
| Feature | Description |
|---|---|
| X Feed | Twitter/X feed on event pages |
| X Analytics | Author feed & posting analytics for tweet markets |
| Comments Filter | Filter comments by holder positions |
| Trader Tracker | Follow traders, group them, and watch their live activity |

**Intel**
| Feature | Description |
|---|---|
| Sports Intel | ESPN standings & recent games |
| Bookmaker Odds | Live Pinnacle/Betfair odds vs Polymarket prices |
| Pentagon Pizza Index | DOUGHCON indicator (OSINT) |
| Conflict Monitor | NASA satellite fire detection for conflict zones |
| Frontline Maps | ISW conflict maps for territorial markets |
| UFC Context | Fighter profiles, records, rankings |
| Esports Context | LoL, Valorant, Dota 2 standings & teams |
| MrBeast Intel | View velocity & attention signal for YouTube events |
| AI Arena | Chatbot Arena rankings & benchmarks for AI model markets |
| Box Office | Daily grosses, projections & comparables for movie markets |
| Polls Intel | Polling data vs market prices for elections |

**Tools**
| Feature | Description |
|---|---|
| Bonds Scanner | High-probability market yield scanner |
| Update Notifier | Notifies when a newer version is on the store |
| Profile Enhancer | Extended trader analytics on profile pages |

Every toggle saves instantly — no need to reload the page.

{% hint style="info" %}
Not sure which tools you need? Leave everything on by default and turn off what you don't use as you go.
{% endhint %}

---

## Next Steps

Now that you understand how PolyHelper works, explore all the available analytics tools:

- [Overview of all features →](../features/overview.md)
- [Crypto Context Panel →](../features/crypto-context.md)
- [Earn reward points →](../rewards/program.md)
