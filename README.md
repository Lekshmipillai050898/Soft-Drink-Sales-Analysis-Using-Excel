## Soft Drink Sales Analysis Using Excel
This project presents a comprehensive time series analysis of a fictitious soft drink company using Excel. The dataset covers monthly data from 
January 2012 to September 2015 and includes sales volume, media advertising spends, pricing, promotional efforts, and competitor activity.
The objective of the project is to uncover trends, seasonality, and key drivers of sales performance using statistical analysis techniques and Excel functions.

## Dataset Description
Time Range: Jan 2012 – Sep 2015 
Total Months: 45

## Data Dictionary

Month-Month of activity

SalesVol-Sales volume in litres

TVGRP-TV Gross Rating Points

Instoreads-Instore ad spend

Outdoorads-Outdoor ad spend (billboards, hoardings, etc.)

Promotions-Spend on discounts, offers

Digitalads-Online advertising spend (Google, FB, etc.)

Price-Avg. price per 10 litres

Comp1TV-Competitor 1 TV ad spend

Comp1NP-Competitor 1 Newspaper spend

Comp1OOH-Competitor 1 Outdoor ad spend

Comp2NP-Competitor 2 Newspaper spend

## Project Objectives

Identify seasonality and trends in soda sales.

Analyze the correlation between Sales Volume and marketing spend.

Explore the impact of pricing and promotions on sales.

Use partial correlation to isolate effects of media.

Transform TVGRP data into Adstock to account for carryover and saturation effects.

Assess the influence of competitor advertising on sales.

## Techniques Used

1. Seasonality Analysis
Created a pivot table of SalesVol by Month (Jan–Dec).

Line charts revealed recurring seasonal peaks, especially in summer months.

2. Trend Analysis
Inserted a linear trendline on monthly sales chart.

Identified slight downward movement over time.

3.Correlation Analysis
Used Excel's CORREL() function to compute correlation between SalesVol and:

TVGRP, Instoreads, Outdoorads, Digitalads

Price (negative correlation observed)

Promotions (positive correlation observed)

 4. Partial Correlation
Used residual method: regressed SalesVol and Promotions separately on media variables.

Took residuals and calculated correlation → e.g., 2.95E-16 suggests almost zero net effect after accounting for media.

5. Adstock Transformation
Calculated Adstock using:

Copy
Edit
Adstock(t) = L * Adstock(t-1) + [GRP(t)^n / (GRP(t)^n + k^n)]
Where:

L = carryover (0 to 1)

n = saturation parameter

k = saturation constant
Created Adstock column using Excel formula with recursive logic.

6. Competitor Impact Analysis
Correlated competitor spends (Comp1TV, Comp1NP, etc.) with SalesVol.

Found Comp1 Outdoor Ads (r = −0.34) and Comp1 TV (r = −0.24) had strongest negative effect.

## Key Findings

Insight	Description
Seasonality	Clear seasonal peaks during summer months.
Trend	Slight downward trend in sales over time.
Media Correlation	TV and Outdoor ads strongly correlated with SalesVol.
Promotions	Positive correlation with sales; less effective when media effects are removed (partial correlation ≈ 0).
Price Impact	Higher prices associated with lower sales (moderate negative correlation).
Competitor Effect	Competitor 1’s Outdoor and TV ads reduced our sales the most.

