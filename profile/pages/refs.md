# References and materials

## Conferences

### Upcoming

- 23 November 2023, at CWI. [Symposium on the Applications of Scientific Machine Learning](https://www.cwi.nl/en/events/cwi-research-semester-programs/sciml-symposium/)
- 16 November 2023, at Lab 42. [AI for chemistry](https://www.eventbrite.nl/e/tickets-chemai-entering-the-fifth-paradigm-for-chemistry-675267040897).

### Past

- 9-13 October 2023. [Autumn school on scientific machine learning](https://www.cwi.nl/nl/events/cwi-research-semester-programs/autumn-school-scientific-machine-learning-semester-programme/)
  - See [notes](https://github.com/DEEPDIP-project/logs/blob/main/attachments/2023-10-autumn-school/notes.md)
- 26 Feb-3 March 2023. [**CSE23**](https://www.siam.org/conferences/cm/conference/cse23): SIAM Conference on Computational Science and Engineering. Amsterdam.
   - Team Nabla presents _Neural Network Solvers for Differential Equations_ [1](https://meetings.siam.org/sess/dsp_programsess.cfm?SESSIONCODE=75203) and [2](https://meetings.siam.org/sess/dsp_programsess.cfm?SESSIONCODE=75204).

<details>
  <summary> 24 February 2023 AI4Science Symposium [Click to expand]</summary>
   
   #### Summary [AI4Science Symposium](https://ai4science-amsterdam.github.io/workshop2/)
   ###### Past, Present, and Future of the AI4Science Lab - Patrick Forré
   Presentation of various projects (mainly PhD thesis).
   
   - [Simulation-efficient marginal posterior estimation](https://arxiv.org/pdf/2011.13951.pdf) [swyft](https://github.com/undark-lab/swyft).
      - Inverse problem approcahed probabilistically. Want to infer parameters $\theta$ given the solution $x$ of a simulator. 
      - N.N. classificator that predicts the posterior $p(x|\theta)$.
      - Team atlas project in 2020.
   
   - Blind source separation in real time: 
     - Example multiple microphones, multiple people talking. Goal: separate who said what. Application: genetics. 
   
   - Bayesian optimization of Liquid Chromatography (LC)
     - Problem: blurry pictures. 
     - What they do currently: Run LC with multiple parameters combinations (grid search), then an expert will look at the results and say which combination is the best: most probably the least blurry.
     - Propose: use bayesian optimization instead of grid search. Achieve the best combination of parameters faster.
     - Follow-up: The space of parameters is a hyperplane, they want to use geometric deep learning to solve the optimization problem in such space.
   
   - Bird Radar
     - Voronoi tesellation: Modelling population dynamics (Population balance model). Sink and growth terms inside the cells, writing the PDE they get a term for the rates of exchange between cells. [FluxRGNN](https://github.com/FionaLippert/FluxRGNN): Amortized recurrent graph neural networks + dimensionality reduction (VAE).
     - From radar: N.N. predicting vecor fields of how an object moves. 
   
   ###### Harnessing ML to Sample, Analyze & Engineer Modes in Molecular & Colloidal Systems - Alberto Pérez de Alba Ortíz (CSM)
      1. Analyze event of transition between two stable states (free energy).
         N.N. decoder from latent space: possible genes pool to atoms. (?)
      2. Bias to trigger an event from A to B: two low free energy states.
      3. Coarse graining: lot of people working on this.
      4. Designing free-energy lanscapes
         Inverse problem: Want to get to a given state (structure).
         Evolution algoritm: maximize fitness. CNN on photos of diffraction patterns to select which parameter to look at for the fitness function. 
   
   ###### Numerical Tools to Dicepher Exoplanet Atmospheres (Gaussian processes) - Jean-Michel Désert
   - Gaussian processes: from telescope measurements, remove systematic noises to estimate astrophysical noises $\to$ model astrophysical processes.
   - WEBB telescope: spectral measurements allow detection of specific molecules (Biosignatures ?).

   ###### Inferring the Properties of Black Holes and Neutron Stars with Machine Learning - Daniela Huppenkothen (SRON)
   - Statistical inference of astrophysical processes: Datadriven discovery of underlying physics.
     - Random forest classifiers . Autoencoder+ UMAP. Reconstruct the input time series (light curves)
   - Fast Radio Bursts: astrophysical objects, but is not clear what they are.
     - Representation learning Autoencoder: latent representations classification, reveals relevant structures in time series. What does each group means (?)
     - Challenge: time series of variable lenght.
   - Effect of supermassive black holes on their environment. 
     - Neural network emulator: take parameters and give spectrum.
     - Active learning strategies: during learning process, where should we generate some additional data?
   - Simulation-based inference: Defectors X-ray are too bright.
     - Neural-network based inference: N.N estimates the posterior. 
   
   ###### From molecular structure to chemical risk assessment. An AI toolbox towards safe(r) chemicals - Saer Samanipour (HIMS) & Antonia Praetorius (IBED)
   - GNNs to categorize toxicity. The 3D structure of molecules is quite important.
   
</details>
<details>
  <summary> 14 and 15 February 2023 CWI Machine learning theory Bootcamp [Click to expand]</summary>
   
   #### Summary CWI Machine learning theory [Bootcamp](https://homepages.cwi.nl/~wmkoolen/MLT_Sem23/bootcamp.html#Ronald) 14 and 15 February 2023
   No recordings available
   ##### Day 1
   ###### Johannes Schmidt-Hieber
   - Biological neurons: Receive signals (spike time) instead of tensors.
   - Hebbian learning: Adapt a neuron's weight depending on how long ago the other neuron fired the message.

   ###### Frans Oliehoek
   - Reinforcement learning basics, Q-learning.
   - SDM: Sequential Decision Making.
   - MPD: Markov Decision Process.
   - Monte carlo research trees.
   - Intuition of how AlphaGo works.

   ###### Gabriele Cesa: Group equivariant deep learning
   - **Groups**: Framework to apply different transformations to the input (e.g. rotations, translations, reflections).
   - Steerable CNNs. 
   - Group equivariance is not suitable for scale transformations.

   ###### Bob Williamson (Lecture): Foundations of machine learning systems

   ###### Emilie Kaufmann (Lecture): A Tale of Two Non-parametric Bandit Problems

   ##### Day 2
   ###### Tim van Erven: Formal Results in Explainable Machine Learning
   - Explainable AI are mostly *local* (for a given data point) *post-hoc* (after the model has been trained).
   - Most of explainable AI methods: linearization of the function at point $x$ such that the coefficients give the importance of each of the parameteres. 
   - Two examples of methodologies: Gradient-based explanaiton, LIME. 

   ###### Ivo Stoepker: Anomaly detection

   ###### Jaron Sanders: Detecting clusters in time series
   - Stochastic Block Models (SBMs)

   ###### Ronald de Wolf: Tutorial on Quantum Machine Learning
   - Quantum/classical, optimizer/data combinations.
   - Learner is Quantum (Optimizer) specially interesting. 
   - **Quantum linear Algebra**: unsupervised learning. Output is quantum, sometimes dequantizable, usually assumes quantum input. Applies PCA: find eigenvectors in quantum notation.

   ###### Mathias Staudigl: Learning in Games
   
</details>

## Contacts

- [Roland de Wolf](https://homepages.cwi.nl/~rdewolf/). Expert in **quantum machine learning**. Luisa met him in the context of the Research Semester Programme in Machine Learning Theory ([link](https://homepages.cwi.nl/~wmkoolen/MLT_Sem23/bootcamp.html)).
