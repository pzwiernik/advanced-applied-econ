# Individual project topics

Each project should deepen one aspect of the course through theory, methods, simulation, or an applied case study. Most projects should include four parts:

1. a clear motivating question,
2. a concise explanation of the method or idea,
3. a small simulation or empirical illustration,
4. a discussion of assumptions, strengths, and limitations.

Students are welcome to refine these topics or propose related alternatives.

---

## Theory and methods

### 1. Markov equivalence and CPDAGs
Explain why conditional independence does not identify a unique DAG in general. Illustrate Markov equivalence with small examples, and explain how CPDAGs summarize what is and is not identified.

### 2. Why non-Gaussianity identifies direction in LiNGAM
Study why linear Gaussian SEMs are directionally ambiguous, and how non-Gaussian shocks break that symmetry. Include a simple simulation and a small implementation of DirectLiNGAM.

### 3. Mean independence versus full independence in causal discovery
Compare classical LiNGAM assumptions with weaker mean-independence assumptions. Explain what changes theoretically, and illustrate with a simulated example involving dependent or heteroskedastic shocks.

### 4. Additive noise models beyond LiNGAM
Introduce additive noise models as a nonlinear alternative to LiNGAM. Explain why asymmetry may identify direction even without linearity, and compare the idea to the non-Gaussian linear case.

### 5. Positive dependence and total positivity
Explain positive dependence, MTP\(_2\), and why sign constraints can simplify dependence modeling. Include a Gaussian graphical example and discuss why this may matter statistically.

### 6. Gaussian graphical models and the precision matrix
Explain carefully why zeros in the precision matrix correspond to conditional independence in the Gaussian case. Include a small simulation and a worked graphical example.

---

## Methods and computation

### 7. Graphical lasso for financial or macroeconomic data
Estimate a sparse Gaussian graph from financial returns or macro indicators. Discuss what the resulting edges mean and how tuning affects the graph.

### 8. Non-paranormal graphical models
Compare Gaussian and non-paranormal graph estimation on skewed or heavy-tailed data. Explain why rank-based methods can be more robust.

### 9. The PC algorithm in practice
Implement the PC algorithm on simulated and real data. Discuss how the result depends on the conditional independence tests and on the significance threshold.

### 10. DirectLiNGAM on simulated economic data
Simulate a system with non-Gaussian shocks and show how DirectLiNGAM can recover the ordering. Compare with what happens in the Gaussian case.

### 11. Latent factor adjustment for hidden confounding
Study how latent factors can be used as controls when confounding is approximately low-dimensional. Include a simulation and, if possible, a small empirical example.

### 12. Proxy controls with multiple noisy measurements
Analyze the proxy-control idea when a confounder is hidden but several noisy measurements are observed. Show how one proxy differs from two or more.

### 13. Gaussian mixtures and hidden segmentation
Use Gaussian mixtures to model latent classes or hidden heterogeneity. Compare clustering-based explanations with factor-based explanations.

### 14. Covariance estimation under total positivity
Study Gaussian covariance estimation under MTP\(_2\) constraints. Compare the unconstrained and constrained estimates in a small example.

---

## Applied topics

### 15. A financial contagion or dependence network
Use stock returns, industry indices, or bank data to build a dependence network. Compare a factor explanation with a sparse residual graph.

### 16. Latent market factors versus residual network structure
Study the extent to which return comovement is explained by one or more latent factors, and how much residual structure remains afterward.

### 17. Peer effects in education
Study a paper on peer effects in schools or classrooms. Explain how interference changes the causal question and what role the network plays.

### 18. Information diffusion in village networks
Study an applied paper on information spread, technology adoption, or social learning in villages. Focus on how exposure is defined and how spillovers are estimated.

### 19. Targeting treatment under network interference
Study a modern paper on treatment targeting when spillovers are present. Explain why the best assignment depends on network position and not only on unit-level treatment effects.

### 20. Instrumental variables with hidden confounding
Study one applied IV paper and explain how the instrument solves a hidden-confounding problem. Focus on the economic logic behind relevance, exclusion, and exogeneity.

### 21. Judge or physician assignment as an instrument
Analyze a paper using quasi-random judge or physician assignment. Explain why assignment variation can be used as an instrument and what assumptions remain critical.

### 22. Education, ability, and proxy controls
Use a stylized or real education dataset to discuss hidden ability and proxy measurements such as test scores, parental variables, or baseline outcomes.

### 23. Text embeddings or latent features as controls
Explore whether low-dimensional features extracted from text or other unstructured data can help account for hidden heterogeneity in an economic application.

### 24. Latent class models in labor or consumer economics
Study how latent classes can be used to model hidden population structure, such as worker types, firms, or consumer segments.

### 25. Positive dependence in portfolio problems
Study whether covariance estimation under positive-dependence constraints can improve stability in a simple portfolio allocation exercise.

---

## Possible papers or methods to anchor projects

Projects may be based on one important paper, but should go beyond summary whenever possible. A strong project usually does at least one of the following:
- reproduces a key simulation,
- applies the idea to a small dataset,
- compares two competing methods,
- or explains one important limitation of the method.

---

## Project categories

Students may choose one of three formats:

### Theory / methods
Focus on mathematical structure, identifiability, or assumptions behind a method.

### Simulation / computation
Focus on implementing and comparing methods on synthetic data.

### Applied empirical project
Use a real dataset or applied paper to study one of the course ideas in context.

---

## Guidance on scope

A good project should be narrower than a survey article. It is usually better to explain one specific idea carefully than to cover too many loosely connected things.

For example:
- good: “DirectLiNGAM versus Gaussian SEMs on simulated macro shocks,”
- too broad: “Causal discovery in economics.”

---

## If you want to propose your own topic

Own-topic proposals are welcome, especially if they are:
- clearly related to the course,
- focused enough to be completed well,
- and have at least one concrete methodological or empirical component.