---
title: "Running Simulations in Sequence with varying parameters"
date: 2024-05-30
---

# Description

In particle physics, we run a lot of simulations of our experiments whether they are still being developed or are already built and currently running. 
Sometimes simulations (such as oscillation analysis) are developed from scratch, but most often we use pre-existing packages such as Geant4. 
Geant4 package is used to simulate a passage of different types of particles through different types of matter. It is written in C++, utilizing ROOT package.
We typically build simulation of each experiment, inserting geometric and material parameters in Geant4, creating a unique simulation of our particular experiment.
The simulation used in these scripts is called G4d2o and was created by COHERENT collaboration for the part of COHERENT experiment, called "D2O" - a detector, that measures neutrino flux using Cherenkov radiation in heavy water.

In this post, I want to share how to run the simulation for different input parameters, varying them and running simulation in sequence for over 60 times.
