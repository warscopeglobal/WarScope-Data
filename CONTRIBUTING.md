# Contributing to WarScope Data

Thank you for helping build the most accurate open military intelligence database. Every contribution matters — even a single country's data helps thousands of readers understand global conflicts better.

---

## Two Ways to Contribute

### 🟢 Option 1 — No GitHub Required (Recommended for most people)

Visit **[warscopeglobal.com/contribute](https://warscopeglobal.com/contribute)**

Fill in a simple form with your country's data in plain language. No coding, no GitHub, no formatting required. We'll handle everything and add your data within 7 days.

### 🔵 Option 2 — GitHub Pull Request (For developers)

Follow the steps below.

---

## GitHub Contribution Steps

### Step 1 — Fork the Repository

Click the **Fork** button at the top right of this page. This creates your own copy of the repository.

### Step 2 — Clone Your Fork

```bash
git clone https://github.com/YOUR-USERNAME/warscope-data.git
cd warscope-data
```

### Step 3 — Find Your Data Sources

**You must cite a source for every data point.** See [`SOURCES.md`](SOURCES.md) for the approved list. The most useful free sources are:

- [SIPRI](https://sipri.org) — arms transfers and military spending
- [UCDP](https://ucdp.uu.se) — conflict history
- [CIA World Factbook](https://cia.gov/the-world-factbook/) — personnel and branches
- Government defence ministry websites — official figures

### Step 4 — Add Your Data

Open the relevant `.js` file. Copy the template from [`TEMPLATES.md`](TEMPLATES.md) or from the `templates/` folder. Add your country's entry following the **exact same format** as existing entries.

**Important formatting rules:**
- Do not change the file's export structure — only add entries to existing arrays/objects
- Use ISO 3166-1 alpha-3 country codes (e.g. `NGA` for Nigeria, `THA` for Thailand)
- Keep all strings in English unless noted otherwise
- Mark estimates clearly: `'~100,000'` or add a note in the `notes` field
- Include the source in the entry's `source` field

### Step 5 — Commit and Push

```bash
git add .
git commit -m "Add Nigeria army units data (Source: Nigerian Army website + IISS 2025)"
git push origin main
```

### Step 6 — Open a Pull Request

Go to your fork on GitHub and click **"Contribute" → "Open Pull Request"**.

**In your PR description, include:**
- Which country you are adding
- Which dataset(s) you are updating
- Your source URL or citation for each figure
- Any caveats (e.g. "personnel figures are estimates from 2024")

### Step 7 — Review

We review all PRs within 7 days. We may ask for clarification or source verification. Once merged, your name is added to [`CONTRIBUTORS.md`](CONTRIBUTORS.md).

---

## Data Quality Rules

### ✅ We Accept

| Type | Examples |
|------|---------|
| Government defence ministry websites | army.mil.ng, mod.gov.uk, defense.gov |
| Academic databases | SIPRI, UCDP, FAS Nuclear Notebook, ACLED |
| Official international sources | CIA World Factbook, UN reports, OFAC, EU sanctions |
| Manufacturer specifications | Official datasheets for vehicles, aircraft, weapons |
| News from major outlets | Reuters, AP, BBC, Al Jazeera (for recent events) |
| IISS Military Balance | Cite page number — do not copy text verbatim |
| Personal knowledge | If you served or work in defence — public information only |

### ❌ We Do Not Accept

| Type | Reason |
|------|---------|
| Classified or leaked documents | Legal risk, unverifiable |
| Social media posts, forums, Reddit | Unreliable, unverifiable |
| Data with no source at all | Cannot verify accuracy |
| Paywalled content copied verbatim | Copyright violation |
| Information endangering personnel | Safety risk |
| Estimates without noting they are estimates | Misleading |

---

## ISO 3166-1 Alpha-3 Country Codes

Use these codes in the `iso3` field. Common ones:

| Country | Code | Country | Code | Country | Code |
|---------|------|---------|------|---------|------|
| Afghanistan | AFG | Germany | DEU | Pakistan | PAK |
| Algeria | DZA | Ghana | GHA | Philippines | PHL |
| Angola | AGO | Greece | GRC | Poland | POL |
| Argentina | ARG | India | IND | Portugal | PRT |
| Australia | AUS | Indonesia | IDN | Romania | ROU |
| Austria | AUT | Iran | IRN | Russia | RUS |
| Bangladesh | BGD | Iraq | IRQ | Saudi Arabia | SAU |
| Belgium | BEL | Israel | ISR | Singapore | SGP |
| Brazil | BRA | Italy | ITA | Somalia | SOM |
| Bulgaria | BGR | Japan | JPN | South Africa | ZAF |
| Canada | CAN | Jordan | JOR | South Korea | KOR |
| Chile | CHL | Kenya | KEN | Spain | ESP |
| China | CHN | Libya | LBY | Sudan | SDN |
| Colombia | COL | Malaysia | MYS | Sweden | SWE |
| Czech Republic | CZE | Mexico | MEX | Syria | SYR |
| Denmark | DNK | Morocco | MAR | Taiwan | TWN |
| DRC | COD | Myanmar | MMR | Thailand | THA |
| Egypt | EGY | Netherlands | NLD | Turkey | TUR |
| Ethiopia | ETH | Nigeria | NGA | UAE | ARE |
| Finland | FIN | North Korea | PRK | Ukraine | UKR |
| France | FRA | Norway | NOR | United Kingdom | GBR |
| Georgia | GEO | Oman | OMN | United States | USA |
| | | | | Vietnam | VNM |

Full list: [ISO 3166-1 on Wikipedia](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3)

---

## What Makes a Good Contribution

**Good PR title:**
> Add Thailand army units, air force and navy data — Source: Royal Thai Army website + IISS 2025

**Good PR description:**
> Adding Thailand military data to army-units-db.js
>
> **Sources:**
> - Personnel figures: Royal Thai Armed Forces official website (rta.mi.th) — accessed March 2026
> - Equipment: IISS Military Balance 2025, p.287
> - Unit structure: Jane's World Armies (citing from secondary sources only)
>
> **Notes:**
> - Reserve figures are approximate — official numbers not publicly released
> - Special Forces unit names translated from Thai — Thai names included in comments

**Good data entry:**
```js
{
  country: 'Thailand',
  iso3: 'THA',
  branch: 'army',
  name: 'Royal Thai Army',
  personnel: { active: 245000, reserve: 200000 },
  hq: 'Bangkok',
  majorUnits: ['First Army', 'Second Army', 'Third Army', 'Fourth Army'],
  equipment: { tanks: 722, apcs: 1100, artillery: 700 },
  source: 'Royal Thai Army rta.mi.th + IISS Military Balance 2025 p.287',
  lastVerified: '2026-03',
}
```

---

## Questions?

- Open a **GitHub Issue** with the `question` label
- Email us at **contact@warscopeglobal.com**
- Use the no-code form at **[warscopeglobal.com/contribute](https://warscopeglobal.com/contribute)**
