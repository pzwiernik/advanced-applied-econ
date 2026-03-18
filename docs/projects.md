# Individual Research Projects

This course bridges the gap between modern structural statistics (graphical models, latent variables, causal discovery) and applied economics. 

**Expectations for the Final Project:**
You will have about 3–4 weeks to complete this project. Given this short timeframe, the goal is not to produce a publishable paper or genuinely new empirical results. Instead, I want to see you actively engage with the material and try applying these advanced methods to see how they behave in practice. 

Pure machine learning methods often fail when applied blindly to economic data due to heavy tails, unmeasured confounding, time-dependence, or SUTVA violations. A successful project will take a method, try it out, and explore these breaking points. You are expected to:
1. **Implement** an estimator or algorithm (in R or Python) based on a methodology from the course.
2. **Apply** it to an economic problem, using either a real-world dataset or a carefully constructed simulation.
3. **Investigate** its limitations. (e.g., Run a robustness check: What happens to the DAG if the data is heavy-tailed instead of Gaussian? What happens to the network if a latent confounder is ignored?)

Do not worry if the method "fails" or gives messy results on real data—documenting and explaining *why* it fails based on economic theory is exactly what I am looking for!

---

## Category 1: Causal Discovery and Structural Vector Autoregressions (SVARs)

*Standard macroeconomic and firm-level models often rely on arbitrary structural assumptions (like Cholesky orderings). These projects explore data-driven causal discovery, focusing on where standard algorithms fail.*

### 1. The Fragility of Gaussian DAGs in Macroeconomic Shocks
**Objective:** Standard causal discovery (like the PC algorithm) heavily uses Gaussian conditional independence tests. Applied to heavy-tailed macroeconomic data, this often produces nonsensical structural orderings. Students will apply the PC algorithm to macro time series (e.g., FRED-MD) and compare the output of standard Gaussian tests against non-parametric tests.
**Key Reference:** Alessio Moneta, Nadine Chlaß, Doris Entner, and Patrick Hoyer (2013). *Causal search in structural vector autoregressive models.* Empirical Economics.

### 2. Identifying Supply and Demand via Non-Gaussianity (LiNGAM)
**Objective:** Separating demand and supply shocks usually requires valid instruments. This project uses the Linear Non-Gaussian Acyclic Model (LiNGAM) to exploit the non-Gaussianity of price/quantity residuals for identification, completely bypassing the need for theoretical zero restrictions.
**Key Reference:** Shohei Shimizu, Patrik O. Hoyer, Aapo Hyvärinen, and Antti Kerminen (2006). *A Linear Non-Gaussian Acyclic Model for Causal Discovery.* Journal of Machine Learning Research.

### 3. Causal Discovery in Institutional and Conflict Data
**Objective:** In political economy (e.g., following the work of Marta Reynal-Querol on conflict and institutions), identifying causal arrows between historical events, institutional quality, and conflict is notoriously hard. Students will apply discovery algorithms to historical datasets, explicitly dealing with the challenge of causal sufficiency (unobserved confounders) by comparing DAG outputs to Maximal Ancestral Graphs (MAGs) estimated via the FCI algorithm.
**Key Reference:** Peter Spirtes, Christopher Meek, and Thomas Richardson (1995). *Causal Inference in the Presence of Latent Variables and Selection Bias.* Proceedings of the Eleventh Conference on Uncertainty in Artificial Intelligence.

### 4. Firm Dynamics and Unobserved State Variables
**Objective:** Firms operate under information frictions and menu costs (themes explored by UPF macroeconomists like Isaac Baley). Students will use Hidden Markov Models (HMMs) or latent state-space models to recover unobserved discrete "regimes" in firm pricing or inventory data, comparing the recovered states to observed macro aggregates.
**Key Reference:** James D. Hamilton (1989). *A new approach to the economic analysis of nonstationary time series and the business cycle.* Econometrica.

---

## Category 2: Network Spillovers and Interference

*In many economic settings, treating units as isolated is mathematically convenient but economically false. These projects focus on methodologies that explicitly model network interference.*

### 5. Production Networks and Macroeconomic Fluctuations
**Objective:** Microeconomic shocks to individual firms or sectors can propagate through supply chains to cause aggregate fluctuations (a key theme in the work of Eduard Schaal and others). Students will estimate an undirected dependence graph of sectoral outputs and analyze how the sparsity of the precision matrix relates to the propagation of shocks.
**Key Reference:** Daron Acemoglu, Vasco M. Carvalho, Asuman Ozdaglar, and Alireza Tahbaz-Salehi (2012). *The network origins of aggregate fluctuations.* Econometrica.

### 6. Estimating Peer Effects and Spillovers in Family/Labor Economics
**Objective:** Interventions like paternity leave reforms or health subsidies often have spillover effects on coworkers or family members (themes seen in Libertad González's research). Students will use exposure mappings to explicitly estimate direct versus network spillover effects, relaxing the SUTVA assumption.
**Key Reference:** Peter M. Aronow and Cyrus Samii (2017). *Estimating average causal effects under general interference.* The Annals of Applied Statistics.

### 7. Information Diffusion in Developing Economies
**Objective:** Model how a new agricultural technology or microfinance program spreads as a message-passing process on a village social network. Students will evaluate how the structure of the network (e.g., centrality of early adopters) impacts the diffusion rate.
**Key Reference:** Abhijit Banerjee, Arun G. Chandrasekhar, Esther Duflo, and Matthew O. Jackson (2013). *The Diffusion of Microfinance.* Science.

### 8. Network Estimation for High-Dimensional Time Series (NETS)
**Objective:** Constructing dependence networks for hundreds of time series requires separating lagged dynamic effects from contemporaneous conditional dependencies. Students will use the NETS methodology to estimate Long Run Partial Correlation networks.
**Key Reference:** Matteo Barigozzi and Christian Brownlees (2019). *NETS: Network estimation for time series.* Journal of Applied Econometrics.

---

## Category 3: High-Dimensional Controls and Proxies

*How do we perform causal inference when the confounders are either too numerous to include in an OLS regression, or entirely unobserved but captured via noisy proxies?*

### 9. Double Machine Learning for Policy Evaluation
**Objective:** Estimate the causal effect of a treatment when there is a massive number of potential confounders. Standard OLS suffers from overfitting, and naive Lasso suffers from regularization bias. Students will implement cross-fitted Double/Debiased Machine Learning (DML) on labor survey data.
**Key Reference:** Victor Chernozhukov, Denis Chetverikov, Mert Demirer, Esther Duflo, Christian Hansen, Whitney Newey, and James Robins (2018). *Double/debiased machine learning for treatment and structural parameters.* The Econometrics Journal.

### 10. Proxy Controls for Unobserved Ability or Health
**Objective:** When an important confounder (like worker ability or early childhood health) is unobserved, researchers use multiple noisy proxies. Students will use the proximal causal inference framework to achieve non-parametric identification using a pair of proxies, applying this to a classic wage or health regression dataset.
**Key Reference:** Wang Miao, Zhi Geng, and Eric J. Tchetgen Tchetgen (2018). *Identifying causal effects with proxy variables of an unmeasured confounder.* Biometrika.

### 11. Text as a High-Dimensional Proxy for Institutional Quality
**Objective:** Following recent trends in political economy (e.g., Marta Reynal-Querol's work), researchers increasingly use text as data. Students will extract low-dimensional latent topics or embeddings from historical/political text and use them as high-dimensional controls or proxies for unobserved institutional confounders in a regression framework.
**Key Reference:** Matthew Gentzkow, Bryan Kelly, and Matt Taddy (2019). *Text as data.* Journal of Economic Literature.

### 12. Synthetic Instruments for High-Dimensional Identification
**Objective:** Finding valid instruments for price in demand estimation is a classic problem. When many weak instruments are available, standard IV estimators suffer from severe bias. Use regularized estimators (Lasso-based IV) to construct an optimal "synthetic" instrument and estimate demand elasticities.
**Key Reference:** Alexandre Belloni, Daniel Chen, Victor Chernozhukov, and Christian Hansen (2012). *Sparse models and methods for optimal instruments with an application to eminent domain.* Econometrica.

---

## Category 4: Latent Variable Models and Market Structure

*Using latent variables to discover hidden subpopulations, unobserved market factors, or structural sorting.*

### 13. Uncovering Latent Worker and Firm Types
**Objective:** In labor economics, the sorting of workers to firms generates market power and wage inequality (a core focus of Jan Eeckhout's research). Students will use Gaussian Mixtures or Latent Class Models on matched employer-employee data to recover unobserved "types" of workers and firms that drive non-random sorting.
**Key Reference:** Stéphane Bonhomme, Thibaut Lamadon, and Elena Manresa (2019). *A distributional framework for matched employer employee data.* Econometrica.

### 14. Non-independent Component Analysis in Macro Factors
**Objective:** Standard factor models in macroeconomics assume latent factors are independent. In reality, unobserved macro shocks have complex, structural dependence. Apply Non-independent Component Analysis (NICA) to a macro dataset to extract latent factors and explicitly model the dependence graph among these unobserved shocks.
**Key Reference:** Geert Mesters and Piotr Zwiernik (2024). *Non-independent components analysis.* The Annals of Statistics.

### 15. Latent Factor Discovery in Subjective Survey Data
**Objective:** Applied microeconomists often use surveys measuring trust, risk aversion, or happiness. These are noisy, discrete proxies. Estimate a structural latent variable model (like a latent tree) to map discrete survey responses into underlying continuous economic preferences.
**Key Reference:** Flavio Cunha, James J. Heckman, and Susanne M. Schennach (2010). *Estimating the technology of cognitive and noncognitive skill formation.* Econometrica.

### 16. Matrix Completion for Causal Panel Data
**Objective:** The synthetic control method recovers missing potential outcomes by exploiting latent factor structure in panel data. Apply high-dimensional matrix completion to evaluate a state-level policy change (e.g., a minimum wage hike) and compare the counterfactuals against standard Difference-in-Differences.
**Key Reference:** Susan Athey, Mohsen Bayati, Nikolay Doudchenko, Guido Imbens, and Khashayar Khosravi (2021). *Matrix completion methods for causal panel data models.* Journal of the American Statistical Association.

---

## Category 5: Positive Dependence and Robust Graph Estimation

*Exploiting the sign of dependence, or protecting network estimation from the extreme non-Gaussianity of economic data.*

### 17. Total Positivity (MTP2) in Macroeconomic Comovement
**Objective:** Test the hypothesis that certain macroeconomic aggregates (inflation, unemployment across regions) exhibit "Total Positivity" (MTP2), implying they always move together structurally. Estimate the precision matrix of macro indicators and check if the M-matrix property (non-positive off-diagonal elements) acts as a natural regularizer.
**Key Reference:** Raj Agrawal, Uma Roy, and Caroline Uhler (2020). *Covariance matrix estimation under total positivity for portfolio selection.* Journal of Financial Econometrics.

### 18. Positive Dependence in Labor Market Sorting
**Objective:** If high-ability workers match with high-productivity firms (assortative mating/sorting), the resulting wage distributions exhibit positive dependence. Explore how imposing structural sign constraints (like MTP2) changes the estimation of joint wage-productivity distributions.
**Key Reference:** Jan Eeckhout and Philipp Kircher (2011). *Identifying sorting—in theory.* The Review of Economic Studies.

### 19. Robust Financial Networks via Non-paranormal Estimators
**Objective:** Asset returns exhibit heavy tails, meaning Gaussian graphical models (standard glasso) are highly non-robust and estimate spurious edges during market crashes. Estimate financial dependence networks using rank-based (Kendall's tau) non-paranormal estimators to see if the recovered network structure is more stable during crises.
**Key Reference:** Han Liu, Fang Han, Ming Yuan, John Lafferty, and Larry Wasserman (2012). *High-dimensional semiparametric Gaussian copula graphical models.* The Annals of Statistics.

### 20. Dependence in Elliptical Partial Correlation Graphs
**Objective:** Investigate an alternative to the non-paranormal approach by using models explicitly designed for elliptical (heavy-tailed) distributions. Apply this to a cross-section of daily equity returns and compare the sparsity and interpretability of the network against the standard Gaussian baseline.
**Key Reference:** David Rossell and Piotr Zwiernik (2021). *Dependence in elliptical partial correlation graphs.* Electronic Journal of Statistics.

---

## Guidelines for Proposing Your Own Topic

I highly encourage you to propose your own topic, especially if it aligns with an ongoing master's thesis or early PhD research! Given the 3–4 week timeframe, an ideal custom proposal should be a targeted experiment rather than a sprawling literature review. 

If you choose to propose your own topic, it must meet the following criteria:

1. **Relevance:** It must explicitly use a methodology covered in the course (e.g., graphical models, latent variable adjustments, network spillovers, non-Gaussian identification).
2. **Empirical or Simulation Component:** You must implement the method on data (real or simulated) to see how it performs.
3. **Critical Evaluation:** Show me that you understand the mechanics of the method by testing its boundaries. 

**To propose a topic:** Submit a short, 1-page PDF outlining your economic question, the dataset or simulation you intend to use, the primary method you will apply, and 1–2 core references.
