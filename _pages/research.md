---
title: "Physics of Social Systems - Research"
layout: textlay
excerpt: "Physics of Social Systems -- Research"
sitemap: false
permalink: /research/
---

# Research

## Sustainable Mobility On-Demand / Ride-Pooling Dynamics

On-demand ride-pooling services have the potential to drastically decrease urban traffic, mobility costs, carbon emissions and the need for owning a private car. In order to analyze and design on-demand ride-pooling dynamics, we develop and enhance analytical theories and also run numerical simulations.
References: [[1]](https://www.sciencedirect.com/science/article/pii/S0965856417316038), [[2]](https://www.pnas.org/content/114/3/462.short), [[3]](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.125.248302), [[4]](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.125.248302), [[5]](https://ieeexplore.ieee.org/abstract/document/6544843)

Our custom-made simulation framework is written in [Julia](https://docs.julialang.org/en/v1/), runs on [OpenStreetMaps](https://www.openstreetmap.org) and is under active development:
|| |
|-|-|
| ![](https://pad.gwdg.de/uploads/upload_c9944825fcfdd4d847a02145c15a7f3b.gif) | ![](https://pad.gwdg.de/uploads/upload_5ba304c3ae4f33e7c2ae3bc3730d9fe6.gif) |

The project ideas below are still on our todo-list and are potentially well-suited for potential Bachelor and Master thesis'.

#### Non-uniform pickup/dropoff distributions
Each transport request consists of two locations: the sites for pickup (stars in .gif above) and dropoff (triangles) of the respective customer (color). While we currently draw both locations from a uniform distribution on the underlying street map, it is clear that this procedure should be improved. Firstly, the two locations are not independent but the distance between them follows e.g. an inverse Gamma distribution ([[1]](https://www.sciencedirect.com/science/article/pii/S0965856417316038), [[2]](https://en.wikipedia.org/wiki/Inverse-gamma_distribution)). Secondly, in reality there may be train stations, theaters, airports etc. which present natural hotspots and should be taken into account.

*How does the shareability of requests change when their pickup or dropoff locations tend to coincide? 
How much more efficiently can a system be operated when a certain amount of information/entropy is contained in the spatial distributions?*

#### Graph centrality
After finishing their job by dropping of the last passenger on board, buses often become idle in remote areas. This is clearly disadvantageous as it hinders them from quickly getting to the next pickup-destination assigned to them.
Keyword: [graph centrality](https://en.wikipedia.org/wiki/Centrality)

*Given a street map (graph), can we predict which nodes are often travelled through, or most likely to be temporally close to incoming requests?
Can they be learned from simulated trajectories?
Should idle buses relocate to hotspots per default?*

#### Speed-up heuristics
When a new request is submitted, the algorithm minimizes a cost function on the set of all possible insertions. For many buses and frequent requests, this progress quickly becomes numerically expensive. The main reason for this is that -currently- all possible insertions are checked and evaluating the cost function over and over requires repeated route finding on a graph ([[1]](https://en.wikipedia.org/wiki/A*_search_algorithm), [[2]](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm)).

*Which options can be quickly discarded?
How much quicker can clever heuristics make a simulation [[1]](https://arxiv.org/abs/2007.14877)?
What's the tradeoff between computational speed and service quality?
Can frequently travelled fastest-routes be [precalculated](https://ieeexplore.ieee.org/abstract/document/6544843) using a coarse-grained grid?*

#### Rush-hour relaxation
Given the request frequency and spatial distribution, it is possible to predict the fleet size required to serve the demand in a steady state. In reality, the demand depends on the time of the day as clearly more people require mobility in the afternoon than at 3am.

*Can we quantify the robustness of the system against peaks of incoming requests?
What are good strategies to have enough capacity in peak hours, but not overly many idle buses during times of low demand?*

#### Re-ordering bus' to-do lists
When a new request comes in and is assigned to a bus, the relative order of already-assigned jobs (picking up and dropping off users) remains unchanged (so far). Yet given the new set of tasks, it may be advantageous to re-optimize the order with which a vehicle performs its assigned jobs.

*Is the extra efficiency worth the numerical effort?
Is the computational problem even feasible for large systems?*
