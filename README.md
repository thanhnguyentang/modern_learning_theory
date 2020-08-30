# MFLI: Mathematical Foundations of Learning and Inference

# Introduction  

The ultimate goal is to derive new efficient principled algorithms with theoretical guarantees for learning and inference problems arising from modern practical settings. There are three elements constructing the goal: (i) principled algorithms, (ii) theoretical guarantees and (iii) modern practical settings (of learning and inference). 

The idea is to master foundational tools and use them to address a diverse range of modern ML problems. For me, such foundational tools are *optimization* and *probability theory*. 

## (i) Principled algorithms 

* Rooted in a principled foundation such as probability theory or optimization. 

* Efficient in practice.  

## (ii) Theoretical guarantees 

* Consistency 

* Large-sample analysis  

* Rate of convergence  

## (iii) Modern practical settings 

I mostly focus on off-policy evaluation problem. 


# Mathematical foundations  

## Concentration inequalities   
* VC shatter coefficient and VC dimension  
* Classic concentration inequalities 
* [Martingales](http://www.math.ucsd.edu/~fan/wp/concen.pdf)


## Rate of convergence   
* Uniform convergence bounds  
* Minimax rate of convergence 

## Optimization   
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

## Statistics   

### [Variance reduction](http://statweb.stanford.edu/~owen/mc/)  
* Antithetic sampling: leverage the symmetry of the density to get more error cancellation.  
* Stratification: Split the domain of the random variable into separate regions, and take samples from each region to estimate a target quantity.  
* Coupling (or common random numbers): One common random variable Z that generates two other random variables X and Y, so when estimate the quantity f(X,Y), it is better to generate Z first to use for both X(Z) and Y(Z).   
* Conditioning: E[f(X,Y)] = E[h(X)] where h(X) = E[f(X,Y) | X]. 
* [Rao-Maxwellization](https://en.wikipedia.org/wiki/Rao%E2%80%93Blackwell_theorem)  
* Control variates (and control variates by regression): Let's say we want to estimate E[f(X)]. If we have h ~ f and E[h(X)] is known, then h(X) is a control variate. We can construct a new estimator based on any crude estimator of E[f(X)] and the control variate. This results in a smaller variance.  
* Moment matching and reweghting: Suppose we want to estimate E[f(X)] and we know E[X], we can use h(X) = X as control variate.  Reweighting is control variate via regression in moment matching case. 

### Statistical bounds  
* Cramer-Rao lower bounds: [Wikipedia](https://en.wikipedia.org/wiki/Cram%C3%A9r%E2%80%93Rao_bound), [PhD thesis](https://drum.lib.umd.edu/bitstream/handle/1903/10290/Moore_umd_0117E_11120.pdf?sequence=1&isAllowed=y)
* Minimax lower bounds 

### [Delta method](https://en.wikipedia.org/wiki/Delta_method)

## Probability theory  
* [Central limit theorem](https://en.wikipedia.org/wiki/Central_limit_theorem)  
* [Order of approximation](https://en.wikipedia.org/wiki/Big_O_in_probability_notation)  
* [Convergence of random variables](https://en.wikipedia.org/wiki/Convergence_of_random_variables)  

# Resources 

## Courses  

* [Algorithimic Foundations of Learning](http://www.stats.ox.ac.uk/~rebeschi/teaching/AFoL/19/index.html) by Patrick Rebeschini, University of Oxford   
* [Statistical methods for ML](http://www.stat.cmu.edu/~larry/=sml/)



## Books / Notes

* [Combinatorial Methods in Density Estimation](https://link.springer.com/book/10.1007/978-1-4613-0125-7) by Luc Devroye and Gabor Lugosi.   
* [Probability in High Dimension](https://web.math.princeton.edu/~rvan/APC550.pdf) by Ramon van Handel.
* [Concentration inequalities A nonasymptotic theory of independence](https://www.oxfordscholarship.com/view/10.1093/acprof:oso/9780199535255.001.0001/acprof-9780199535255) by Stephane Boucheron, Gabor Lugosi, and Pascal Massart. 
* [Understanding machine learning: From theory to algorithms](https://www.cs.huji.ac.il/~shais/UnderstandingMachineLearning/understanding-machine-learning-theory-algorithms.pdf) by Shai Shalev-Shwartz and Shai Ben-David  

## Seminars  
* [RL theory seminars](https://sites.google.com/view/rltheoryseminars/home)  

## Applications 

### Off-policy evaluation   
* [DualDICE: Behavior-Agnostic Estimation of Discounted Stationary Distribution Corrections](https://arxiv.org/abs/1906.04733): The square of an expectation in Eq. (6) is ugly and difficult to compute in practice, thus it is desirable to resolve this issue. Frenchet duality comes to the rescue by transforming such difficulty to the well-studied difficulty of convex-concave optimization. 

### General principles  
* When a class of methods have strikingly common elements, it could be a good time to think about a unifying view of them. 

### Optimimization foundations of RL 
