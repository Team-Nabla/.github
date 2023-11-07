
# MALES

Machine Learning for Single Star Scidar
Link to github organization: [MALES](https://github.com/MALES-project)

Below you can find some notes.

--------------------------------
(*The following notes correspond to October 2023, before the kickoff meeting*).

## Goal

Optimize satellite communication in atmosphere

## Research question

There is effect of a noisy function Cn^2 (atmosferic turbolence) that can be estimated from model but not measured

They can measure local Cn^2 and infer Cn^2(h) [high altitude]. But also they can use SCIDAR instrument to measure cn^2(h) from 'speckle patterns' (?). The reasoning is that SCIDAR can measure these 'speckle' which are strongly correlated to turbolence (thus Cn^2(h)), so they use this SCIDAR which is a instrument for star things, but in a different context.

ML will be used to correlate speckle to cn, so it is like function to function prediction with ml (i have no idea what speckles are)

In practice, people have ben using stereo SCIDAR (double stars) cause they are easier. They want to use single star SCIDAR, but it requires a 'motion stage' (??) which adds complexity.

**In practice we want to solve an inverse problem with ML, where the forward is standard optics (SOAPY)**. This means that we will use soapy to generate data in a direct way, and train something todo the inverse. So we have to learn soapy.

## What are speckle patterns?

?

## what is a motion stage?

?

## SOAPY

-[soapy](https://github.com/AOtools/soapy) : optics simulation to do the forwards problem. Basically we can use it to generate data

It takes as input phase screens, that can be measured, and correspond to local Cn^2. Then the simulatio uses MC to calculate speckle patterns as output.

Then in practice **we take soapy, we plug in some realistic[^1] Cn^2, so soapy will give us he speckle patterns. Then we train a model to use those patterns to reconstruct Cn^2**

[^1]: right now I have no idea about 'realistic' Cn^2. This is crucially relevant since we cn not expect to wrk with any possible function.

## SOAPY parameters

A simulation in SOAPY is described by a `.yaml` file. It contains many parameters that are necessary to run the simulation. In our inverse approach, we would need to predict some of them, while other are fixed and depend on the specific apparatus. **It is necessary to know the parameters that correspond to their specific experimental setup, because there is no way to let them free**.

## The ML model

Befor discussing which model to use for the inverse problem, it is necessary to understand the dofs that are in play.

## Problems

1) there are too many parameters to correlate and the structure is weak (turbolence)
2) they do not provide data
3) one single synthetic data point (with SOAPY) requires >1h of simulation
4) they do not seem to be expert with the forward problem, so I don't think they can be helpful with the inversion

## References

In the proposal, hey have linked 4 references which are not very useful and I think they are almost ignorable.
However, in the meantime they have published this [paper](https://arxiv.org/abs/2304.12177) which is interesting an points to useful references.

----------------------------------------------------------------

# PI-ML

In September 2023 they have published a [paper](https://arxiv.org/abs/2304.12177), connected to the following [repo](https://github.com/mpierzyna/piml), that should be the main focus for us.
**The package answers to a simplified version of the research question, so our focus can be instead to improve this existing package**.
This is our [fork](https://github.com/Team-Nabla/piml) of the package.

In brief, their method is based on the following pipeline:

0) goal: from collected data, trainto predict Cn^2
1) use domain knowledge to identify physical variables that are relevant
2) use [PI theorem](#pi-theorem) (from [here](https://linkinghub.elsevier.com/retrieve/pii/S2352711021001291)) to reduce complexity
3) apply even more domain knowledge to remove unnecessary elements from the previous step
4) use this reduced set of data in a XGboost ensemble to predict Cn^2

In practice the data have now the structure of $14*6$ input, to predict $14*1$ outputs.

## PI theorem

The PI theorem, also known as the Buckingham Pi theorem or Buckingham's π theorem, is a fundamental concept in dimensional analysis, which is a technique used to simplify complex physical relationships by eliminating redundant variables and expressing relationships in terms of dimensionless groups. The PI theorem can be applied to a wide range of scientific and engineering problems, including those involving dimensionality reduction.

The PI theorem states that if you have a physical relationship involving a certain number of physical variables (n), and these variables can be expressed in terms of k fundamental dimensions (e.g., mass, length, time, etc.), then the relationship can be expressed in terms of n - k dimensionless groups. These dimensionless groups are often called "π-groups" or "Buckingham π-groups."

In the context of dimensionality reduction, the PI theorem helps identify which dimensionless combinations of variables are important for describing a physical system while eliminating extraneous variables. This simplification is especially useful in experiments and simulations because it reduces the number of measurements or computations required to characterize a system.

Here's a general outline of the steps involved in applying the PI theorem for dimensionality reduction:

- Identify the Relevant Physical Variables: Determine the physical variables that are relevant to the problem you are trying to solve. These variables could include parameters like length, mass, time, temperature, velocity, pressure, etc.

- Determine the Fundamental Dimensions: Assign dimensions (e.g., [L] for length, [M] for mass, [T] for time, etc.) to each of the physical variables. You should aim to express all variables in terms of these fundamental dimensions.

- Check for Dimensional Consistency: Ensure that the equation or relationship you are analyzing is dimensionally consistent. In other words, verify that the dimensions on both sides of the equation match.

- Apply the PI Theorem: Use the PI theorem to determine the number of dimensionless π-groups (n - k) required to describe the system. These dimensionless groups can be constructed by combining the relevant physical variables in specific ways.

- Formulate the Dimensionless Groups: Construct the dimensionless groups (π-groups) using the relevant physical variables. The specific form of these dimensionless groups will depend on the problem at hand.

- Interpret the Results: The dimensionless groups you obtain from the PI theorem represent dimensionless parameters that characterize the system. These parameters can often provide valuable insights into the behavior of the system and can help reduce the complexity of the problem.

By using the PI theorem for dimensionality reduction, you can identify and focus on the most important dimensionless parameters that govern the behavior of a physical system, which can simplify analysis and experimentation.

## Things we can do

- Clean/refactor/improve the repo
- SHAP importance
- Use raw features instead of PI theorem, and do dimensionality reduction with PCA,t-SNE,AE ecc.
- Split their best PI_2 descriptor to see if num or den is more important