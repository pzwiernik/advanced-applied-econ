# Individual Research Projects

This course connects modern structural statistics — graphical models, latent variable methods, causal discovery, interference, and structured dependence — with questions that arise in applied economics.

## Expectations for the final project

You will have about 3–4 weeks to complete this project. The goal is **not** to produce a publishable paper or genuinely new empirical results. Instead, the goal is to engage seriously with one specific methodological idea from the course and show that you understand:

- what problem it is trying to solve,
- what assumptions it needs,
- how it behaves in practice,
- and where it may fail.

You may approach the project from either an applied or a theoretical perspective.

### Option A: Applied / empirical / simulation track
For students interested in applied work, the goal is to take one method, apply it, and test its boundaries. A successful project will usually:

1. **Implement** an estimator or algorithm in R or Python.
2. **Apply** it to a real dataset or a carefully designed simulation.
3. **Evaluate** how the method behaves when its assumptions are plausible, questionable, or clearly violated.

Examples:
- What happens to graph estimation if the data are heavy-tailed rather than Gaussian?
- What happens to a causal-discovery method when there is hidden confounding?
- What changes when SUTVA fails and outcomes depend on neighbors' treatments?

### Option B: Theory / methodology track
For students leaning toward econometrics, statistics, or theory, the project does not need to involve a real dataset. A successful project might:

1. **Clarify** the logic of a method or identification argument.
2. **Compare** two related approaches and explain where they differ.
3. **Work through** a theoretical example, proof sketch, counterexample, or simulation that reveals the role of the assumptions.
4. **Adapt** a method to a specific economic setting or explain why such an adaptation is difficult.

A project is still successful even if the method “fails,” as long as the failure is clearly explained and tied to the assumptions.

---

# Suggested project topics

## Category 1: Causal discovery and directional structure

These topics focus on what can and cannot be learned about causal direction from observational data.

### 1. Constraint-based causal discovery and the fragility of Gaussian assumptions
**Objective:** The PC algorithm is a constraint-based method built from conditional independence tests. Study how its output changes when different CI tests are used, especially in settings where Gaussian assumptions are questionable. Apply the method to simulated data or to a small macroeconomic or financial example.

* **Ref 1 (Method):** Peter Spirtes, Clark Glymour, and Richard Scheines (2000). *Causation, Prediction, and Search.*
* **Ref 2 (Application):** Alessio Moneta, Nadine Chlaß, Doris Entner, and Patrick Hoyer (2013). *Causal search in structural vector autoregressive models.* Empirical Economics.

### 2. Identifying direction via non-Gaussianity: LiNGAM
**Objective:** In linear Gaussian SEMs, direction is often not identified. LiNGAM shows that non-Gaussian shocks can break this symmetry. Study the logic of LiNGAM, implement a simple example, and explain clearly why non-Gaussianity helps.

* **Ref 1 (Method):** Shohei Shimizu, Patrik O. Hoyer, Aapo Hyvärinen, and Antti Kerminen (2006). *A Linear Non-Gaussian Acyclic Model for Causal Discovery.* Journal of Machine Learning Research.
* **Ref 2 (Econometric angle):** Markku Lanne, Mika Meitz, and Katarzyna Maciejowska (2017). *Structural vector autoregression with non-Gaussian shocks.* Journal of Econometrics.

### 3. Causal discovery with hidden confounding: DAGs versus MAGs
**Objective:** Compare what can be learned when causal sufficiency is assumed and when it is not. Use DAG-based output and MAG-based output to study how hidden confounding changes the graphical summary.

* **Ref 1 (Method):** Thomas Richardson and Peter Spirtes (2002). *Ancestral graph Markov models.* The Annals of Statistics.
* **Ref 2 (Related discussion):** Doris Entner, Patrik Hoyer, and Peter Spirtes (2012). *Statistical Causal Discovery and the Role of Instrumental Variables.* JMLR Workshop and Conference Proceedings.

### 4. Additive noise models as a nonlinear alternative to LiNGAM
**Objective:** LiNGAM uses linearity plus non-Gaussianity. Additive noise models use nonlinearity plus independence of the noise. Explain the identification logic and compare these two routes to directional discovery.

* **Ref 1 (Method):** Patrik O. Hoyer, Dominik Janzing, Joris Mooij, Jonas Peters, and Bernhard Schölkopf (2009). *Nonlinear causal discovery with additive noise models.* NIPS.
* **Ref 2 (Context):** Jonas Peters, Dominik Janzing, and Bernhard Schölkopf (2017). *Elements of Causal Inference.*

---

## Category 2: Dynamic and network structure

These topics explore how graph-based ideas enter applied economics when units interact or when dependence is dynamic.

### 5. Production networks and aggregate fluctuations
**Objective:** Microeconomic shocks can propagate through input-output or supply-chain networks. Study how network structure amplifies or dampens shocks, and relate this to sparse dependence or transmission graphs.

* **Ref 1:** Daron Acemoglu, Vasco M. Carvalho, Asuman Ozdaglar, and Alireza Tahbaz-Salehi (2012). *The network origins of aggregate fluctuations.* Econometrica.
* **Ref 2:** Vasco M. Carvalho (2014). *From micro to macro via production networks.* Journal of Economic Perspectives.

### 6. Peer effects and interference in school or village networks
**Objective:** When one unit's treatment affects another unit's outcome, SUTVA fails. Study one simple interference design or paper and explain how direct and spillover effects are separated.

* **Ref 1 (Classic):** Charles F. Manski (1993). *Identification of Endogenous Social Effects: The Reflection Problem.* The Review of Economic Studies.
* **Ref 2 (Modern method):** Peter M. Aronow and Cyrus Samii (2017). *Estimating average causal effects under general interference.* The Annals of Applied Statistics.

### 7. Information diffusion in village networks
**Objective:** Study how information or technology adoption spreads over a network. Focus on exposure mappings, targeting, or the role of central nodes.

* **Ref 1:** Abhijit Banerjee, Arun G. Chandrasekhar, Esther Duflo, and Matthew O. Jackson (2013). *The Diffusion of Microfinance.* Science.
* **Ref 2:** Lori Beaman, Ariel BenYishay, Jeremy Magruder, and Ahmed Mushfiq Mobarak (2021). *Can network theory-based targeting increase technology adoption?* American Economic Review.

### 8. Network estimation for high-dimensional time series
**Objective:** In multivariate time series, one may want to distinguish lagged dependence from contemporaneous conditional dependence of shocks. Study one method for constructing such networks and explain what the resulting graph means.

* **Ref 1 (Method):** Matteo Barigozzi and Christian Brownlees (2019). *NETS: Network estimation for time series.* Journal of Applied Econometrics.
* **Ref 2 (Related application):** Francis X. Diebold and Kamil Yilmaz (2014). *On the network topology of variance decompositions: Measuring the connectedness of financial firms.* Journal of Econometrics.

### 9. Policy targeting under network interference
**Objective:** When spillovers are present, the best treatment rule depends on the whole network, not only on unit-level effects. Study one recent paper and explain the targeting logic carefully.

* **Ref 1 (Anchor):** Davide Viviano, selected recent papers on policy targeting under interference.
* **Ref 2 (General background):** Victor Chernozhukov et al. and related literature on policy learning under interference.
---

## Category 3: Hidden confounding, proxies, and high-dimensional adjustment

These topics focus on situations where the confounders are not directly observed or are too numerous to handle naively.

### 10. Double machine learning for treatment effects
**Objective:** Study how DML uses nuisance estimation plus orthogonalization to estimate treatment effects with many controls. Explain why naive machine learning is not enough.

* **Ref 1 (Method):** Victor Chernozhukov, Denis Chetverikov, Mert Demirer, Esther Duflo, Christian Hansen, Whitney Newey, and James Robins (2018). *Double/debiased machine learning for treatment and structural parameters.* The Econometrics Journal.
* **Ref 2 (Context):** Alexandre Belloni, Victor Chernozhukov, and Christian Hansen (2014). *High-dimensional methods and inference on structural and treatment effects.* Journal of Economic Perspectives.

### 11. Proxy controls for an unobserved confounder
**Objective:** Study the idea that multiple noisy proxies can help recover information about a hidden confounder. Explain what is and is not identified, and illustrate with a simulation.

* **Ref 1 (Classic):** Manabu Kuroki and Judea Pearl (2014). *Measurement bias and effect restoration in causal inference.* Biometrika.
* **Ref 2 (Modern method):** Wang Miao, Zhi Geng, and Eric J. Tchetgen Tchetgen (2018). *Identifying causal effects with proxy variables of an unmeasured confounder.* Biometrika.

### 12. Text as a proxy for hidden institutional or policy variables
**Objective:** Study whether text-derived variables (topics, embeddings, sentiment, etc.) can help proxy for hidden confounders or latent institutional states in an economic application.

* **Ref 1 (Review):** Matthew Gentzkow, Bryan Kelly, and Matt Taddy (2019). *Text as data.* Journal of Economic Literature.
* **Ref 2 (Application):** Stephen Hansen, Michael McMahon, and Andrea Prat (2018). *Transparency and deliberation within the FOMC: a computational linguistics approach.* The Quarterly Journal of Economics.

### 13. Synthetic instruments and many-instrument methods
**Objective:** Study the many-instrument problem and how regularization can be used to construct a useful instrument from many candidate variables. Explain the distinction between a classical instrument and a constructed instrument.

* **Ref 1:** Alexandre Belloni, Daniel Chen, Victor Chernozhukov, and Christian Hansen (2012). *Sparse models and methods for optimal instruments with an application to eminent domain.* Econometrica.
* **Ref 2:** Christian Hansen, Jerry Hausman, and Whitney Newey (2008). *Estimation with many instrumental variables.* Journal of Business & Economic Statistics.

### 14. Latent factor adjustment for hidden confounding
**Objective:** When many observables share a common hidden source, a factor model or principal component adjustment may partially recover the confounder. Study the logic, assumptions, and limitations of this approach.

* **Ref 1:** Related literature on factor-adjusted regression and latent confounding.
* **Ref 2:** Susan Athey, Mohsen Bayati, Guido Imbens, and related work where latent structure is used in causal adjustment or panel settings.

---

## Category 4: Latent variable models and hidden structure

These topics focus on using latent variables to represent hidden heterogeneity, hidden classes, or hidden dependence structure.

### 15. Gaussian mixtures and hidden segmentation
**Objective:** Use Gaussian mixtures or latent class models to represent hidden subpopulations. A good project compares latent classes with factor models and explains when each is more appropriate.

* **Ref 1:** Geoffrey McLachlan and David Peel (2000). *Finite Mixture Models.*
* **Ref 2:** Applied labor, consumer, or industrial-organization paper using latent classes.

### 16. Uncovering latent worker and firm types
**Objective:** Study how latent-type ideas enter matched employer-employee data. This project may be more conceptual than computational if the data are too difficult to access.

* **Ref 1:** John M. Abowd, Francis Kramarz, and David N. Margolis (1999). *High wage workers and high wage firms.* Econometrica.
* **Ref 2:** Stéphane Bonhomme, Thibaut Lamadon, and Elena Manresa (2019). *A distributional framework for matched employer employee data.* Econometrica.

### 17. Non-independent component analysis
**Objective:** Standard ICA assumes independent latent components. Study what changes when latent components are not independent, and explain how this broadens the latent-variable perspective.

* **Ref 1 (Method):** Geert Mesters and Piotr Zwiernik (2024). *Non-independent components analysis.* The Annals of Statistics.
* **Ref 2 (Context):** Mario Forni, Marc Hallin, Marco Lippi, and Lucrezia Reichlin (2000). *The generalized dynamic-factor model.* The Review of Economics and Statistics.

### 18. Matrix completion and latent panel structure
**Objective:** Study matrix-completion or synthetic-control style methods as latent-factor approaches to causal panel data.

* **Ref 1 (Foundational):** Alberto Abadie, Alexis Diamond, and Jens Hainmueller (2010). *Synthetic control methods for comparative case studies.* Journal of the American Statistical Association.
* **Ref 2 (Modern method):** Susan Athey, Mohsen Bayati, Nikolay Doudchenko, Guido Imbens, and Khashayar Khosravi (2021). *Matrix completion methods for causal panel data models.* Journal of the American Statistical Association.

---

## Category 5: Positive dependence and robust graph estimation

These topics focus on dependence structures that go beyond sparsity alone.

### 19. Total positivity in macro or financial comovement
**Objective:** Study whether a positive-dependence assumption such as MTP\(_2\) is plausible in an economic dataset, and explain what statistical benefits it gives for covariance or graph estimation.

* **Ref 1 (Theory):** Shaun Fallat, Steffen Lauritzen, Kayvan Sadeghi, Caroline Uhler, Nanny Wermuth, and Piotr Zwiernik (2017). *Total positivity in Markov structures.* The Annals of Statistics.
* **Ref 2 (Application):** Raj Agrawal, Uma Roy, and Caroline Uhler (2020). *Covariance matrix estimation under total positivity for portfolio selection.* Journal of Financial Econometrics.

### 20. Robust financial networks via non-paranormal or elliptical models
**Objective:** Compare Gaussian graphical models with more robust alternatives for financial data, such as non-paranormal or elliptical partial correlation graphs.

* **Ref 1 (Non-paranormal):** Han Liu, Fang Han, Ming Yuan, John Lafferty, and Larry Wasserman (2012). *High-dimensional semiparametric Gaussian copula graphical models.* The Annals of Statistics.
* **Ref 2 (Elliptical):** David Rossell and Piotr Zwiernik (2021). *Dependence in elliptical partial correlation graphs.* Electronic Journal of Statistics.

---

## Proposing your own topic

You are strongly encouraged to propose your own topic, especially if it connects to an ongoing thesis or research interest.

A custom topic should satisfy three criteria:

1. **Relevance:** it must clearly connect to a method or idea from the course.
2. **Core component:** it must include either an implementation / simulation / empirical illustration, or a serious methodological / theoretical analysis.
3. **Critical evaluation:** it must go beyond description and say something about assumptions, limits, or interpretation.

To propose your own topic, submit a short 1-page PDF describing:
- the question,
- the method,
- the dataset or simulation plan (if applicable),
- and 1–2 core references.
