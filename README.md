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

## Repository Contents

```text
VoltRelay-Data-Analytics/
│
├── VoltRelay_6Q_Analysis.ipynb
└── README.md
