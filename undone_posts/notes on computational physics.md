Her kan bruke sharelatex; fagene til Hermann og CQM 



## Bootstrap and Resampling (also useful in Machine Learning)
We have some observations of something, n samples.
* Find the the properties of the observed distribution (mean, std etc). Say all this info is in S
* Then what is the TRUE error?
* Assume that all samples are IID and we can do bootstrap resampling
* We now resample, using properties from the observed distribution, with replacement (so can get 1 value more than once)
* From the resample, we get different statistics S*, not same as S (or could be). When we do this again, we get another S** and so on.
* So doing this many times, we get a distribution of estimates of S!
* Can plot histogram of all S. Then we will expect something quite Gaussian (since resampeled from same sample). Lets say our mean of the distribution of S is S_bar. Then we can calculate sigma^2_boot = (sum of i=1 to i=B (S^i - S^i_bar)^2) / (B-1), where B is the number of bootstraps. 
* So what have we done? We have got the shape of parent distribution, without really knowing it!

See also https://www.youtube.com/watch?v=gcPIyeqymOU and https://www.youtube.com/watch?v=tTZybQTE0dw
