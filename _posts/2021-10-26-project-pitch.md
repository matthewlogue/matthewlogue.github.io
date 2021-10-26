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

Since we estimate the prior before collecting any data, our choice is somewhat arbitrary. This means

### Further analysis
- the l=1 mode
