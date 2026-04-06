##Carbon Lens 🌿
The 5-Minute Carbon Audit for Indian MSMEs
Carbon Lens is an automated sustainability auditor designed specifically for India’s 63 million Micro, Small, and Medium Enterprises (MSMEs). It transforms raw operational data—electricity bills, fuel logs, and headcount—into a professional carbon footprint report with AI-driven, ROI-focused reduction strategies.

📖 The Vision
Most carbon auditing tools are built for Western conglomerates, requiring expensive consultants and complex data. Indian MSMEs face a "Sustainability Gap": they want to reduce costs and emissions but lack the tools to measure them.

Carbon Lens bridges this gap by:

Localizing Data: Using India-specific emission factors (CEA Grid).

Simplifying Input: Only requiring data an owner already has on their monthly bills.

Prioritizing ROI: Giving recommendations that save money (INR) while saving the planet (CO 
2
​
 e).

⚙️ How It Works
The application operates in four distinct phases, moving from raw data to actionable intelligence.

1. Data Collection
The user provides 5 key data points:

Electricity (kWh): Scope 2 emissions.

Diesel (L): Scope 1 (Stationary combustion/Generators).

Vehicle Fuel (L): Scope 1 (Mobile combustion).

Employee Count: Proxy for Scope 3 (Commuter/Office overhead).

Industry & City: Context for AI benchmarks.

2. Local Engineering (The Math)
Before calling the AI, the tool performs deterministic calculations using established emission factors:

Grid Electricity: kWh×0.82 (India CEA Grid Factor).

Diesel: Litres×2.68 (Standard density/emissions).

Vehicle Fuel: Litres×2.31.

Supply Chain (Estimate): (Employees×0.5)+(ElectricityEmissions×0.3).

3. AI Inference (Claude 3.5)
The calculated totals are sent to the Claude API. The AI acts as a senior sustainability consultant to:

Analyze the footprint based on the specific industry (e.g., Textile vs. IT).

Generate three "High-ROI" actions.

Calculate estimated INR savings based on current Indian market rates for solar, LED retrofitting, and energy efficiency.

4. Professional Reporting
The system generates a dashboard using a "Dieter Rams" minimalist UI, allowing the user to export a clean PDF for stakeholders, banks (for green loans), or internal tracking.

🛠️ Tech Stack
Frontend: Vanilla JavaScript (ES6+), HTML5, CSS3.

Intelligence: Anthropic Claude API (Haiku/Sonnet).

Design: Minimalist functionalism (Dieter Rams principle).

Deployment: Vercel / GitHub Pages.

🚀 Quick Start
Clone the repository:

Bash
git clone https://github.com/your-username/carbon-lens.git
Configure API Key:
Open index.html and replace REPLACE_WITH_YOUR_KEY with your Anthropic API key.
Note: For production, this should be handled via a backend proxy to keep the key secure.

Run Locally:
Open index.html in any modern web browser.

📊 Emission Factors Reference
Source	Factor	Unit	Reference
Electricity	0.82	kgCO 
2
​
 e/kWh	Central Electricity Authority (India)
Diesel	2.68	kgCO 
2
​
 e/Litre	IPCC / GHG Protocol
Petrol	2.31	kgCO 
2
​
 e/Litre	IPCC / GHG Protocol
🛡️ License
Distributed under the Apache License 2.0
 License. See LICENSE for more information.

Built for India's Green Transition. 🇮🇳


