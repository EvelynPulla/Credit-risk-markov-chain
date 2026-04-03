# Credit Risk Modeling with Markov Chains

## Overview

This project models credit rating transitions using a discrete-time Markov chain and applies Monte Carlo simulation to estimate default risk and credit default swap (CDS) premiums.

The goal is to understand how credit risk evolves over time and quantify its financial impact.

## Model Description
	•	Each credit rating is treated as a state:
        AAA, AA, A, BBB, BB, B, CCC/C, D, NR
	•	Transitions between ratings are modeled using a transition probability matrix
	•	Default states: D and NR

The model assumes:

The next credit rating depends only on the current rating (Markov property)

## Methodology

1. Markov Chain Modeling
	•	Constructed a one-year transition matrix
	•	Computed multi-period transitions using matrix powers P^n

2. Monte Carlo Simulation
	•	Simulated 100,000+ paths
	•	Modeled credit evolution over a 10-year horizon
	•	Estimated expected present value of CDS contracts

3. CDS Pricing

Fair premium computed as:

$$x^* = \frac{\mathbb{E}[\text{payout leg}]}{\mathbb{E}[\text{premium leg}]}$$

## Key Results


| Rating | Fair Premium |
|--------|-------------|
| AAA    | 0.0000      |
| AA     | 1.1789      |
| A      | 2.4692      |
| BBB    | 4.4258      |
| BB     | 10.5715     |
| B      | 18.7952     |
| CCC/C  | 50.9801     |
	•	Default risk increases as credit rating deteriorates
	•	Speculative-grade firms show significantly higher risk
	•	CDS premiums reflect expected default losses

## Default Risk Analysis

The model also estimates multi-year default probabilities:

	•	Default probability increases non-linearly over time
	•	Lower-rated firms (B, CCC/C) exhibit rapid risk escalation
	•	Investment-grade firms maintain low long-term default risk

## Financial Interpretation

The model can be extended to compute Expected Loss (EL):

$$EL = PD \times Exposure \times LGD$$

This connects the model to real-world risk management and pricing.

## Technologies Used
	•	Python
	•	NumPy
	•	Pandas
	•	Matplotlib
	•	Monte Carlo Simulation
