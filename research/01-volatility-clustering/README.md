# Volatility Forecasting: S&P 500

## Overview

This project investigates whether historical patterns in S&P 500 returns can help forecast future volatility out of sample.

It compares four approaches: historical variance, rolling variance, EWMA and GARCH(1,1).

## Research Questions

1. Do daily returns show little linear autocorrelation while their squared values show dependence?
2. Do time-varying variance forecasts improve on a constant historical-variance benchmark out of sample?
3. Does GARCH(1,1) achieve lower QLIKE loss than EWMA on the test period?

## Data

- **Asset:** S&P 500 Index (`^GSPC`)
- **Source:** Yahoo Finance (`yfinance`), read from a local snapshot `data/GSPC.csv` (downloaded 2026-11-23, 4,217 rows). The snapshot is not committed, because Yahoo's terms restrict redistribution. The notebook records its SHA-256 checksum, shows the download code that recreates it, and stops if the file doesn't match. Yahoo can revise history, so a new download may differ.
- **Period:** January 2010 - October 2026
- **Evaluation:** Chronological training, validation and test periods

## Methodology

The analysis examines volatility clustering and compares forecasts using mean squared error (MSE) and quasi-likelihood loss (QLIKE).

## Main Findings

GARCH(1,1) achieved the lowest out-of-sample MSE and QLIKE among the four approaches tested, and its QLIKE advantage over EWMA was significant at the 5% level in a Diebold–Mariano-style test. These findings are specific to the sample and model configurations used.

## Reproducing the Analysis

From the repository root, activate the virtual environment and install the dependencies as described in the main README. Then open this notebook and run its cells.

## Full Article

[Read the research article](https://laurasalop03.github.io/blog/posts/01_volatility_clustering.html)

## Limitations

This project evaluates volatility forecasting, not return predictability or the profitability of a trading strategy.