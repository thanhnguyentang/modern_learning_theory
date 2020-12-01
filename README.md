# Foundations of Learning and Inference (FLI)

# 1. Introduction  
In this repo, I keep track of the pointers to several important resources and notions for FLI. This is expected to be useful for self-taught learners who are bulding a mathametical backgroun for machine learning research. By foundations, I currently refer to probability theory, statistics and optimization perspectives of learning and inference (this stance can be incrementally improved in the future). The ultimate goal is to derive new efficient principled algorithms with theoretical guarantees for learning and inference problems arising from *modern* *practical* settings. To me, there are three main elements constructing the goal: (i) principled algorithms, (ii) theoretical guarantees and (iii) modern practical settings (of learning and inference). 

* Principled algorithms 
  * Rooted in a principled foundation such as probability theory or optimization. 
  * Efficient in practice.  

* Theoretical guarantees 
  * Asymptotic consistency 
  * Large-sample analysis  
  * Rate of convergence  

* Modern practical settings 
  * I mostly focus on off-policy evaluation problem. 


# 2. Background  

* Concentration inequalities   
  * VC shatter coefficient and VC dimension  
  * Classic concentration inequalities 
  * [Martingales](http://www.math.ucsd.edu/~fan/wp/concen.pdf)


* Rate of convergence   
  * Uniform convergence bounds  
  * Minimax rate of convergence 
  
* Optimization   
   * Frenchet duality
   * The interchangeability principle 
   * Convex optimization  
   * Convex-concave optimization  
   * Min-max problem by taking a function class to be a unit ball of RKHS 
   * Linear programming and convex duality  (e.g., an example of application, this [talk](http://cs.bme.hu/~gergo/files/NPB20_s.pdf)). Convex duality is often used to reformulate an objective so that it can be represented via empirical samples. 
   * R Tyrrell Rockafellar. Augmented Lagrange multiplier functions and duality in nonconvex programming. SIAM Journal on Control, 12(2):268–285, 1974.
   * Convex optimization book by Rockafellar
   * Convex analysis book by Boyd 
   * Reinforcement Learning via Fenchel-Rockafellar Duality

* Statistics   
  * [Variance reduction](http://statweb.stanford.edu/~owen/mc/)  
    * Antithetic sampling: leverage the symmetry of the density to get more error cancellation.  
    * Stratification: Split the domain of the random variable into separate regions, and take samples from each region to estimate a target quantity.  
    * Coupling (or common random numbers): One common random variable Z that generates two other random variables X and Y, so when estimate the quantity f(X,Y), it is better to generate Z first to use for both X(Z) and Y(Z).   
    * Conditioning: E[f(X,Y)] = E[h(X)] where h(X) = E[f(X,Y) | X]. 
    * [Rao-Maxwellization](https://en.wikipedia.org/wiki/Rao%E2%80%93Blackwell_theorem)  
    * Control variates (and control variates by regression): Let's say we want to estimate E[f(X)]. If we have h ~ f and E[h(X)] is known, then h(X) is a control variate. We can construct a new estimator based on any crude estimator of E[f(X)] and the control variate. This results in a smaller variance.  
    * Moment matching and reweghting: Suppose we want to estimate E[f(X)] and we know E[X], we can use h(X) = X as control variate.  Reweighting is control variate via regression in moment matching case. 

  * Statistical bounds  
    * Cramer-Rao lower bounds: [Wikipedia](https://en.wikipedia.org/wiki/Cram%C3%A9r%E2%80%93Rao_bound), [PhD thesis](https://drum.lib.umd.edu/bitstream/handle/1903/10290/Moore_umd_0117E_11120.pdf?sequence=1&isAllowed=y)
    * Minimax lower bounds 
  * [Delta method](https://en.wikipedia.org/wiki/Delta_method)

* Probability theory  
  * [Central limit theorem](https://en.wikipedia.org/wiki/Central_limit_theorem)  
  * [Order of approximation](https://en.wikipedia.org/wiki/Big_O_in_probability_notation)  
  * [Convergence of random variables](https://en.wikipedia.org/wiki/Convergence_of_random_variables)  

# 3. Resources 
* Courses  
  * [Algorithimic Foundations of Learning](http://www.stats.ox.ac.uk/~rebeschi/teaching/AFoL/19/index.html) by Patrick Rebeschini, University of Oxford   
  * [Statistical methods for ML](http://www.stat.cmu.edu/~larry/=sml/)

* Books / Notes
  * Stats 
    * [Combinatorial Methods in Density Estimation](https://link.springer.com/book/10.1007/978-1-4613-0125-7) by Luc Devroye and Gabor Lugosi.   
    * [Probability in High Dimension](https://web.math.princeton.edu/~rvan/APC550.pdf) by Ramon van Handel.
    * [Concentration inequalities A nonasymptotic theory of independence](https://www.oxfordscholarship.com/view/10.1093/acprof:oso/9780199535255.001.0001/acprof-9780199535255) by Stephane Boucheron, Gabor Lugosi, and Pascal Massart. 
    * [Understanding machine learning: From theory to algorithms](https://www.cs.huji.ac.il/~shais/UnderstandingMachineLearning/understanding-machine-learning-theory-algorithms.pdf) by Shai Shalev-Shwartz and Shai Ben-David   
    * [A Distribution-Free Theory of Nonparametric Regression](http://www-leland.stanford.edu/class/ee378a/books/book1.pdf) by Gyorfi et al.  
    * [Foundations of ML](https://pdfs.semanticscholar.org/e923/9469aba4bccf3e36d1c27894721e8dbefc44.pdf) by Mohri et al. 
    * [Probability and Measure](https://www.colorado.edu/amath/sites/default/files/attached-files/billingsley.pdf) by PATRICK BILLINGSLEY

  * Optimization  
    * [Algorithms for convex optimization](https://convex-optimization.github.io/ACO-v1.pdf)   
    * R Tyrrell Rockafellar. Augmented Lagrange multiplier functions and duality in nonconvex programming. SIAM Journal on Control, 12(2):268–285, 1974.
    * Convex optimization book by Rockafellar
    * Convex analysis book by Boyd 
    * Reinforcement Learning via Fenchel-Rockafellar Duality

* Seminars  
  * [RL theory seminars](https://sites.google.com/view/rltheoryseminars/home)  

* Events 
  * [Mathematics of ML](https://mathml2020.github.io/): LMS-Bath Symposium, 3-7 August 2020, University of Bath 

* Applications 
  * Off-policy evaluation   
    * [DualDICE: Behavior-Agnostic Estimation of Discounted Stationary Distribution Corrections](https://arxiv.org/abs/1906.04733): The square of an expectation in Eq. (6) is ugly and difficult to compute in practice, thus it is desirable to resolve this issue. Frenchet duality comes to the rescue by transforming such difficulty to the well-studied difficulty of convex-concave optimization. 

* General principles  
  * When a class of methods have strikingly common elements, it could be a good time to think about a unifying view of them. 
  
  
* Papers
  * [Is Temporal Difference Learning Optimal? An Instance-Dependent Analysis](https://arxiv.org/abs/2003.07337), 2020 
  * [Instance-dependent ℓ∞-bounds for policy evaluation in tabular reinforcement learning](https://arxiv.org/abs/1909.08749), 2020 
  * [An Almost Constant Lower Bound of the Isoperimetric Coefficient in the KLS Conjecture](https://arxiv.org/pdf/2011.13661.pdf), 2020
