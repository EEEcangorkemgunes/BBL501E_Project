# Waiting-Time Dependent Mortality in a Single-Server Emergency Unit

This repository contains the analytical and numerical implementation of the term project  
_“Waiting-Time Dependent Mortality in a Single-Server Emergency Unit with Heterogeneous Patients”_,  
prepared for _BBL 501E – Probability and Stochastic Processes (2025–2026 Fall Semester)_ at Istanbul Technical University.

## Project Overview

The project studies how _waiting time and service-time heterogeneity_ affect patient mortality risk in a congested emergency surgical unit.  
The system is modeled as a _single-server M/G/1 queue_ with two heterogeneous patient classes:

- _Type A (Standard cases)_: frequent, short, exponential service times
- _Type B (Complex cases)_: rare, long, Erlang-2 service times

Mortality risk is modeled as a *time-dependent function of total system time, motivated by the clinical *golden hour concept.

All results are derived _analytically_, without simulation-based estimation.

## Modeling Assumptions

- Poisson arrivals with rates λ<sub>A</sub> and λ<sub>B</sub>
- Single non-preemptive server (FCFS discipline)
- Infinite waiting capacity
- System stability condition: ρ < 1
- Independent arrivals and service times
- Time-dependent mortality model:

  \[
  P(\text{Death} \mid H = t) = 1 - e^{-\alpha t}
  \]

where \( H = W + S \) is the total system time.

## Methodology

The analysis relies on _Laplace–Stieltjes Transforms (LST)_ and classical queueing theory:

- Service-time LSTs for exponential and Erlang-2 distributions
- Waiting-time LST via the Pollaczek–Khinchine formula
- Closed-form expressions for:
  - \( P(\text{Death} \mid \text{Type A}) \)
  - \( P(\text{Death} \mid \text{Type B}) \)
- Bayesian inference for:
  - \( P(\text{Type B} \mid \text{Death}) \)

Numerical results are obtained using a representative congested-system parameter set.

## Results Summary

- Type B patients experience _systematically higher mortality risk_
- Increased risk arises purely from _service-time heterogeneity_, despite identical waiting-time distributions
- Posterior probability of a patient being Type B increases when conditioned on death
- Visual analysis confirms stronger overlap between Type B system-time distribution and high-risk regions
