---
title: "Variational Quantum Algorithm for Option Pricing"
excerpt: "Pricing options modelled with stochastic volatility via quantum algorithm."
collection: portfolio
date: 2024-09-14
category: "Research"
tags: ["Quantum", "Differential Equation"]
period: "hk"
header:
  teaser: "/srf.jpg"
---

**Links:** [Synopsis]({{ base_path }}/files/sypnosis_draft.pdf) • [Poster]({{ base_path }}/files/SRF_Poster.pdf) • [Notes]({{ base_path }}/files/SRF_Notes.pdf) • [Code](https://github.com/BienBienBuen/SRF)

## Project Overview

The focus of my Summer Research Fellowship at HKU was to apply Variational Quantum Imaginary Time Evolution (VarQITE) to the pricing of options modelled with stochastic volatility. The general framework was previously developed in literature([A variational quantum algorithm for the Feynman-Kac formula](https://arxiv.org/pdf/2108.10846)), but the application of VarQITE was limited to pricing options with fixed volatility. By making volatility stochastic, we introduce an extra dimension to the option surface, requiring more sophisticated ansatz and a more complex implementation in discretizing the time evolution operator, which was the main focus of our research project. 