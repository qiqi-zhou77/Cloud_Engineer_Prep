# Cloud Monitoring
- SLO: Service Level Objectives
- Works in hybrid env: with support for gcp, aws, and on prem

## Creating Dashbaord
## Usimg Metric Exporer
## Creating Alters
- policy: condition type= threshold or metric absent


# Cloud Logging

## Log Routers and Log Sinks
- log data is ingested by cloud logging api, then routed to sinks
- Required log sink, Default log sink, user defined log sink
- Google creates a required and a default sink for each billing account prohect folder or organization



## Configuring Log Sinks
- log sinks is a service that receives log messages and applies inclusion and exclusion filters to determine which log sinks whould receive the message
- Required Log sink is used to store admin activities, system events and access transparency logs: 400 days
- Default: 30 days, if lopnger is required, sent to cloud storage or BigQuery



## Viewing and Filtering Logs

## Viewing Message Details

# Using Cloud Diagnostics
- GCP provides diagnostic tools that software developers can use to collect information about the performance and functioning of the applications

## Overview of Cloud Trace
- Collecting latency time of app,so that dev knows where app are spending their time and to identify cases where performance is degrading

## Viewing Google Cloud Status




# Using Pricing Calculator