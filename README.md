# Valuation Model: Tata Consultancy Services (TCS)

## What is this?
This is a financial valuation project I built to practice equity research using Python. Instead of relying on standard Excel templates, I wanted to build a dynamic script that pulls live market data and calculates intrinsic value automatically.

I chose **TCS (Tata Consultancy Services)** because the stock has been volatile due to fears of a US recession, and I wanted to see if the fundamentals justified the lower price.

## The Results (TL;DR)
Based on my model, **TCS looks undervalued.**

* **Current Market Price:** ₹3,141
* **My Calculated Fair Value:** ~₹3,639
* **Potential Upside:** ~16%

## How I got these numbers
I didn't want to just plug in random growth rates to make the stock look good. I tried to be conservative to see if the investment still made sense in a "worst-case" scenario.

### 1. Growth Rate (7.8%)
Historically, TCS grows at double digits. However, given the current slowdown in US/Europe tech spending, I capped the growth rate at **7.8%** for the next 5 years. This is barely above India's nominal GDP growth—a very safe assumption.

### 2. Discount Rate / WACC (8.89%)
I used live data from YFinance to calculate the Weighted Average Cost of Capital. TCS has a very low Beta (0.33), which lowers the discount rate, reflecting that it's a stable, low-risk stock.

### 3. Comparison with Peers
I also checked the P/E ratios of Infosys and HCL Tech. Based on the peer average, TCS should be trading around **₹3,296**, which confirms my DCF findings that the market is currently mispricing it.

## Stress Testing the Model
To be sure, I ran a Sensitivity Analysis (visualized in the heatmap below). I wanted to see what happens if my assumptions are wrong.

* **X-Axis:** Growth Rate (5.8% to 9.8%)
* **Y-Axis:** WACC (Discount Rate)

**The Takeaway:** Even if growth drops to 6.8% (very low) and interest rates rise, the model still shows the price holding above ₹3,000. This gives me a comfortable "Margin of Safety."


## The Code
The project is built in a single Python notebook/script using:
* `yfinance` for real-time data.
* `pandas` & `numpy` for the heavy math (DCF projections).
* `seaborn` for the heatmap visualization.
