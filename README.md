Green Hydrogen Production Optimization
This repository contains the code and models developed for optimizing the allocation of renewable energy (wind/solar) to hydrogen production and electricity sales, considering uncertain power input and dynamic hydrogen pricing.

Problem Overview
The goal of this project is to optimize revenue from green hydrogen production by determining the optimal distribution of renewable energy between hydrogen production (for two customers) and electricity sales to the grid. The optimization problem considers:

Uncertainty in renewable energy supply.
Dynamic pricing for two categories of hydrogen:
H1 (higher price, promised to Customer 1).
H2 (excess production, sold at a lower price to Customer 2).
15-minute time step scheduling.
Probability-based constraints ensuring the promise to Customer 1 is met with a certain confidence level (e.g., 90%).
Key Features
Optimization Model: A linear programming approach (using scipy.optimize.linprog) is used to maximize revenue.
Revenue Maximization: The model maximizes profits from selling electricity and hydrogen under capacity constraints.
Dynamic Hydrogen Pricing: The price for hydrogen varies depending on the amount produced and promised quantities.
Uncertainty Handling: Production is modeled with probability distributions, allowing for risk-adjusted pricing.


Inputs
Time-series power forecast (from renewable energy sources).
Prices for electricity and hydrogen (for both customers).
Capacity constraints for electrolyzer, storage, and customer demands.
Probability thresholds for fulfilling customer promises (e.g., 90% probability for promised hydrogen).

Outputs
Optimal power allocation to hydrogen production and electricity sales.
Scheduled hydrogen distribution to two customers.
Surplus electricity and hydrogen (if any).
Total revenue generated.


Requirements
Python 3.7+
Required libraries:
numpy
pandas
scipy


Example Usage
A simulated daily power schedule with 15-minute intervals is used for demonstration. The code iterates over the time series to compute the optimal allocation and price-sensitive hydrogen distribution.
