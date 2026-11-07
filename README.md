# pricing-ab-test-delivery-fee.
A/B test of a tiered delivery fee: +18.7% orders, +21.3% revenue (Python).
Pricing A/B Test: Delivery Fee Optimization

Goal: find a delivery fee set-up that keeps revenue the same (or higher) while getting more orders.

## Data
18,006 orders over 31 days (8,232 Control, 9,774 Test). Control charges a flat fee of 2.29. Test charges nothing on baskets of 33+ and a higher fee below that. Revenue = order value x 20% + delivery fee.

## What I did
- Validated the data (no nulls or duplicates) and checked the revenue formula on every row
- EDA by hour of day, morning vs evening, and fee vs revenue
- A/B tests: Welch t-test, Mann-Whitney, bootstrap CI, Levene's test
- Segment view: orders below and above 33, and hour by hour

## Results
- Orders +18.7%, total revenue +21.3%, revenue per order +2.1% (p = 0.008)
- Free delivery on 33+ orders: +47% orders, +28% revenue in that segment
- Average order value rose 8.8%, driven by more large baskets, not bigger baskets

## Limitations
No visitor counts, so the order lift assumes similar traffic in both groups. One month of data. No delivery cost data, so revenue is not profit.

## Files
- EDA2_Pricing_AB_Test.ipynb: full analysis
- charts/: all charts used

## Tools
Python (Pandas, NumPy, SciPy, Matplotlib), Jupyter
