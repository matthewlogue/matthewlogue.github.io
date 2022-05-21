## Project Pitch

This week, we have been exploring different algorithms and their uses, with the aim of choosing one to focus on for our project. Ultimately we have decided to attempt to improve the prior used by [PBJam](https://github.com/grd349/PBjam). PBJam is a python library that is used to apply Bayesian Inference in the field of asteroseismology.

### Asteroseismology
In the same way that sound waves bounce around the inside of a flute, there are also sound waves travelling through the insides of stars. These sound waves cause the surface of a star to oscillate, and these oscillations can be studied to determine the properties of a particular star. For example, the frequency of oscillations can be used to determine the speed of sound inside a star, which in turn provides information about its chemical composition. One of the things that affects the oscillations of a star is the location of convective zones inside a star. PBJam focuses on modelling stars with a convective region just under the stellar surface, as our Sun is one of these stars.

### Bayesian Inference
In order to understand the approach taken by PBJam to study asteroseismology, we should first understand the basics of Bayesian Inference, in which we want to calculate the probability that a particular model is the correct one to describe a set of data.

We start with Bayes' theorem

<p align="left">
  <img src="/img/bayes.png"
       width="500"/>
</p>

where the posterior represents the probability that our model correctly describes the data and is obtained from

- the likelihood, which represents the probability that we would collect our data given our model
- the prior, which represents how likely we believe our model to be before we have collected any data
- and the evidence, which ensures that the posterior distribution is normalised.

Since we estimate the prior before collecting any data, our choice is somewhat arbitrary. This means we can experiment with different models to find one that seems to give sensible results.

### Our work with PBJam
PBJam uses a kernal density estimator (KDE) to calculate its estimate of the prior distribution. A more detailed explanation of how this works can be found [here](https://en.wikipedia.org/wiki/Kernel_density_estimation), but for now we only need to consider the run time of the KDE. Due to its reliance on linear algebra, the KDE has a run time which scales as O(n). Since stellar databases are typically made of thousands of stars (the Kepler telescope observed over 500,000 stars in its 9 year lifespan), it isn't feasable for PBJam to run the KDE across the whole dataset. To get around this, PBJam only considers a subset of stars when constructing its prior, specifically the stars closest to us. However this means that if there are differences between these stars, and stars that are further away, these differences will not be captured by the prior. Therefore it would be ideal if we could use machine learning to find a faster algorithm to estimate the prior.

### Further analysis
Another difficulty faced by PBJam, is that while the l=0, and l=2 mode oscillations occur with a relatively well-known pattern, the l=1 mode is more complicated. This is partly because the l=1 mode couples to gravitational, or g-modes, and partly because it gets split by the rotation of a star around its axis. These means that it is difficult to determine the values of parameters used in models of this mode. Since machine learning is suited to fitting model parameters to big data sets, this is a problem we intend to try to solve if we successfully speed up the prior estimation used by PBJam.
