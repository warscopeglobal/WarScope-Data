# Data Templates

Copy-paste templates for each dataset. Follow the exact format shown — only the values change, not the structure.

All templates are also available as standalone files in the `templates/` folder.

---

## 1. Army Units & Order of Battle (`army-units-db.js`)

Add your entry to the `UNITS` array and make sure your country is in the `COUNTRIES` object.

### Add to COUNTRIES object:
```js
'Nigeria': { flag: '🇳🇬', iso3: 'NGA' },
```

### Add to UNITS array:
```js
// ═══════════════════════════════════════════
// ───────────── NIGERIA ─────────────────────
// ═══════════════════════════════════════════
{
  country: 'Nigeria',
  iso3: 'NGA',
  branch: 'army',           // army | navy | air | marines | sof | strategic | cyber | space | missile | coastguard | gendarmerie
  name: 'Nigerian Army',
  established: 1960,
  personnel: {
    active:  100000,        // use null if unknown
    reserve: 32000,         // use null if unknown
  },
  hq: 'Abuja',
  commander: 'Chief of Army Staff',  // title or name if public
  majorUnits: [
    '1 Division (Kaduna)',
    '2 Division (Ibadan)',
    '3 Division (Jos)',
    '81 Division (Lagos)',
    '82 Division (Enugu)',
  ],
  equipment: {
    tanks:      148,        // main battle tanks — use null if unknown
    apcs:       1500,       // armoured personnel carriers
    artillery:  339,        // towed + self-propelled
    helicopters: 48,
  },
  missions: [
    'Counter-insurgency (Boko Haram, northeast)',
    'Counter-banditry (northwest)',
    'ECOWAS peacekeeping',
  ],
  notes: 'Figures approximate — sourced 2025',
  source: 'Nigerian Army official website (army.mil.ng) + IISS Military Balance 2025 p.489',
  lastVerified: '2026-03',  // YYYY-MM format
},
{
  country: 'Nigeria',
  iso3: 'NGA',
  branch: 'navy',
  name: 'Nigerian Navy',
  established: 1958,
  personnel: {
    active:  23000,
    reserve: null,
  },
  hq: 'Abuja (Naval HQ)',
  majorUnits: ['Western Naval Command', 'Eastern Naval Command', 'Central Naval Command'],
  equipment: {
    frigates:     1,
    corvettes:    2,
    patrolVessels: 35,
    submarines:   0,
  },
  notes: null,
  source: 'Nigerian Navy official website (navy.mil.ng) + IISS 2025',
  lastVerified: '2026-03',
},
{
  country: 'Nigeria',
  iso3: 'NGA',
  branch: 'air',
  name: 'Nigerian Air Force',
  established: 1963,
  personnel: {
    active:  18000,
    reserve: null,
  },
  hq: 'Abuja',
  majorUnits: ['Ground Attack Group', 'Fighter Group', 'Transport Group'],
  equipment: {
    fighters:       12,     // combat-capable jets
    attackAircraft: 6,
    transportAircraft: 23,
    helicopters:    32,
    trainers:       31,
    drones:         6,
  },
  aircraft: [
    { name:'Alpha Jet', role:'Light attack / trainer', quantity: 12 },
    { name:'JF-17 Thunder', role:'Fighter', quantity: 3 },
    { name:'C-130 Hercules', role:'Transport', quantity: 6 },
  ],
  notes: 'JF-17 recently ordered — delivery ongoing',
  source: 'Nigerian Air Force (airforce.mil.ng) + Flight Global World Air Forces 2025',
  lastVerified: '2026-03',
},
```

**Available branch values:** `army` `navy` `air` `marines` `sof` `strategic` `cyber` `space` `missile` `coastguard` `gendarmerie`

---

## 2. Military Vehicles & Equipment (`vehicles-data.js`)

Add to the `VEHICLES` array.

```js
{
  id: 'k2-black-panther',        // unique slug, lowercase, hyphens
  name: 'K2 Black Panther',
  manufacturer: 'Hyundai Rotem',
  country: 'South Korea',        // country of origin
  iso3: 'KOR',
  type: 'Main Battle Tank',      // see types below
  role: 'Armoured warfare, breakthrough operations',
  status: 'Active',              // Active | In Development | Retired | Export Only
  inService: 2014,               // year entered service
  image: 'https://upload.wikimedia.org/wikipedia/commons/...',  // Wikimedia preferred
  specs: {
    weight:     '55 tonnes',
    length:     '10.8 m',
    width:      '3.6 m',
    height:     '2.4 m',
    crew:       3,
    speed:      '70 km/h (road)',
    range:      '450 km',
    engine:     '1,500 hp MTU diesel',
    armament:   '120mm smoothbore gun, 7.62mm coaxial MG',
    armour:     'Composite + ERA',
  },
  operators: [
    { iso3: 'KOR', name: 'South Korea', quantity: 260, notes: 'Primary operator' },
    { iso3: 'POL', name: 'Poland',      quantity: 180, notes: 'K2PL variant on order' },
    { iso3: 'NOR', name: 'Norway',      quantity: 54,  notes: 'On order 2023' },
  ],
  description: 'South Korea\'s most advanced main battle tank. Features autoloader, active protection system, and remote weapons station.',
  source: 'Hyundai Rotem official specifications + IISS Military Balance 2025',
  lastVerified: '2026-03',
},
```

**Common type values:** `Main Battle Tank` `Infantry Fighting Vehicle` `Armoured Personnel Carrier` `Self-Propelled Artillery` `Towed Artillery` `Multiple Rocket Launcher` `Fighter Aircraft` `Attack Helicopter` `Transport Aircraft` `Frigate` `Destroyer` `Submarine` `Patrol Vessel` `UAV / Drone` `Air Defence System` `Ballistic Missile`

---

## 3. Sanctions (`sanctions-data.js`)

Add to the `SANCTIONED_COUNTRIES` array.

```js
{
  iso3: 'MMR',
  name: 'Myanmar',
  flag: '🇲🇲',
  severity: 'high',             // critical | high | medium | low
  summary: 'Sanctions imposed following the military coup of 1 February 2021 and subsequent violent crackdown on civilian protesters.',
  sanctions: [
    {
      id: 'mmr-us-arms',
      issuer: 'US',             // UN | US | EU | UK
      type: 'arms',             // arms | financial | travel | trade | oil
      title: 'Arms Embargo on Myanmar Military (Tatmadaw)',
      imposed: '2021-02-11',    // YYYY-MM-DD
      expanded: null,           // date if expanded later, or null
      description: 'Prohibition on export of defence articles and services to Myanmar military following coup. Includes suspension of military-to-military activities.',
      status: 'active',         // active | suspended | lifted
      legalBasis: 'Executive Order 14014 (Biden, Feb 2021)',
      source: 'OFAC — ofac.treasury.gov',
    },
    {
      id: 'mmr-eu-arms',
      issuer: 'EU',
      type: 'arms',
      title: 'EU Arms Embargo on Myanmar',
      imposed: '2021-02-22',
      expanded: '2022-02-21',
      description: 'Full arms embargo covering all military equipment. Expanded in 2022 to include dual-use goods and additional targeted sanctions on military entities.',
      status: 'active',
      legalBasis: 'Council Decision 2021/308/CFSP; Regulation 2021/309',
      source: 'EU Sanctions Map — sanctionsmap.eu',
    },
    {
      id: 'mmr-us-financial',
      issuer: 'US',
      type: 'financial',
      title: 'Asset Freezes on Military Leadership',
      imposed: '2021-02-11',
      description: 'Blocking sanctions on Senior General Min Aung Hlaing and other coup leaders. Freezes US-held assets and prohibits US persons from transacting with designated individuals.',
      status: 'active',
      legalBasis: 'EO 14014 — OFAC SDN List',
      source: 'OFAC SDN List — ofac.treasury.gov',
    },
  ],
  source: 'OFAC + EU Sanctions Map + UK OFSI',
  lastVerified: '2026-03',
},
```

**Issuer values:** `UN` `US` `EU` `UK`
**Type values:** `arms` `financial` `travel` `trade` `oil`
**Severity values:** `critical` `high` `medium` `low`

---

## 4. Arms Transfers (`arms-trade-data.js`)

Add to the `ARMS_TRANSFERS` array. TIV = Trend Indicator Value (SIPRI methodology, millions USD equivalent).

```js
{
  id: 'mod-50',                 // unique id — use next available number
  era: 'modern',                // cold-war | post-cold | modern
  from: 'France',               // supplier country name
  to: 'India',                  // recipient country name
  tiv: 3200,                    // SIPRI TIV value in millions USD equivalent
  cat: 'aircraft',              // aircraft | naval | missile | armour | drone | artillery | mixed
  label: '36 Rafale fighter jets',
  year: 2016,                   // year of contract / delivery
  fromLat: 48.9, fromLng: 2.3, // Paris coordinates
  toLat: 28.6,   toLng: 77.2,  // New Delhi coordinates
  description: '€7.87 billion government-to-government deal for 36 Rafale F3R jets. France\'s largest ever arms export deal. Delivery completed 2022.',
  source: 'SIPRI Arms Transfers Database + French MoD press release',
  lastVerified: '2026-03',
},
```

**How to find TIV values:** Go to [sipri.org/databases/armstransfers](https://sipri.org/databases/armstransfers) → use the search tool → find your transfer → note the TIV figure.

**Era values:** `cold-war` (1950–1991) `post-cold` (1992–2013) `modern` (2014–present)

**Category values:** `aircraft` `naval` `missile` `armour` `drone` `artillery` `mixed`

---

## 5. Conflict Timeline (`timeline-data.js`)

Add to the `TIMELINE_CONFLICTS` array.

```js
{
  id: 'eth-tigray-2020',        // unique slug
  location: 'Ethiopia (Tigray)',
  region: 'Africa',             // Africa | Middle East | Europe | Asia | Americas | Oceania
  sideA: 'Ethiopian Government + Eritrea',
  sideB: 'TPLF (Tigray People\'s Liberation Front)',
  conflictType: 'Internal',     // Internal | Interstate | Internationalised Internal
  incompatibility: 'Government', // Government | Territory | Both
  startYear: 2020,
  lastYear: 2022,
  isActive: false,              // true if ongoing
  peakIntensity: 2,             // 1=Minor (<25 deaths/year) | 2=War (>1000 deaths/year)
  peakLabel: 'War',             // Minor Armed Conflict | War
  totalDeaths: 300000,          // approximate — use null if unknown
  episodes: [
    { year: 2020, intensity: 2, label: 'War' },
    { year: 2021, intensity: 2, label: 'War' },
    { year: 2022, intensity: 1, label: 'Minor (ceasefire Nov 2022)' },
  ],
  description: 'Armed conflict between Ethiopian federal forces (with Eritrean support) and the Tigray People\'s Liberation Front. Ceasefire signed November 2022.',
  tags: ['civil war', 'humanitarian crisis', 'ethnic conflict'],
  source: 'UCDP Conflict Catalog v24.1 + ACLED',
  lastVerified: '2026-03',
},
```

**Intensity values:** `1` = Minor armed conflict (25–999 battle deaths/year) | `2` = War (1000+ battle deaths/year)

**Region values:** `Africa` `Middle East` `Europe` `Asia` `Americas` `Oceania`

---

## Quick Reference — Required Fields Per Dataset

| Dataset | Required | Optional |
|---------|----------|----------|
| Army Units | `country`, `iso3`, `branch`, `name`, `personnel.active`, `source` | `equipment`, `majorUnits`, `missions`, `notes` |
| Vehicles | `id`, `name`, `type`, `operators`, `source` | `specs`, `image`, `description` |
| Sanctions | `iso3`, `name`, `severity`, `sanctions[].issuer`, `sanctions[].type`, `sanctions[].imposed`, `source` | `expanded`, `legalBasis` |
| Arms Trade | `id`, `era`, `from`, `to`, `tiv`, `cat`, `year`, `source` | `description`, `label` |
| Timeline | `id`, `location`, `sideA`, `sideB`, `startYear`, `isActive`, `source` | `episodes`, `totalDeaths`, `description` |

---

## Notes on Data Quality

- **Mark estimates clearly:** Use `~` prefix (`~100000`) or add a `notes` field saying "figures are estimates"
- **Use null not 0:** If you don't know a value, use `null` — `0` means zero, which is a real value
- **Dates:** Always use `YYYY-MM-DD` format for dates, `YYYY-MM` for month precision, `YYYY` for year only
- **Always include `lastVerified`:** So we know when to re-check the data
- **Always include `source`:** The single most important field
