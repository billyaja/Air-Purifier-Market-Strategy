# 🌬️ AirPure Innovations: India Market Entry Strategy
[**Click Here to View Dashboard** ](https://app.powerbi.com/view?r=eyJrIjoiNDFlYmFhZTgtY2JlMC00NDcwLWFiMGUtOTk3MDExY2IyZjRlIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9)

![Status](https://img.shields.io/badge/Status-Complete-success)
![Tools](https://img.shields.io/badge/Tools-Python%20|%20PowerBI%20|%20Pandas-blue)

## **1. Executive Summary**
AirPure Innovations should reject a generic nationwide launch in favor of a **"Precision Entry Strategy"**—targeting **Maharashtra** for immediate premium adoption and **North India** for future industrial-grade protection.

* **The Geography of Risk:** The market follows a strict "Barbell Distribution." The North (Delhi) faces **Hazardous** levels (AQI 200+), while the South (Bengaluru) maintains **Moderate** levels (AQI < 60), requiring distinct product lines.
* **The Strategic Pivot:** Initial volume metrics were misleading. By applying a **"Lifestyle Compatibility Filter"** (isolating personal vehicles from commercial fleets), we discovered that **Maharashtra**—not Uttar Pradesh—is the primary market for premium devices.
* **The "September Window":** Pollution follows a strict U-Curve. Launch must occur in **September** (AQI ~80) to capture the pre-winter surge before the November crisis (AQI ~150+).

---

## **2. Business Scenario**
**Client:** AirPure Innovations (Smart Home Electronics Startup).

**The Problem:** The client wants to enter the Indian market but lacks data on **Where** (Geography), **When** (Seasonality), and **Who** (Target Segment) to prioritize.

**The Objective:** Analyze 3 years of air quality and vehicle registration data to build a data-driven **Go-to-Market Strategy**.

---

## **3. Insights Deep Dive**

### **A. Geography of Risk ("The Barbell")**

* **Finding:** 80% of hazardous air days are concentrated in the Indo-Gangetic Plain (North).
* **Implication:** A "one-size-fits-all" product will fail.
    * **North:** Needs HEPA H14 Industrial Filters (Dust focus).
    * **South:** Needs Active Carbon & Smart Sensors (Gas/Odor focus).

### **B. Market Segmentation ("The Lifestyle Pivot")**
* **Challenge:** Raw data indicated Uttar Pradesh had the highest EV adoption, suggesting a "Green" market.
* **Investigation:** Deep-dive analysis revealed 90% of this volume was driven by commercial utility vehicles (e-Rickshaws).
* **Correction:** We applied a **"Lifestyle Filter"** (Cars & Scooters only).
* **Result:** **Maharashtra** emerged as the #1 "Sweet Spot," containing the highest concentration of premium early adopters living in high-pollution zones.

### **C. Seasonality ("The Window of Opportunity")**
* **Finding:** Pollution is dormant during the Monsoons (July-August).
* **Inflection Point:** **September 1st**. AQI begins a rapid 90-day ascent.
* **Strategy:** Marketing must frame air purifiers as "Preventative Health" in September, before the visible smog in November triggers generic panic buying.

---

## **4. The Solution: Executive Dashboard**
*An interactive Power BI Dashboard was created to guide the COO's decision-making.*

**Page 1: The Risk Radar**
![](/images/risk_radar.png)
* **Visual:** Geographic Heatmap (Red=Hazardous, Green=Safe).
* **Function:** Instantly identifies the "Red Zone" markets vs. "Green Zone" markets.

**Page 2: The Forecast Center**
![](/images/seasonality_curve.png)
* **Visual:** Seasonality Trend Line with a "Launch Window" reference line.
* **Function:** Aligns supply chain mobilization with the September inflection point.

**Page 3: The Market Radar**
![](/images/market_radar.png)
* **Visual:** Quadrant Analysis (Pollution Severity vs. Lifestyle Wealth).
* **Function:** visually positions **Maharashtra** in the top-right "Priority Quadrant."

---

## **5. Strategic Recommendations**

| Strategy | Target Market | Product Focus | Launch Window |
| :--- | :--- | :--- | :--- |
| **"The Fortress"** | **Maharashtra (Mumbai/Pune)** | **Premium Smart (App + Gas Sensor)** | **Sept 15** |
| **"The Shield"** | **North India (Delhi/NCR)** | **Industrial Grade (High CADR)** | **Oct 01** |
| **"The Lab"** | **Karnataka (Bengaluru)** | **Wellness Tech (Lifestyle)** | **Nov 01** |

---

## **6. Technical Implementation**
**Data Engineering (Star Schema):**
To ensure scalability, the analysis moved from flat files to a Star Schema architecture:
* **Fact Tables:** `stg_aqi` (Daily), `stg_vehicles` (Monthly).
* **Dimension Tables:** `Dim_State` (Geo), `Dim_Date` (Time).

**Tools Used:**
* **Python (Pandas):** For data cleaning, "Lifestyle Filter" logic, and hypothesis testing.
* **Power BI:** For the interactive Executive Dashboard and DAX scenario modeling.

---

## **7. Caveats & Assumptions**
* **EV as Proxy:** EV adoption is used as a proxy for "Eco-Consciousness" and "Disposable Income."
* **Health Data:** Acute epidemic data (Dengue) was excluded to maintain a focus on respiratory health indicators.


---
**Created By:** [Billy Erickson Samosir](https://www.linkedin.com/in/billyerickson/)


