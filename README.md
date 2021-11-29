# SPAPD

A method for detecting sentiment-driven pricing that combines existing anomaly
pattern detection methodology with sentiment analysis models. The model is named **Sentiment-driven
Pricing Anomaly Pattern Detection (SPAPD)**.

## Background

In January of 2021, retail investors on social media carried
out the first-ever case of predatory trading.
Rallied under posts published on subreddit
r/WallStreetBets, these retail investors traded
collaboratively in the same direction, which
caused the price of GameStop stock to go up
from $20 to $347 in less than 2 weeks, hence
inflicting heavy losses on institutional hedge
funds and short sellers. Sentiment Driven Pricing is a term that first
featured in a paper on GameStop returns and
impacts of media-driven sentiments by Umar
et al. (2021), which were used to describe
stock price returns induced by investor
sentiments on social media platforms.

This research acknowledge the
positive contributions of the event, but argues
such event is not healthy for the financial
market in the long run, because retail
investors are more easily affected by
emotions and biases that can cause price to
derive from its fundamentals, thus leading to
market inefficiency. Therefore, this research
proposed and tested a methodology that
detects sentiment-driven pricing. The goal is
to help regulators and policymakers
monitoring the market, so they can respond
fast to potential cases of sentiment-driven
pricing and minimise the negative impacts.

## Methodology 

SPAPD is made up of three components, namely:

1. **Anomaly pattern detection model:** an anomaly pattern detection model based on
the proposed method of APD-HT by Kim and Park (2020)
2. **Two sentiment analysis models:** one checks for the presence of a crisis environment and the other detects abnormality in
investor attention on social media
3. **Cross verification:** uses results from the 2nd component to verify anomaly detected by the 1st 
component to see if it characterises as a sentiment-driven pricing

![alt text](images/methodology.png) 

## Results 

![alt text](images/results_detections.png) 

Above table shows the number of times an
anomaly was successfully signalled between
01/01/2021 and 21/01/2021, which are
considered to be the preliminary phase of the
GameStop Short Squeeze, as investor
attention gradually accumulated during this
period but share price has yet burst out of
control. It is shown that SPAPD using return as input
significantly outperforms other alternatives at
making early detection. It is also shown SPAPD is consistent as the
results are either 0 or 100 out of 100 run.

![alt text](images/results_charts.png) 

It is shown in charts above that all DTW
(Dynamic Time Wrapping used in clustering)
variants outperforms their ED (Euclidean
Distancing used in clustering) counterparts,
and those use return as input significantly
outperforms those use normalised adjusted
closing price as input, except for the baseline
KNN model.

## Research Implications 

SPAPD is the first known attempt to target
sentiment-driven pricing using anomaly pattern
detection method and sentiment analysis. Results
from the study shows it is possible to treat
sentiment-driven pricing as anomaly and apply
existing anomaly detection methodologies to
detect them.

The study also shows sentiment analysis can be
used to capture the contextual background of a
pricing anomaly, which can have a wide range of
application including identify the presence of a
crisis environment in the financial market, or
unusual amount of investor attention towards
certain stocks on social media.

This study may serve as prototype to future
solutions that predicts sentiment-driven pricing,
as public sentiments on social media getting
more influential, there is no guarantee that
events like GameStop would not be a recurring
phenomenon.

## Dependencies

- [Python 3](http://www.python.org)
- [Numpy](http://www.numpy.org)
- [Matplotlib](https://matplotlib.org)
- [SciPy](https://www.scipy.org)

The code in this repository requires Python 3.9 or later.

It is strongly recommended to run the the code from inside a virtual environment. The required packages can be installed to the environment with pip install -r requirements.txt.

## References

1. Kim, T., & Park, C. H. (2020). Anomaly pattern detection for
streaming data. Expert Systems with Applications, 149, 113252.
2. Umar, Z., Gubareva, M., Yousaf, I., & Ali, S. (2021). A tale of company
fundamentals vs sentiment driven pricing: The case of GameStop.
Journal of Behavioral and Experimental Finance, 100501.
