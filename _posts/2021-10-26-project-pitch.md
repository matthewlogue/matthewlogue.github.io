## Project Pitch

This week, we have been exploring different algorithms and their uses, with the aim of choosing one to focus on for our project. Ultimately we have decided to attempt to improve the prior used by [PBJam](https://github.com/grd349/PBjam). PBJam is a python library used to model the oscillation of stars, in particular, stars which have a convective region just below their surface.

### Bayesian Inference
In order to understand the approach taken by PBJam, we should first understand the basics of Bayesian Inference, in which we want to calculate the probability that a particular model is the correct one to describe a set of data.

We start with Bayes' theorem

![Bayes_theorem](https://latex.codecogs.com/svg.latex?P(\theta|d)&space;=&space;\frac{\mathcal{L}(d|\theta)\pi(\theta)}{Z}),

where the posterior, ![posterior](https://latex.codecogs.com/svg.latex?P(\theta|d)) represents the probability that our model correctly describes the data and is obtained from

- the likelihood, ![likelihood](https://latex.codecogs.com/svg.latex?\mathcal{L}(d|\theta)) which represents the probability that we would collect our data given our model
- the prior, ![prior](https://latex.codecogs.com/svg.latex?\pi(\theta)) which represents how likely we believe our model to be before we have collected any data
- and the evidence, Z which ensures that the posterior distribution is normalised.

Since the prior encodes how likely we believe our model is before we have any data, our choice is somewhat arbitrary 


<p align="center">
  <img src="/img/2021-10-10_dec_tree_reg_imgs/dec_tree_schem.png"/>
</p>

img/2021-10-10_dec_tree_reg_imgs/
