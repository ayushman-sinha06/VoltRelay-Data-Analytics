# VoltRelay EV Battery-Swapping Network Analytics

## Data Analytics Hackathon — Gradient

This project analyzes the operational performance of an EV battery-swapping network, VoltRelay, using large-scale swap-event, station, battery, pricing and rider-level data.

The objective is to identify the major drivers of service failures, operational bottlenecks, battery and energy-cost patterns, station-level pressure and differences in rider engagement.

---

## Business Questions

The analysis addresses six key business questions:

1. **Network Performance & Growth**  
   How has network demand and operational performance evolved over time?

2. **Service Failures & Customer Experience**  
   What are the major causes of unsuccessful swaps, and are poor customer waiting experiences associated with unsuccessful outcomes?

3. **Station & Geographic Performance**  
   Which stations experience the greatest operational pressure, and where are battery-unavailability failures concentrated?

4. **Battery & Equipment Performance**  
   How do battery state-of-charge and state-of-health relate to recharge energy requirements?

5. **Pricing & Economics**  
   How do energy consumption and electricity tariffs affect energy costs and network economics?

6. **Rider Retention & Engagement**  
   What rider characteristics are associated with stronger engagement and where are potential rider-retention risks concentrated?

---

## Key Insights

- Network demand increased substantially over the observed period, while completion performance experienced periods of deterioration during high-demand periods.
- **Battery-unavailability failures accounted for approximately 3.47% of all swap attempts**, making them the largest unsuccessful-swap category.
- **Queue abandonment accounted for approximately 1.77% of attempts** and was associated with substantially longer waiting times.
- Median queue waiting time for abandoned swaps was approximately **648 seconds**, compared with **209 seconds for completed swaps**.
- Operational pressure was concentrated at specific stations rather than being evenly distributed across the network.
- Incoming battery SOC showed a weak negative relationship with recharge energy, while battery SOH showed a stronger positive association.
- Energy consumption differences across tariff categories were more pronounced than differences in average electricity tariffs.
- Rider engagement varied most noticeably across **vehicle class and commercial plan segments**, while differences across age and shift categories were comparatively smaller.

---

## Analysis Areas

### 1. Network Performance
- Monthly swap demand
- Completion rates
- Failed attempts
- Revenue trends
- Periods of operational stress

### 2. Service Failures
- Failure composition
- Battery-unavailability failures
- Queue abandonment
- Customer waiting times
- Station-level failure patterns

### 3. Station Operations
- Swap attempt volume
- Completion rates
- Revenue
- Queue waiting time
- Battery-unavailability rate and volume

### 4. Battery & Energy Analysis
- Incoming battery SOC
- Battery SOH
- Recharge energy requirements
- SOC-energy relationship
- SOH-energy relationship

### 5. Economics
- Energy cost per completed swap
- Electricity tariff variation
- Energy consumption by tariff category
- Revenue per completed swap

### 6. Rider Engagement
- Vehicle class
- Plan type
- Declared shift
- Signup channel
- Age band
- KYC verification status

---

## Tools & Technologies

- Python
- Pandas
- Matplotlib
- Seaborn
- Jupyter / Google Colab
- Exploratory Data Analysis
- Statistical Analysis
- Data Visualization
- Business Analytics

---

## Key Findings

### Q1 — Network Performance Over Time
- Monthly swap attempts increased substantially, from approximately **110K in January 2024** to more than **340K by May 2025**.
- Completion rates remained around **95–96%** during most of the period but deteriorated during **April–June 2024** and **April–June 2025**.
- **May 2025** was the most notable stress period, with completion falling to approximately **90%** while the network handled its highest monthly swap volume.
- The pattern indicates periods of operational stress as network demand increased.

### Q2 — Service Failures & Customer Experience
- `failed_no_charged_battery` was the largest unsuccessful-swap category, accounting for approximately **3.47% of all swap attempts**.
- `abandoned_queue` was the second-largest failure category at approximately **1.77%**.
- Queue abandonment was strongly associated with longer waiting times: the median wait was **648 seconds (10.8 minutes)** for abandoned swaps versus **209 seconds (3.5 minutes)** for completed swaps.
- The two major operational themes identified were **battery availability** and **queue/service capacity**.

### Q3 — Station & Geographic Patterns
- **STN-BLR-019** recorded the highest swap-attempt volume at approximately **58,067 attempts**.
- Among the ten busiest stations, completion rates ranged from approximately **91.27% to 95.35%**, compared with an overall network completion rate of approximately **94.04%**.
- **STN-JAI-141** recorded the lowest completion rate among the top ten busiest stations at approximately **91.27%** and had a battery-unavailability failure rate of approximately **5.43%**.
- Battery-unavailability failure volume was highest at **STN-JAI-138 (2,635)**, followed by **STN-DEL-043 (2,611)**, **STN-HYD-072 (2,530)** and **STN-DEL-050 (2,513)**.
- The analysis indicates that operational hotspots are better identified by combining **demand, completion performance and battery availability** rather than looking at station volume alone.

### Q4 — Battery & Equipment Performance
- Completed swaps entering with **0–20% SOC** required approximately **2.09 kWh**, compared with **1.80 kWh** for the 20–40% SOC group.
- The SOC-energy correlation was **−0.118**, indicating only a weak negative relationship.
- Battery SOH showed a stronger positive association with recharge energy.
- Average energy requirement increased from approximately **1.68 kWh for batteries below 80% SOH** to approximately **2.51 kWh for batteries above 100% SOH**.
- The raw SOH-energy correlation was **0.341**.
- Overall, battery condition and charging state are associated with energy requirements, but neither variable alone explains the full variation.

### Q5 — Pricing & Economics
- Revenue per completed swap increased from approximately **₹59–60** during the first half of 2024 to around **₹65 from July 2024 onward**.
- Average energy cost per completed swap was approximately **₹19.50**, with a median of approximately **₹17.39**.
- PARTNER swaps required approximately **2.17 kWh** per completed swap, compared with **1.97 kWh for STD** and **1.88 kWh for PEAK/OFFPEAK**.
- Average grid tariffs were relatively similar across categories, at approximately **₹9.23–₹9.33/kWh**.
- Therefore, variation in **energy consumption** was a more important driver of energy-cost variation than tariff differences.
- The available data does not support treating the calculated contribution-margin proxy as formal accounting profit.

### Q6 — Rider Retention & Engagement
- **2W riders** averaged approximately **191 completed swaps**, compared with approximately **131 for 3W riders**.
- Completion rates were approximately **93.8% for 2W** and **88.5% for 3W**.
- Partner-billed riders averaged approximately **195 completed swaps**, compared with approximately **162** for both pay-as-you-go and prepaid-pack riders.
- Signup channel also showed differences in engagement: partner-onboarding and field-agent riders recorded higher activity than app-store and referral cohorts.
- Declared shift and age band showed relatively limited differences, with completion rates remaining close to **93%**.
- KYC status also showed only a modest difference in completion performance.
- Overall, the observed engagement differences were more pronounced across **vehicle type and commercial/onboarding characteristics** than across demographic characteristics.
- These findings represent **associations in observed rider activity, not causal effects**.

---


```markdown
## Business Implications

The analysis points to six major operational priorities:

1. **Improve battery availability** at stations with elevated battery-unavailability failures.
2. **Reduce excessive queue waiting times** to address the strong association between long waits and abandoned swaps.
3. **Prioritize station-level interventions** using a combination of demand, completion rate and battery-failure metrics.
4. **Incorporate battery condition into charging and allocation decisions**, since SOH and SOC are associated with recharge energy requirements.
5. **Control energy consumption per completed swap**, as energy usage explains more cost variation than grid tariff differences in the observed data.
6. **Monitor lower-engagement rider segments**, particularly 3W riders, while distinguishing observed associations from causal retention drivers.


## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter / Google Colab
- Exploratory Data Analysis
- Statistical correlation analysis
- Business KPI analysis
- Data visualization

## Project Structure

```text
VoltRelay-Data-Analytics/
│
├── README.md
└── VoltRelay_6Q_Analysis.ipynb
