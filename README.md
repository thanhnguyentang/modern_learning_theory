# MFLI: Mathematical Foundations of Learning and Inference

# Introduction  

The ultimate goal is to derive new efficient principled algorithms with theoretical guarantees for learning and inference problems arising from modern practical settings. There are three elements constructing the goal: (i) principled algorithms, (ii) theoretical guarantees and (iii) modern practical settings (of learning and inference). 

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

## Rate of convergence   
* Uniform convergence bounds  

## Optimization   
* Frenchet duality
* The interchangeability principle 
* Convex optimization  
* Convex-concave optimization 

## Statistics   

### [Variance reduction](http://statweb.stanford.edu/~owen/mc/)  
* Antithetic sampling: leverage the symmetry of the density to get more error cancellation.  
* Stratification: Split the domain of the random variable into separate regions, and take samples from each region to estimate a target quantity.  
* Coupling (or common random numbers): One common random variable Z that generates two other random variables X and Y, so when estimate the quantity f(X,Y), it is better to generate Z first to use for both X(Z) and Y(Z).   
* Conditioning: E[f(X,Y)] = E[h(X)] where h(X) = E[f(X,Y) | X]. 
* [Rao-Maxwellization](https://en.wikipedia.org/wiki/Rao%E2%80%93Blackwell_theorem)  
* Control variates (and control variates by regression): Let's say we want to estimate E[f(X)]. If we have h ~ f and E[h(X)] is known, then h(X) is a control variate. We can construct a new estimator based on any crude estimator of E[f(X)] and the control variate. This results in a smaller variance.  
* Moment matching and reweghting: Suppose we want to estimate E[f(X)] and we know E[X], we can use h(X) = X as control variate.  Reweighting is control variate via regression in moment matching case. 


### [Delta method](https://en.wikipedia.org/wiki/Delta_method)

## Probability theory  
* [Central limit theorem](https://en.wikipedia.org/wiki/Central_limit_theorem)  
* [Convergence of random variables](https://en.wikipedia.org/wiki/Big_O_in_probability_notation)  
* [Order of approximation](https://en.wikipedia.org/wiki/Convergence_of_random_variables)  

# Resources 

## Courses  

* [Algorithimic Foundations of Learning](http://www.stats.ox.ac.uk/~rebeschi/teaching/AFoL/19/index.html) by Patrick Rebeschini, University of Oxford   



## Books 

* [Combinatorial Methods in Density Estimation](https://link.springer.com/book/10.1007/978-1-4613-0125-7) by Luc Devroye and Gabor Lugosi.    
* [Concentration inequalities A nonasymptotic theory of independence](https://www.oxfordscholarship.com/view/10.1093/acprof:oso/9780199535255.001.0001/acprof-9780199535255) by Stephane Boucheron, Gabor Lugosi, and Pascal Massart.


## Applications 

### Off-policy evaluation   
* [DualDICE: Behavior-Agnostic Estimation of Discounted Stationary Distribution Corrections](https://arxiv.org/abs/1906.04733): The square of an expectation in Eq. (6) is ugly and difficult to compute in practice, thus it is desirable to resolve this issue. Frenchet duality comes to the rescue by transforming such difficulty to the well-studied difficulty of convex-concave optimization. 
