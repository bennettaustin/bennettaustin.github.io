---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

# Machine Learning for Particle Physics
During my second year at Berkeley, I was offered the opportunity to join Professor [Heather Gray's](https://physics.berkeley.edu/people/faculty/heather-gray) ATLAS research group at [Lawrence Berkeley National Laboratory](https://www.physics.lbl.gov/atlas/). During my time here, my advisor, Postdoc Tomohiro Yamazaki, and I worked on developing a method to increase the charm quark identification efficiency (known as "charm tagging") within machine learning classification algorithms.

Motivation for such research comes from the recently discovered Higgs-boson, an elementary particle giving rise to mass in other particles. Since the Higgs-boson was discovered in 2012, physicists have wanted to learn more about its properties. A method of doing so is by studying its decay modes (particles the Higgs-boson decays into). When the Higgs-boson decays into a charm quark, interesting physics phenomena occur. Though, a method of detecting such decays requires the ability to tag charm quarks. Unfortunatley, even the most modern algorithms have a low accuracy when it comes to classifying charm quarks. The main algorithm we focused on was the DL1 algorithm. More information about ATLAS and quark identification algorithms can be read [here](https://arxiv.org/pdf/1907.05120.pdf).

In order to figure out a way to improve charm tagging, I first studied the Higgs-boson itself and its coupling into charm quarks. My first task was to reconstruct the Higgs-boson mass distribution using charm quark decays. The mass in plotted below; the blue line plots the Higgs mass based on all charm quarks while the red line plots the Higgs mass based only on the charm quarks that have been correctly identified as charm quarks by the DL1 algorithm. As seen, there are about 3,500 entries (events) with all charm quarks, whereas there are only about 250 events with correctly classified charm quarks. Hence, not only does this plot show the Higgs-boson mass, but it also highlights the inefficiency of the algorithm with respect to charm quarks. For reference, the official ATLAS Higgs mass distribution plot is also located below. 

<p float="left">
  <img width="350" alt="Higgs_mass" src="https://user-images.githubusercontent.com/93623304/140403859-2a254b7c-a7a0-4cad-b41a-38ed45d6cacb.png" />
  <img width="350" alt="higgs_mass_atlas" src="https://user-images.githubusercontent.com/93623304/140403948-e9e8d587-385f-42d7-95fd-866819d45fe6.png" />
  <img width="320" alt="dl1_score" src="https://user-images.githubusercontent.com/93623304/140404379-333fb703-cc79-4fb7-b4d6-e90cb6a24b81.png" />
</p>

The next step was to plot several different variables used in the DL1 algorithm to identify which are potentially highly influential in charm tagging. The DL1 algorithm actually takes in as input variables from other algorithms, known as JetFitter and SV1, which can be read about in the above paper. I studeid most of the variables in these two algorithms their plots can be seen one of my talks located [here]().


After studying the JetFitter and SV1 variables directly, we decided to look into leptonic variables, where "lepton" refers to an electron or muon. 
