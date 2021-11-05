---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

## Machine Learning for Particle Physics
During my second year at Berkeley, I was offered the opportunity to join Professor [Heather Gray's](https://physics.berkeley.edu/people/faculty/heather-gray) ATLAS research group at [Lawrence Berkeley National Laboratory](https://www.physics.lbl.gov/atlas/). During my time here, my advisor, Postdoc Tomohiro Yamazaki, and I worked on developing a method to increase the charm quark identification efficiency (known as "charm tagging") within machine learning classification algorithms.

Motivation for such research comes from the recently discovered Higgs-boson, an elementary particle giving rise to mass in other particles. Since the Higgs-boson was discovered in 2012, physicists have wanted to learn more about its properties. A method of doing so is by studying its decay modes (particles the Higgs-boson decays into). When the Higgs-boson decays into a charm quark, interesting physics phenomena occur. Though, a method of detecting such decays requires the ability to tag charm quarks. Unfortunatley, even the most modern algorithms have a low accuracy when it comes to classifying charm quarks. The main algorithm we focused on was the DL1 algorithm. More information about ATLAS and quark identification algorithms can be read [here](https://arxiv.org/pdf/1907.05120.pdf).

In order to figure out a way to improve charm tagging, I first studied the Higgs-boson itself and its coupling into charm quarks. My first task was to reconstruct the Higgs-boson mass distribution using charm quark decays. The mass in plotted below; the blue line plots the Higgs mass based on all charm quarks while the red line plots the Higgs mass based only on the charm quarks that have been correctly identified as charm quarks by the DL1 algorithm. As seen, there are about 3,500 entries (events) with all charm quarks, whereas there are only about 250 events with correctly classified charm quarks. Hence, not only does this plot show the Higgs-boson mass (125 GeV), but it also highlights the inefficiency of the algorithm with respect to charm quarks. For reference, the official ATLAS Higgs mass distribution plot is also located below. Also, I added the DL1 Score distribution, which is plotted by calculating the DL1 discriminant <img width="130" alt="equation" src="https://user-images.githubusercontent.com/93623304/140429897-5d9218f6-4449-4d75-8110-9e8594ef8160.png">, where pc, pb, and pu refer to the probabilities of a charm, bottom, or light jet, resepectively, being present in the training; and f = 0.08 is another parameter meausring the fraction of bottom jets present in the background of the training dataset. A DL1 score greater than 1.3 is what is required for a particle to be labelled as charm quark. From this, the current charm tagging efficiency is about 20%. 


<p float="left">
  <img width="325" alt="Higgs_mass" src="https://user-images.githubusercontent.com/93623304/140403859-2a254b7c-a7a0-4cad-b41a-38ed45d6cacb.png" />
  <img width="325" alt="higgs_mass_atlas" src="https://user-images.githubusercontent.com/93623304/140403948-e9e8d587-385f-42d7-95fd-866819d45fe6.png" />
  <img width="318" alt="dl1_score" src="https://user-images.githubusercontent.com/93623304/140428258-a45c2478-f9af-4931-9706-74af2e495200.png">
</p>

The next step was to plot several different variables used in the DL1 algorithm to identify which are potentially highly influential in charm tagging. The DL1 algorithm actually takes in as input variables from other algorithms, known as JetFitter and SV1, which can be read about in the above paper. I studied most of the variables in these two algorithms their plots can be seen in one of my talks located [here](http://bennettaustin.github.io/files/Charm_tagging_presentation.pdf).


After studying the JetFitter and SV1 variables directly, we decided to look into leptonic variables, where "lepton" refers to an electron or muon. After plotting these types of variables, we went ahead and began training the DL1 algorithm with these added features. Looking at the plots below, you can see that, when the leptonic variables are included in the training data, the performance of the DL1 algorithm increases. The blue line plots the default DL1 performance, which is the base performance used by ATLAS (and hence excludes leptonic variables); the orange line plots the my DL1 performance. The far left orange plot is my base case, which has no leptonic variables, but is still slightly better than ATLAS'S default; the middle orange plot includes electron variables, performing better than ATLAS'S default algorithm as well as my base case; the far right orange curve includes muon variables, and outperforms all other cases. The difference is most easily seen in the ratio plot, where the muon plot gives an initial ratio of 1.15, roughly 10% higher than the other two plots.

<p float="left">
  <img width="320" alt="default" src="https://user-images.githubusercontent.com/93623304/140433540-88b57eca-dbd4-46fe-9b8a-152ac18c1f6c.png">
  <img width="320" alt="electrons" src="https://user-images.githubusercontent.com/93623304/140433551-66161d4f-09bc-48ac-ae16-f3f2dc3f45fd.png">
  <img width="320" alt="muons" src="https://user-images.githubusercontent.com/93623304/140433580-91c068aa-255f-4933-af73-d107ccf2f2cb.png">
</p>

Summarizing, my research group and I were able to identify a family of variables that improve the charm quark identification rate in classification algorithms used by ATLAS for particle collion experiments. The rest of my talk, on what is known as a "Soft Lepton Tagger," is available [here](http://bennettaustin.github.io/files/Soft_Lepton_Tagger.pdf). This provides some more detailed background information, includes many more plots of variables, and discusses the the DL1 algorithm itself (e.g. the neural network structure and hyperparameter optimization).
