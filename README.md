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
* Convex optimization  
* Convex-concave optimization 

# Resources 

## Courses  

* [Algorithimic Foundations of Learning](http://www.stats.ox.ac.uk/~rebeschi/teaching/AFoL/19/index.html) by Patrick Rebeschini, University of Oxford   



## Books 

* [Combinatorial Methods in Density Estimation](https://link.springer.com/book/10.1007/978-1-4613-0125-7) by Luc Devroye and Gabor Lugosi.    
* [Concentration inequalities A nonasymptotic theory of independence](https://www.oxfordscholarship.com/view/10.1093/acprof:oso/9780199535255.001.0001/acprof-9780199535255) by Stephane Boucheron, Gabor Lugosi, and Pascal Massart.


## Applications 

### Off-policy evaluation   
* [DualDICE: Behavior-Agnostic Estimation of Discounted Stationary Distribution Corrections](https://arxiv.org/abs/1906.04733): The square of an expectation in Eq. (6) is ugly and difficult to compute in practice, thus it is desirable to resolve this issue. Frenchet duality comes to the rescue by transforming such difficulty to the well-studied difficulty of convex-concave optimization. 
