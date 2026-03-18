# Individual Research Projects

This course bridges the gap between modern structural statistics (graphical models, latent variables, causal discovery) and applied economics. 

## Expectations for the Final Project

You will have about 3–4 weeks to complete this project. Given this short timeframe, the goal is not to produce a publishable paper or genuinely new empirical results. Instead, the objective is to actively engage with the material, demonstrating a deep understanding of a specific methodology covered in the course. 

You are welcome to approach the project from either an applied or a theoretical perspective:

**Option A: Applied / Empirical / Simulation Track**
For students interested in applied work, the goal is to take an advanced method, apply it, and test its boundaries. Pure machine learning methods often fail when applied blindly to economic data due to heavy tails, unmeasured confounding, or time-dependence. A successful applied project will:
1. **Implement** an estimator or algorithm (in R or Python).
2. **Apply** it to an economic problem, using a real-world dataset or a carefully constructed simulation.
3. **Investigate** its limitations based on economic theory (e.g., What happens to the DAG if the data is heavy-tailed instead of Gaussian? What happens to the network if a latent confounder is ignored?).

**Option B: Theory / Methodology Track**
For students leaning toward econometrics, statistics, or theoretical work, you do not need to run regressions on real data. Instead, your project can focus on the mathematical or algorithmic properties of these tools. A successful theory project might:
1. **Extend or adapt** an existing algorithm to fit a specific economic setting.
2. **Analyze** the theoretical properties of an estimator (e.g., exploring identification conditions when a standard assumption, like Gaussianity or SUTVA, is systematically relaxed).
3. **Synthesize and critique** a frontier methodological literature, providing your own theoretical proofs, counter-examples, or structural insights.

*Do not worry if an applied method "fails" on real data, or if a theoretical proof hits a dead end—documenting and explaining why the breakdown occurs is exactly what I am looking for!*

---

## Category 1: Causal Discovery and Structural Vector Autoregressions (SVARs)

*Standard macroeconomic and firm-level models often rely on arbitrary structural assumptions (like Cholesky orderings). These projects explore data-driven causal discovery, focusing on where standard algorithms fail.*

### 1. The Fragility of Gaussian DAGs in Macroeconomic Shocks
**Objective:** Standard causal discovery (like the PC algorithm) heavily uses Gaussian conditional independence tests. Applied to heavy-tailed macroeconomic data, this often produces nonsensical structural orderings. Students will apply the PC algorithm to macro time series and compare the output of standard Gaussian tests against non-parametric tests.
* **Ref 1 (Method):** Peter Spirtes, Clark Glymour, and Richard Scheines (2000). *Causation, Prediction, and Search.* (The foundational text for the PC Algorithm).
* **Ref 2 (Application):** Alessio Moneta, Nadine Chlaß, Doris Entner, and Patrick Hoyer (2013). *Causal search in structural vector autoregressive models.* Empirical Economics.

### 2. Identifying Supply and Demand via Non-Gaussianity (LiNGAM)
**Objective:** Separating demand and supply shocks usually requires valid instruments. This project uses the Linear Non-Gaussian Acyclic Model (LiNGAM) to exploit the non-Gaussianity of residuals for identification, completely bypassing the need for theoretical zero restrictions.
* **Ref 1 (Method):** Shohei Shimizu, Patrik O. Hoyer, Aapo Hyvärinen, and Antti Kerminen (2006). *A Linear Non-Gaussian Acyclic Model for Causal Discovery.* Journal of Machine Learning Research.
* **Ref 2 (Application):** Markku Lanne, Mika Meitz, and Katarzyna Maciejowska (2017). *Structural vector autoregression with non-Gaussian shocks.* Journal of Econometrics.

### 3. Causal Discovery in Institutional and Conflict Data
**Objective:** In political economy, identifying causal arrows between historical events, institutional quality, and conflict is notoriously hard. Apply discovery algorithms to historical datasets, explicitly dealing with causal sufficiency (unobserved confounders) by comparing DAG outputs to Maximal Ancestral Graphs (MAGs) via the FCI algorithm.
* **Ref 1 (Method):** Thomas Richardson and Peter Spirtes (2002). *Ancestral graph Markov models.* The Annals of Statistics.
* **Ref 2 (Application):** Doris Entner, Patrik Hoyer, and Peter Spirtes (2012). *Statistical Causal Discovery and the Role of Instrumental Variables.* JMLR Workshop and Conference Proceedings.

### 4. Firm Dynamics and Unobserved State Variables
**Objective:** Firms operate under information frictions and menu costs (themes explored by UPF macroeconomists). Students will use latent state-space models or Hidden Markov Models (HMMs) to recover unobserved discrete "regimes" in firm pricing or inventory data.
* **Ref 1 (Method):** James D. Hamilton (1989). *A new approach to the economic analysis of nonstationary time series and the business cycle.* Econometrica.
* **Ref 2 (Application):** Fernando Alvarez, Francesco Lippi, and Luigi Paciello (2011). *Optimal price setting with observation and menu costs.* The Quarterly Journal of Economics.

---

## Category 2: Network Spillovers and Interference

*In many economic settings, treating units as isolated is mathematically convenient but economically false. These projects focus on methodologies that explicitly model network interference.*

### 5. Production Networks and Macroeconomic Fluctuations
**Objective:** Microeconomic shocks to individual firms or sectors can propagate through supply chains to cause aggregate fluctuations. Estimate an undirected dependence graph of sectoral outputs and analyze how the sparsity of the precision matrix relates to the propagation of shocks.
* **Ref 1 (Theory):** Daron Acemoglu, Vasco M. Carvalho, Asuman Ozdaglar, and Alireza Tahbaz-Salehi (2012). *The network origins of aggregate fluctuations.* Econometrica.
* **Ref 2 (Application):** Vasco M. Carvalho (2014). *From micro to macro via production networks.* Journal of Economic Perspectives.

### 6. Estimating Peer Effects and Spillovers in Family/Labor Economics
**Objective:** Interventions like paternity leave reforms or health subsidies often have spillover effects on coworkers or family members. Use exposure mappings to explicitly estimate direct versus network spillover effects, relaxing the SUTVA assumption.
* **Ref 1 (Classic Econ):** Charles F. Manski (1993). *Identification of Endogenous Social Effects: The Reflection Problem.* The Review of Economic Studies.
* **Ref 2 (Modern Method):** Peter M. Aronow and Cyrus Samii (2017). *Estimating average causal effects under general interference.* The Annals of Applied Statistics.

### 7. Information Diffusion in Developing Economies
**Objective:** Model how a new agricultural technology or microfinance program spreads as a message-passing process on a village social network. Evaluate how the structure of the network impacts the diffusion rate.
* **Ref 1:** Abhijit Banerjee, Arun G. Chandrasekhar, Esther Duflo, and Matthew O. Jackson (2013). *The Diffusion of Microfinance.* Science.
* **Ref 2:** Lori Beaman, Ariel BenYishay, Jeremy Magruder, and Ahmed Mushfiq Mobarak (2021). *Can network theory-based targeting increase technology adoption?* American Economic Review.

### 8. Network Estimation for High-Dimensional Time Series (NETS)
**Objective:** Constructing dependence networks for hundreds of time series requires separating lagged dynamic effects from contemporaneous conditional dependencies. Use the NETS methodology to estimate Long Run Partial Correlation networks.
* **Ref 1 (Method):** Matteo Barigozzi and Christian Brownlees (2019). *NETS: Network estimation for time series.* Journal of Applied Econometrics.
* **Ref 2 (Application):** Francis X. Diebold and Kamil Yilmaz (2014). *On the network topology of variance decompositions: Measuring the connectedness of financial firms.* Journal of Econometrics.

---

## Category 3: High-Dimensional Controls and Proxies

*How do we perform causal inference when the confounders are either too numerous to include in an OLS regression, or entirely unobserved but captured via noisy proxies?*

### 9. Double Machine Learning for Policy Evaluation
**Objective:** Estimate the causal effect of a treatment when there is a massive number of potential confounders. Standard OLS suffers from overfitting, and naive Lasso suffers from regularization bias. Implement cross-fitted Double/Debiased Machine Learning (DML) on labor survey data.
* **Ref 1 (Method):** Victor Chernozhukov, Denis Chetverikov, Mert Demirer, Esther Duflo, Christian Hansen, Whitney Newey, and James Robins (2018). *Double/debiased machine learning for treatment and structural parameters.* The Econometrics Journal.
* **Ref 2 (Econ Context):** Alexandre Belloni, Victor Chernozhukov, and Christian Hansen (2014). *High-dimensional methods and inference on structural and treatment effects.* Journal of Economic Perspectives.

### 10. Proxy Controls for Unobserved Ability or Health
**Objective:** When an important confounder (like worker ability) is unobserved, researchers use multiple noisy proxies. Use the proximal causal inference framework to achieve non-parametric identification using a pair of proxies.
* **Ref 1 (Classic):** Manabu Kuroki and Judea Pearl (2014). *Measurement bias and effect restoration in causal inference.* Biometrika.
* **Ref 2 (Modern Method):** Wang Miao, Zhi Geng, and Eric J. Tchetgen Tchetgen (2018). *Identifying causal effects with proxy variables of an unmeasured confounder.* Biometrika.

### 11. Text as a High-Dimensional Proxy for Institutional Quality
**Objective:** Following recent trends in political economy, researchers increasingly use text as data. Extract low-dimensional latent topics or embeddings from historical text and use them as high-dimensional controls or proxies for unobserved institutional confounders.
* **Ref 1 (Review):** Matthew Gentzkow, Bryan Kelly, and Matt Taddy (2019). *Text as data.* Journal of Economic Literature.
* **Ref 2 (Application):** Stephen Hansen, Michael McMahon, and Andrea Prat (2018). *Transparency and deliberation within the FOMC: a computational linguistics approach.* The Quarterly Journal of Economics.

### 12. Synthetic Instruments for High-Dimensional Identification
**Objective:** Finding valid instruments for price in demand estimation is a classic problem. When many weak instruments are available, standard estimators suffer from severe bias. Use regularized estimators (Lasso-based IV) to construct an optimal "synthetic" instrument.
* **Ref 1:** Alexandre Belloni, Daniel Chen, Victor Chernozhukov, and Christian Hansen (2012). *Sparse models and methods for optimal instruments with an application to eminent domain.* Econometrica.
* **Ref 2:** Christian Hansen, Jerry Hausman, and Whitney Newey (2008). *Estimation with many instrumental variables.* Journal of Business & Economic Statistics.

---

## Category 4: Latent Variable Models and Market Structure

*Using latent variables to discover hidden subpopulations, unobserved market factors, or structural sorting.*

### 13. Uncovering Latent Worker and Firm Types
**Objective:** In labor economics, the sorting of workers to firms generates market power and wage inequality (a core focus of applied micro at UPF). Use Gaussian Mixtures or Latent Class Models on matched employer-employee data to recover unobserved "types" of workers and firms.
* **Ref 1 (Classic):** John M. Abowd, Francis Kramarz, and David N. Margolis (1999). *High wage workers and high wage firms.* Econometrica.
* **Ref 2 (Modern Method):** Stéphane Bonhomme, Thibaut Lamadon, and Elena Manresa (2019). *A distributional framework for matched employer employee data.* Econometrica.

### 14. Non-independent Component Analysis in Macro Factors
**Objective:** Standard factor models in macroeconomics assume latent factors are independent. In reality, unobserved macro shocks have complex, structural dependence. Apply Non-independent Component Analysis (NICA) to a macro dataset to extract latent factors and model their dependence graph.
* **Ref 1 (Method):** Geert Mesters and Piotr Zwiernik (2024). *Non-independent components analysis.* The Annals of Statistics.
* **Ref 2 (Application):** Mario Forni, Marc Hallin, Marco Lippi, and Lucrezia Reichlin (2000). *The generalized dynamic-factor model: Identification and estimation.* The Review of Economics and Statistics.

### 15. Latent Factor Discovery in Subjective Survey Data
**Objective:** Applied microeconomists often use surveys measuring trust, risk aversion, or happiness. Estimate a structural latent variable model to map discrete survey responses into underlying continuous economic preferences.
* **Ref 1:** James J. Heckman, Jora Stixrud, and Sergio Urzua (2006). *The effects of cognitive and noncognitive abilities on labor market outcomes and social behavior.* Journal of Labor Economics.
* **Ref 2:** Flavio Cunha, James J. Heckman, and Susanne M. Schennach (2010). *Estimating the technology of cognitive and noncognitive skill formation.* Econometrica.

### 16. Matrix Completion for Causal Panel Data
**Objective:** The synthetic control method recovers missing potential outcomes by exploiting latent factor structure in panel data. Apply high-dimensional matrix completion to evaluate a state-level policy change and compare the counterfactuals against standard Difference-in-Differences.
* **Ref 1 (Foundational):** Alberto Abadie, Alexis Diamond, and Jens Hainmueller (2010). *Synthetic control methods for comparative case studies: Estimating the effect of California’s tobacco control program.* Journal of the American Statistical Association.
* **Ref 2 (Modern Method):** Susan Athey, Mohsen Bayati, Nikolay Doudchenko, Guido Imbens, and Khashayar Khosravi (2021). *Matrix completion methods for causal panel data models.* Journal of the American Statistical Association.

---

## Category 5: Positive Dependence and Robust Graph Estimation

*Exploiting the sign of dependence, or protecting network estimation from the extreme non-Gaussianity of economic data.*

### 17. Total Positivity (MTP2) in Macroeconomic Comovement
**Objective:** Test the hypothesis that certain macroeconomic aggregates exhibit "Total Positivity" (MTP2), implying they always move together structurally. Estimate the precision matrix of macro indicators and check if the M-matrix property acts as a natural regularizer.
* **Ref 1 (Theory):** Shaun Fallat, Steffen Lauritzen, Kayvan Sadeghi, Caroline Uhler, Nanny Wermuth, and Piotr Zwiernik (2017). *Total positivity in Markov structures.* The Annals of Statistics.
* **Ref 2 (Finance App):** Raj Agrawal, Uma Roy, and Caroline Uhler (2020). *Covariance matrix estimation under total positivity for portfolio selection.* Journal of Financial Econometrics.

### 18. Positive Dependence in Labor Market Sorting
**Objective:** If high-ability workers match with high-productivity firms (assortative mating/sorting), the resulting wage distributions exhibit positive dependence. Explore how imposing structural sign constraints changes the estimation of joint wage-productivity distributions.
* **Ref 1 (Classic Theory):** Gary S. Becker (1973). *A Theory of Marriage: Part I.* Journal of Political Economy.
* **Ref 2 (Modern Application):** Jan Eeckhout and Philipp Kircher (2011). *Identifying sorting—in theory.* The Review of Economic Studies.

### 19. Robust Financial Networks via Non-paranormal Estimators
**Objective:** Asset returns exhibit heavy tails, meaning standard Gaussian graphical models estimate spurious edges during market crashes. Estimate financial dependence networks using rank-based non-paranormal estimators to see if the network structure is more stable during crises.
* **Ref 1 (Method):** Han Liu, Fang Han, Ming Yuan, John Lafferty, and Larry Wasserman (2012). *High-dimensional semiparametric Gaussian copula graphical models.* The Annals of Statistics.
* **Ref 2 (Refinement):** Lingzhou Xue and Hui Zou (2012). *Regularized rank-based estimation of high-dimensional nonparanormal graphical models.* The Annals of Statistics.

### 20. Dependence in Elliptical Partial Correlation Graphs
**Objective:** Investigate an alternative to the non-paranormal approach by using models explicitly designed for elliptical (heavy-tailed) distributions. Apply this to a cross-section of daily equity returns and compare the network against the standard Gaussian baseline.
* **Ref 1 (Classic Robust Network):** Michael Finegold and Mathias Drton (2011). *Robust graphical modeling of gene networks using classical and alternative t-distributions.* The Annals of Applied Statistics. 
* **Ref 2 (Modern Method):** David Rossell and Piotr Zwiernik (2021). *Dependence in elliptical partial correlation graphs.* Electronic Journal of Statistics.

---

## Guidelines for Proposing Your Own Topic

I highly encourage you to propose your own topic, especially if it aligns with an ongoing master's thesis or early PhD research! Given the 3–4 week timeframe, an ideal custom proposal should be a targeted experiment or theoretical derivation rather than a sprawling literature review. 

If you choose to propose your own topic, it must meet the following criteria:

1. **Relevance:** It must explicitly engage with a methodology covered in the course (e.g., graphical models, latent variable adjustments, network spillovers, non-Gaussian identification).
2. **Core Component:** You must either implement the method on data (real or simulated) OR provide a formal methodological/theoretical analysis.
3. **Critical Evaluation:** Show me that you understand the mechanics of the method by testing its boundaries, limits, or underlying assumptions. 

**To propose a topic:** Submit a short, 1-page PDF outlining your economic question or theoretical focus, the dataset/simulation (if applicable), the primary method you will analyze, and 1–2 core references.
