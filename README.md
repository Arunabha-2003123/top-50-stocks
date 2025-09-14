# top-50-stocks
This is a followup code from a video :Algorithmic Trading – Machine Learning &amp; Quant Strategies Course with Python
(https://www.youtube.com/watch?v=9Y3yaoi9rUQ)
A few critical issues to highlight:
1. RSI is not normalized, which becomes the dominant feature during k-means clustering (euclidean based), and the rest features are just noise
2. When joining betas with technical indicators, the shift makes future month NaN which was later imputed by mean; however, by default the future month should be values shifted from previous month
3. Normalization of features are using std and var produced from entire population, and this will induce look-ahead biases during backtest
4. For monthly resample, technical indicators should be calculated directly from monthly prices, instead of resampled from daily technical indicators
These issues are really critical btw. The backtest result could be completely different after implementing fixing.
told by @MrSonglu in the comments I just implemented those 
fetching data from y fincane used agglomerative clusting to detect patterns and built porfolio on it. 
