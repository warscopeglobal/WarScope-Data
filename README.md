# WarScope Data

> The open military intelligence database powering [warscopeglobal.com](https://warscopeglobal.com)

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Data Coverage](https://img.shields.io/badge/countries%20covered-54%2F195-orange.svg)](https://warscopeglobal.com/contribute)

---

## What is this?

WarScope is an open-source military intelligence platform. This repository contains all the data files that power the site — army units, military vehicles, sanctions, arms transfers, conflict timelines and more.

**The database is community-maintained.** We are currently missing data for 140+ countries. If you know your country's armed forces, equipment or conflict history, you can contribute it here.

---

## 📊 Current Coverage

| Dataset | File | Countries Covered | Priority |
|---------|------|:-----------------:|----------|
| Army Units & Order of Battle | `army-units-db.js` | 54 / 195 | 🔴 HIGH |
| Military Vehicles & Equipment | `vehicles-db.js` | 25 / 195 | 🔴 HIGH |
| Sanctions & Arms Embargoes | `sanctions-data.js` | 19 / 195 | 🟡 MEDIUM |
| Arms Transfers | `arms-trade-data.js` | 40 / 195 | 🟡 MEDIUM |
| Conflict Timeline | `timeline-data.js` | 120 / 195 | 🟡 MEDIUM |
| Alliances | `alliance-data.js` | 195 / 195 | ✅ COMPLETE |
| Nuclear Arsenal | `nuclear-data.js` | 9 / 9 | ✅ COMPLETE |

---

## 🤝 How to Contribute

### Not a developer?
Visit **[warscopeglobal.com/contribute](https://warscopeglobal.com/contribute)** — fill in a simple form with your country's data in plain English. No GitHub or coding skills needed. We'll add it for you within 7 days.

### Developer / GitHub user?
1. **Fork** this repository
2. Add or update data in the relevant `.js` file following the format in [`TEMPLATES.md`](TEMPLATES.md)
3. Cite your sources in the Pull Request description
4. Submit a **Pull Request** against `main`
5. We review within 7 days — accepted contributors are listed in [`CONTRIBUTORS.md`](CONTRIBUTORS.md)

Read the full guide in [`CONTRIBUTING.md`](CONTRIBUTING.md).

---

## 📁 Repository Structure

```
warscope-data/
├── army-units-db.js        # Military units, personnel, branches by country
├── vehicles-db.js          # Military vehicles, aircraft, vessels, weapons
├── sanctions-data.js       # Active sanctions and arms embargoes
├── arms-trade-data.js      # Historical and recent arms transfers (SIPRI TIV)
├── timeline-data.js        # Conflict timeline (UCDP dataset base)
├── alliance-data.js        # Military and political alliances
├── nuclear-data.js         # Nuclear arsenal data (9 states)
├── templates/
│   ├── army-units.template.js      # Copy-paste template
│   ├── vehicles.template.js
│   ├── sanctions.template.js
│   ├── arms-trade.template.js
│   └── timeline.template.js
├── CONTRIBUTING.md         # Full contribution guide
├── TEMPLATES.md            # Format reference for all datasets
├── SOURCES.md              # Approved data sources
├── CONTRIBUTORS.md         # Hall of fame
└── LICENSE                 # CC BY 4.0
```

---

## ✅ Approved Data Sources

| Source | Free | Best For |
|--------|------|----------|
| [SIPRI](https://sipri.org) | ✅ | Arms transfers, military spending |
| [UCDP](https://ucdp.uu.se) | ✅ | Conflict history, academic standard |
| [CIA World Factbook](https://cia.gov/the-world-factbook/) | ✅ | Personnel, branches overview |
| [FAS Nuclear Notebook](https://fas.org/issues/nuclear-weapons/nuclear-notebook/) | ✅ | Nuclear arsenals |
| [ACLED](https://acleddata.com) | ✅ | Recent conflict events |
| [OFAC SDN List](https://ofac.treasury.gov) | ✅ | US sanctions |
| [EU Sanctions Map](https://sanctionsmap.eu) | ✅ | EU sanctions |
| [GlobalFirepower](https://globalfirepower.com) | ✅ | Cross-reference only — verify independently |
| Government defence ministry websites | ✅ | Official figures |
| IISS Military Balance | ❌ Paid | Most detailed — cite page, don't copy |

See [`SOURCES.md`](SOURCES.md) for the complete list with usage notes.

---

## ⚖️ License

Data is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You are free to use, share and adapt this data for any purpose — including commercial use — as long as you credit **WarScope (warscopeglobal.com)** as the source.

**Note:** WarScope compiles data from public sources including SIPRI, UCDP, FAS, government defence ministries and community contributors. Original sources retain their own copyright. Always cite the primary source when publishing.

---

## 🚫 What We Don't Accept

- Classified or leaked government documents
- Data without a cited source
- Information that could endanger military personnel or ongoing operations
- Unverified social media posts or forum claims

---

## 📬 Contact

- **Website:** [warscopeglobal.com](https://warscopeglobal.com)
- **Contribute (no-code form):** [warscopeglobal.com/contribute](https://warscopeglobal.com/contribute)
- **Email:** contact@warscopeglobal.com
- **Issues:** Use the GitHub Issues tab for data corrections or questions

---

*WarScope displays publicly available information only. All data is sourced from open, verifiable sources.*
