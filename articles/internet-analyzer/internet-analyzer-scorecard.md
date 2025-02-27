---
title: 'Interpreting your Scorecard | Microsoft Docs'
description: Learn how to interpret your scorecard. The scorecard tab contains the aggregated and analyzed results from your tests.
services: internet-analyzer
author: KumudD

ms.service: internet-analyzer
ms.topic: how-to
ms.date: 10/16/2019
ms.author: kumud
---
# Interpreting your scorecard

[!INCLUDE [Azure Internet Analyzer retirement notice](../../includes/internet-analyzer-retirement.md)]

The scorecard tab contains the aggregated and analyzed results from your tests. Each test has its own scorecards. Scorecards provide quick and meaningful summaries of measurement results to provide data-driven results for your networking requirements. Internet Analyzer takes care of the analysis, allowing you to focus on the decision.

The scorecard tab can be found in the Internet Analyzer resource menu. 


## Filters

* ***Test:*** Select the test that you’d like to view results for - each test has its own scorecard. Test data will appear once there's enough data to complete the analysis – in most cases, this should be within 24 hours. 
* ***Time period & end date:*** Three scorecards are generated daily – each scorecard reflects a different aggregation period – the 24 hours prior (day), the seven days prior (week), and the 30 days prior (month). Use the “End Date” filter to select the last day of the time period you want to see. 
* ***Country:*** For each country that you have end users, a scorecard is generated. The global filter contains all end users.

## Measurement count

The number of measurements impacts the confidence of the analysis. The higher the count, the more accurate the result. At minimum, tests should aim for a minimum of 100 measurements per endpoint per day. If measurement counts are too low, please configure the JavaScript client to execute more frequently in your application. The measurement counts for endpoints A and B should be very similar although small differences are expected and okay. In the case of large differences, the results shouldn't be trusted.

## Percentiles

Latency, measured in milliseconds, is a popular metric for measuring speed between a source and destination on the Internet. Latency data isn't normally distributed (i.e. doesn't follow a "Bell Curve") because there's a "long-tail" of large latency values that skew results when using statistics such as the arithmetic mean. As an alternative, percentiles provide a "distribution-free" way to analyze data. As an example, the median, or 50th percentile, summarizes the middle of the distribution - half the values are above it and half are below it. A 75th percentile value means it's larger than 75% of all values in the distribution. Internet Analyzer refers to percentiles in shorthand as P50, P75, and P95.

Internet Analyzer percentiles are _sample metrics_. This is in contrast to the true _population metric_. For example, the daily true population median latency between students at the University of Southern California and Microsoft is the median latency value of all requests during that day. In practice, measuring the value of all requests is impractical, so we assume that a reasonably large sample is representative of the true population.

For analysis purposes, P50 (median), is useful as an expected value for a latency distribution. Higher percentiles, such as P95, are useful for identifying how high latency is in the worst cases. If you're interested in understanding customer latency in general, P50 is the correct metric to focus on. If you're concerned with understanding performance for the worst-performing customers, then P95 should be the focus. P75 is a balance between these two.


## Deltas

A delta is the difference in metric values for endpoints A and B. Deltas are computed to show the benefit of B over A. Positive values indicate B performed better than A, whereas negative values indicate B's performance is worse. Deltas can be absolute (for example, 10 milliseconds) or relative (5%).

## Confidence interval 

Confidence intervals (CI) are a range of values that have a probability of containing the population metric such as median, P75, or average. We follow the common statistical convention of using the 95% CI.

For Internet Analyzer, a narrow confidence interval is good because it shows the sample metric is likely very close to the actual population metric. A wide confidence interval means less certainty that our sample metric reflects the true population metric. The best way to improve the CI is to increase measurement counts.

## Time series 

A time series shows how a metric changes over time. On the Internet, there are many temporal factors that impact performance such as peak traffic periods, weekday-weekend population differences, and holidays.


## Next steps

To learn more, see our [Internet Analyzer Overview](internet-analyzer-overview.md).
