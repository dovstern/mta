# mta
Multi-Touch Attribution. Find out which channels contribute most to user conversion. This repo extends the implementation in https://github.com/eeghor/mta by applying so-called Simple Probabilistic Attribution Model by Shao and Li at the user/lead-path level, as opposed to just aggregate level attribution breackdown as found in that implementation. See mta/shao_user_level_output.py for this addition.


### Included Data

The package comes with the same test data set as an R package called [ChannelAttribution](https://cran.r-project.org/web/packages/ChannelAttribution/ChannelAttribution.pdf)  - there are 10,000 rows containing customer journeys across 12 channels: alpha, beta, delta, epsilon, eta, gamma, iota, kappa, lambda, mi, theta and zeta.

![data_snippet](img/data_snippet.png)

These are conversion aggregations by path. Suppose  there’s a path  (customer journey)
```
a > b > c
```
with **total_conversions** equal to 2 and **total_null** equal to 5. This means that we recorded 2 consumer journeys
```
a > b > c > (conversion)
```
and 5 customer journeys 
```
a > b > c > (null)
```

There’s an option to generate timestamp data if you want to use the Additive Hazard model (the only model that explicitly incorporates exposure times).

### References

* Shao and Li (2011)  - Data-driven Multi-touch Attribution Models [pdf](http://www0.cs.ucl.ac.uk/staff/w.zhang/rtb-papers/data-conv-att.pdf)
