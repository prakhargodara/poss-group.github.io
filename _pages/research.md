---
title: "Physics of Social Systems - Research"
layout: textlay
excerpt: "Physics of Social Systems -- Research"
sitemap: false
permalink: /research/
---

# Research

## Sustainable Mobility On-Demand / Ride-Pooling Dynamics

On-demand ride-pooling services have the potential to drastically decrease urban traffic, mobility costs, carbon emissions and the need for owning a private car. In order to analyze and design ride-pooling dynamics, we develop and enhance analytical theories and also run numerical simulations.
References: [[1]](https://www.sciencedirect.com/science/article/pii/S0965856417316038), [[2]](https://www.pnas.org/content/114/3/462.short), [[3]](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.125.248302), [[4]](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.125.248302), [[5]](https://ieeexplore.ieee.org/abstract/document/6544843)

Our custom-made simulation framework is written in [Julia](https://docs.julialang.org/en/v1/), runs on [OpenStreetMaps](https://www.openstreetmap.org) and is under active development. The project ideas below are still on our todo-list and are potentially well-suited for potential Bachelor and Master thesis'.

![]({{ site.url }}{{ site.baseurl }}/images/respic/mobility1.gif){: style="width: 500px; float: right; margin: 0px 10px"}
![]({{ site.url }}{{ site.baseurl }}/images/respic/mobility2.gif){: style="width: 500px; float: right; margin: 0px 10px"}


**Non-uniform pickup/dropoff distributions**: Each transport request consists of two locations: the sites for pickup (stars in .gif on the right) and dropoff (triangles) of the respective customer (color). While we currently draw both locations from a uniform distribution on the underlying street map, it is clear that this procedure should be improved. Firstly, the two locations are not independent but the distance between them follows e.g. an inverse Gamma distribution ([[1]](https://www.sciencedirect.com/science/article/pii/S0965856417316038), [[2]](https://en.wikipedia.org/wiki/Inverse-gamma_distribution)). Secondly, in reality there may be train stations, theaters, airports etc. which present natural hotspots and should be taken into account.

*How does the shareability of requests change when their pickup or dropoff locations tend to coincide? 
How much more efficiently can a system be operated when a certain amount of information/entropy is contained in the spatial distributions?*

**Graph centrality**: After finishing their job by dropping off the last passenger on board, buses often become idle in remote areas. This is clearly disadvantageous as it hinders them from quickly getting to the next pickup-destination assigned to them.
Keyword: [graph centrality](https://en.wikipedia.org/wiki/Centrality)

*Given a street map (graph), can we predict which nodes are often travelled through, or most likely to be temporally close to incoming requests?
Can they be learned from simulated trajectories?
Should idle buses relocate to hotspots per default?*

**Speed-up heuristics**: When a new request is submitted, the algorithm minimizes a cost function on the set of all possible insertions. For many buses and frequent requests, this progress quickly becomes numerically expensive. The main reason for this is that -currently- all possible insertions are checked and evaluating the cost function over and over requires repeated route finding on a graph ([[1]](https://en.wikipedia.org/wiki/A*_search_algorithm), [[2]](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm)).

*Which options can be quickly discarded?
How much quicker can clever heuristics make a simulation [[1]](https://arxiv.org/abs/2007.14877)?
What's the tradeoff between computational speed and service quality?
Can frequently travelled fastest-routes be [precalculated](https://ieeexplore.ieee.org/abstract/document/6544843) using a [coarse-grained grid](https://en.wikipedia.org/wiki/Contraction_hierarchies)?*

**Rush-hour robustness**: Given the request frequency and spatial distribution, it is possible to predict the fleet size required to serve the demand in a steady state. In reality, the demand depends on the time of the day as clearly more people require mobility in the afternoon than at 3am.

*Can we quantify the robustness of the system against peaks of incoming requests?
What are good strategies to have enough capacity in peak hours, but not overly many idle buses during times of low demand?*

**Re-ordering bus' to-do lists**: When a new request comes in and is assigned to a bus, the relative order of already-assigned jobs (picking up and dropping off users) remains unchanged (so far). Yet given the new set of tasks, it may be advantageous to re-optimize the order with which a vehicle performs its assigned jobs.

*Is the extra efficiency worth the numerical effort?
Is the computational problem even feasible for large systems?*

## Social Networks

<p align="center">
  <img src="{{ site.url }}{{ site.baseurl }}/images/respic/users-by-social-media-platform.png" 
  alt="Social media usage" width="700" />
<br>
*Figure: Evolution of social media, taken from [Our World in Data](https://ourworldindata.org/rise-of-social-media).*
</p>

Social networks have transformed the world, becoming the main way opinion is formed in our modern society (see Fig. 1). They bring a completely new set of societal challenges, as they can be used to manipulate opinion on a much larger scale than previously possible. We aim to use concepts from physics and network theory to understand how opinions spread in social networks. We focus on large and influential platforms, backing our modeling with large-scale data analysis. We are particularly interested in the following topics:

**Discussion dynamics in Reddit communities**: [Reddit](https://www.reddit.com/) is one of most influential social media platforms in the world, and individual Reddit communities have been involved in some of the biggest social events in recent times (such as [The_Donald](https://en.wikipedia.org/wiki/R/The_Donald) and [wallstreetbets](https://en.wikipedia.org/wiki/R/wallstreetbets)). We use percolation models and data analysis to quantify how the discussion dynamics differs between communities. References: [[1]](https://www.dpg-verhandlungen.de/year/2021/conference/bpcppdysoe/part/soe/session/3/contribution/7?lang=en), [[2]](https://academic.oup.com/comnet/article/7/1/67/4991998).

**Polarization and social tipping**: We live in an increasingly polarized world. We are interested in models that reproduce such macroscopic polarization from microscopic mechanisms, and that offer insights into how polarization can be tackled. Related to polarization is [social tipping](https://en.wikipedia.org/wiki/Tipping_point_(sociology)), which refers to drastic changes in collective societal behavior. We are interested in the role of phase transition models in explaining social tipping. References: [[3]](https://link.aps.org/doi/10.1103/PhysRevX.11.011012),[[4]](http://www.nature.com/articles/s41598-020-67102-6).


**Fake news spreading on Twitter**: Fake news have a large impact on modern society. They have been used to hack elections, promote conspiracy theories and create social polarization. On Twitter, fake news have been observed to spread in a coordinated manner through the use of bots. We are interested in characterizing fake news on Twitter from its dynamical and topological spreading patterns. Reference: [[5]](https://www.sciencemag.org/lookup/doi/10.1126/science.aap9559).
