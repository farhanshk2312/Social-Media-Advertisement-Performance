Possible Use Cases



✅ **SQL \& Data Exploration → Practice joins, filters, aggregations, and window functions.**

✅ Market \& Strategic Analysis → Identify top-performing campaigns, ads, and targeting strategies.

✅ **Cohort Analysis → Segment users by demographics/behavior and track engagement over time.**

✅ Conversion Funnel Tracking → Measure drop-offs from Impression → Click → Purchase.

✅ **Predictive Modeling → Forecast ad performance or user conversion likelihood.**



**8 — Dashboard layout (single page recommended)**



* **Top row (KPIs):** Impressions, Reach, Clicks, CTR, Purchases, CVR, Revenue, Cost, ROAS, CPA, AOV.
* **Main visual (center)**: Time series (Impressions / Clicks / Purchases / Revenue).
* **Right panel**: Top campaigns by ROAS \& Spend (bar chart); Top ads by CTR/CVR.
* **Lower left**: Funnel step chart (Impression → Click → AddToCart → Purchase) with stage conversion percentages.
* **Lower right:** Audience breakdown (age/gender/country) heatmap for ROAS/CPA.
* **Filters:** Date range, Campaign, Creative, Country, Age band, Gender, Interest tags.



**Core Metrics (definitions)**



* Impressions: count of event\_type='Impression'
* Reach: distinct user\_id with any event
* Clicks: count of event\_type='Click'
* Purchases: count of event\_type='Purchase'
* Revenue: sum of revenue
* Cost: sum of cost



**Rates**



* CTR = Clicks / Impressions
* CVR (Click→Purchase) = Purchases / Clicks
* AOV = Revenue / Purchases
* CPA = Cost / Purchases
* CPC = Cost / Clicks
* CPM = (Cost \* 1000) / Impressions
* ROAS = Revenue / Cost
* Funnel (per campaign/ad)
* Stages: Impression → Click → View/AddToCart → Purchase
* Stage-to-Stage = stage\_n+1 / stage\_n
* Overall = Purchases / Impressions



**Cohorts**



Acquisition Cohort = first Impression month per user; track retention to Click/Purchase in later periods.



LTV (simple) = average (future Revenue per acquired user) over a horizon.



**Dashboard Layout (1 page, executives + analysts)**



Top KPIs: Impressions, Reach, Clicks, CTR, Purchases, CVR, Revenue, Cost, ROAS, CPA, AOV.

Trends: Daily/weekly lines—Impressions, Clicks, Purchases, Revenue, ROAS.

Breakdowns:



By Campaign → bar/columns: ROAS, Revenue, Spend, Purchases.



By Ad (creative) → CTR \& CVR comparison.



By Audience (age, gender, country, interests) → heatmap of ROAS/CPA.

Funnel: step chart (Impression→Click→AddToCart→Purchase) with stage-to-stage rates.

Cohorts: acquisition month vs purchase rate over time (matrix/heatmap).

Filters: Date range, Campaign, Ad Type, Country, Gender, Age band, Interests.



**Key DAX measures (Power BI)**



Impressions = COUNTROWS(FILTER(Fact, Fact\[event\_type] = "Impression"))

Clicks = COUNTROWS(FILTER(Fact, Fact\[event\_type] = "Click"))

Purchases = COUNTROWS(FILTER(Fact, Fact\[event\_type] = "Purchase"))

Revenue = SUM(Fact\[revenue])

Cost = SUM(Fact\[cost])

CTR% = DIVIDE(\[Clicks], \[Impressions])

ROAS = DIVIDE(\[Revenue], \[Cost])

CPA = DIVIDE(\[Cost], \[Purchases])

AOV = DIVIDE(\[Revenue], \[Purchases])



**6 — Core metrics \& definitions**



* Impressions: # events where event\_type = 'Impression'
* Reach: distinct user\_id with any event
* Clicks: # event\_type = 'Click'
* Purchases: # event\_type = 'Purchase'
* Revenue / Cost: SUM over revenue / cost fields
* CTR: Clicks / Impressions
* CVR: Purchases / Clicks
* CPC: Cost / Clicks
* CPA: Cost / Purchases
* CPM: (Cost \* 1000) / Impressions
* ROAS: Revenue / Cost
* AOV: Revenue / Purchases
