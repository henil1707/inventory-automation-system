# Inventory Automation System

## Overview

This project is a Python-based inventory automation system built using Jupyter Notebook. It analyzes batch-wise stock data, predicts demand, identifies risks, and generates actionable inventory alerts.

## Key Modules

### Stock Intelligence

* Fast, slow, and dead stock classification
* Stock velocity and movement analysis
* Non-moving stock detection

### Expiry Management

* Expiry tracking at batch level
* Expiry bucket segmentation (0–60, 61–90, 91–180, >180 days)
* Expired stock identification

### Risk & Alerts Engine

* Risk scoring and risk status classification
* Return-heavy product detection
* Automated stock alerts and reorder recommendations

### Forecasting

* 30/60/90-day sales trends
* Product-level demand forecasting
* Safety stock and reorder quantity calculation

## Outputs

* Stock alert report
* Expiry breakdown report
* Reorder recommendations

## Tools Used

* Python
* Pandas
* Jupyter Notebook
