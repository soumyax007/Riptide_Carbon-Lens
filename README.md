# 🌿 Carbon Lens
### India's First Conversational Carbon Auditor for MSMEs

> **Transform operational data into a professional green roadmap — in under 5 minutes.**

[![License](https://img.shields.io/badge/License-Apache_2.0-green.svg)](https://opensource.org/licenses/Apache-2.0)
[![Built with Claude](https://img.shields.io/badge/AI-Claude%203.5%20Haiku-blueviolet)](https://www.anthropic.com)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-zero-brightgreen)](#)
[![India](https://img.shields.io/badge/Built%20for-India%20🇮🇳-orange)](#)

---

## The Problem

India's 63 million MSMEs account for ~30% of the country's GDP — yet most have **zero access to carbon consulting**. Traditional audits cost ₹50,000–₹5,00,000 and require specialist consultants. Carbon Lens changes that.

---

## What It Does

Carbon Lens takes basic operational inputs (electricity usage, diesel, fuel, headcount) and produces:

- 📊 **Scope 1, 2 & 3 emission breakdown** using India-specific emission factors
- 🤖 **3 AI-generated reduction actions** tailored to the business type and city
- 💰 **INR savings estimate** for each action — so green = profitable
- 📄 **One-click PDF report** ready for auditors, investors, or ESG filings

---


> *No account needed. No server. Just open `index.html` and go.*

---

## Philosophy: "Less but Better"

Inspired by Dieter Rams' design principles:

- **Whitespace over decoration** — the UI informs, it doesn't distract
- **Action over data** — every number is tied to a rupee savings figure
- **No-Cloud Architecture** — single HTML file, zero npm installs, runs offline

---

## Key Features

| Feature | Detail |
|---|---|
| 🇮🇳 India-specific emission factors | CEA grid factor: **0.82 kg CO₂e/kWh** |
| 🤖 AI-powered roadmap | Claude 3.5 Haiku generates 3 localized actions |
| 📄 One-click PDF export | Native browser print engine — no libraries needed |
| 🛡️ Resilient fallback | Industry-specific mock data if API is unavailable |
| ⚡ Zero dependencies | Single HTML file, no build step, no npm |

---

## The Carbon Math

**Scope 1 — Direct Emissions**
```
Diesel (litres/month × 12)  × 2.68 kg CO₂e/L   → tonnes/year
Petrol (litres/month × 12)  × 2.31 kg CO₂e/L   → tonnes/year
```

**Scope 2 — Indirect (Grid Electricity)**
```
Electricity (kWh/month × 12) × 0.82 kg CO₂e/kWh → tonnes/year
```

**Scope 3 — Supply Chain (Proxy)**
```
Estimated from employee count × operational intensity factor
```

### Emission Factors Reference

| Source | Factor | Unit | Authority |
|---|---|---|---|
| Grid Electricity | 0.82 | kg CO₂e / kWh | CEA (India) |
| Diesel | 2.68 | kg CO₂e / Litre | IPCC |
| Petrol | 2.31 | kg CO₂e / Litre | GHG Protocol |

---

## AI Integration

Once the footprint is calculated, operational data is passed to the Anthropic Claude API:

```javascript
// Prompt sent to Claude 3.5 Haiku
`You are a carbon reduction expert for Indian MSMEs.
A ${businessType} in ${city} with ${employees} employees has:
  Electricity ${elec}T, Diesel ${diesel}T, Vehicles ${fuel}T,
  Supply Chain ${supply}T — TOTAL ${total}T CO₂e/year.

Return ONLY a JSON array of exactly 3 actions:
[{"action":"...","co2Saved":number,"inrSaved":number,"difficulty":"Easy|Medium|Hard"}]`
```

The model returns localized, actionable suggestions — e.g., installing BLDC fans, switching to solar rooftops, or sourcing locally — with realistic INR savings calibrated to Indian MSME scale.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla JS (ES6+), HTML5, CSS3 |
| Fonts | DM Sans + DM Mono (Google Fonts) |
| Intelligence | Claude 3.5 Haiku (Anthropic API) |
| PDF Export | Native browser `window.print()` |
| Hosting | Vercel / Netlify / GitHub Pages |

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/carbon-lens.git
cd carbon-lens
```

### 2. Configure your API key

Open `index.html` and find the `getRecommendations` function. Replace the placeholder:

```javascript
headers: {
  "Content-Type": "application/json",
  "x-api-key": "YOUR_ANTHROPIC_API_KEY",   // ← replace this
  "anthropic-version": "2023-06-01",
  "anthropic-dangerous-direct-browser-access": "true"
}
```

> ⚠️ **Security Note:** This is a hackathon-ready frontend implementation. For production, move the API call to a backend proxy (Node.js, Python, etc.) so your secret key is never exposed in client-side code.

### 3. Run locally

```bash
# No npm install required — just open the file
open index.html
```

Works in Chrome, Brave, and Safari.

---

## Project Structure

```
carbon-lens/
├── index.html          # Entire application — single file
├── README.md
└── assets/
    └── screenshot.png  # Optional: demo screenshot
```

---

## Resilient Fallback

If the Anthropic API is unavailable (rate limit, no key, network error), Carbon Lens automatically falls back to a curated set of **industry-specific recommendations** — so the demo never breaks:

| Industry | Pre-built Actions |
|---|---|
| Manufacturing | VFDs on motors, LED sensors, rooftop solar |
| Textile | Solar water heating, LED upgrade, local sourcing |
| Restaurant | Induction hobs, refrigeration seals, farm sourcing |
| IT / Software | Power management, Energy Star gear, WFH policy |

---

## Roadmap

- [ ] Multi-location audit aggregation
- [ ] BRSR (Business Responsibility & Sustainability Reporting) export
- [ ] Benchmarking against MSME sector averages


---

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

1. Fork the repository
2. Create your branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## License

```
Copyright 2026 Carbon Lens Authors

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at:

    http://www.apache.org/licenses/LICENSE-2.0
```

---

<p align="center">
  Built to empower India's 63 million MSMEs in the race to Net Zero. 🇮🇳<br>
  <sub>Emission data sources: Central Electricity Authority (CEA), IPCC, GHG Protocol, DEFRA</sub>
</p>
