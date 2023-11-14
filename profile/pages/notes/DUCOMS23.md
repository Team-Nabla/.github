## Notes
By Pablo R.

### Opening and Welcome
Johan Mentink (Radboud Universiteit Nijmegen) and Kees Vuik (University of Delft|TUD)

Strategic areas correspond with parallel sessions:

- Machine Learning
- Data-driven methods
- Multi-scale computing
- Uncertainty Quantification
- Energy-efficient Computing

### Keynote: Speeding up calculations for water management 
Albrecht Weerts - Wageningen|WUR & Deltares

- Uses of machine learning in hydrology 
- Collaborated with Netherlands eScience Center|us (eWater cycle) 
- Not very relevant

### Keynote: From multiscale modeling of knee osteoarthritis to building the virtual human twin
Liesbet Geris - University of Liège, KU Leuven & Virtual Physiological Human Institute, Belgium

- Multi-scale biophysics 
- *In silico* health care research 
- From macroscopic to cellular level, and even genes
- Not to replace, but to assist the doctors
	- So they have more time for patients instead of less 

### Keynote: Application of deep learning to drug discovery: limitations and opportunities
Francesca Grisoni - Eindhoven University, Dept. Biomedical Engineering, Institute for Complex Molecular Systems (ICMS) and Eindhoven AI Systems Institute (EAISI)

- The cardinality of the chemical universe is enormous, around $10^{60}$
- Link structure to activity $f(s) = A$
- s can be a graph or a SMILES string 
- Activity cliffs: tiny structural changes that trigger large activity changes
	- Tricky to deal with machine learning 
- Molecules have
	- syntax: valid and invalid molecules 
	- and semantics: useful and for what
	- Natural language processing is relevant here! 

### Past, Present and Future of AI in High Energy Physics and Astrophysics: From simple models to GPT4
Sascha Caron, Radboud Universiteit Nijmegen and Nikhef.

- Member of the European Coalition for AI in fundamental physics
- The standard model has a huge predictive power with relatively few parameters
- But there are still open questions
	- What is general relativity doing at the quantum level
- Use machine learning for analyzing results of particle collision experiments
- Drifted into philosophy of science

### Learning neural closure models for fluid flows
Benjamin Sanderse, CWI.

- About DEEPDIP
- Structure preserving: integrate physics and data with structure
- Structure
	- Conservation laws
	- Symmetries
	- Invariants
- Challenge
	- Find relevant structure
	- Preserve from continuous to discrete
	- Closure models
- Main idea: use conserved quantities to build stable closure models
- Check automatic differentiation with Zygote

### Decomposing physics-informed neural networks
Alexander Heinlein, University of Delft.

- Numerical methods
	- Robust and generalizable
	- Require mathematical models
- Driven by data
	- Don't require mathematical models
	- Sensitive to data
	- Limited extrapolation capabilities
- Physics informed neural networks
	- Moseley, Markham, and Nissen-Meyer (2023)

### Digital Twins with the Multiscale Modelling and Simulation Framework and MUSCLE3
Lourens Veen and Alfons Hoekstra, Netherlands eScience Center|NLeSC.

- A challenging scientific problem is a challenging technological problem
	- Our role is to help scientists focus on the scientific challenge
	- And take care of the technological one
- Introduced the Multiscale Modelling and Simulation Framework
	- See tutorial
	- Borgdorff 2012, Foundations of distributed multiscale computing
	- Belgacem 2013, Distribute
	- Chopard 2014, A framework...
	- Borgdorf 2014 MUSCLE2
	- MUSCLE3 is ongoing work
		- Documentation
		- Exascale
		- More applications
		- More community
		- Your models?

### Advancing Wind Farm Modeling through Fluid Physics and High Performance Computing
Richard Stevens, University of Twente.

- Fluid dynamics require collecting information from scales among 7 orders of magnitude
- Interested in efficiency decay in windfarms due to wakes

### Keynote: Infectious Disease Data Analytics and Modelling: Mpox, COVID-19
Jacco Wallinga, Rijksinstituut voor volksgezondheid en milieu|RIVM and University of Leiden|Leiden Universiteit.

- The Netherlands, due to its population density, is particularly sensitive to epidemics
- Live learning from incoming data
- Example [repo from RIVM](https://github.com/rivm-syso/cm-evaluation)
	- They can use some R packaging!

### Special Lecture: Computational Science and Engineering: Looking back and looking forward
Margot Gerritsen, Stanford University.

- Mathematicians: Jack of all, master of nothing
	- But the basics are the same: a bit of linear algebra, a bit of calculus, ...
- Data science is taking of. Exciting period ahead
- A lot of cowboys out there saying _"give me your data, I'll give you your answer"_
	- This happened before, with the boom of consultants...
	- ... and black boxes, and not very much understanding.
	- It was even claimed that linear algebra was dead
	- Google was born in a linear algebra lesson about Jacobi iteration
- [National agenda computational sciences for a sustainable future](https://www.computationalsciencenl.nl/en/national-agenda/)