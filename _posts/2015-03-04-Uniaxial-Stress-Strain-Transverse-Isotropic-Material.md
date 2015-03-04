---
layout: post
title: Uniaxial Stress and Uniaxial Strain for Transversely Isotropic Material
date: 2015-02-27
author: Matthew W. Priddy
meta: Mechanics, 
cover: "/images/IMAG1336.jpg"
---

Some of the boundary conditions I have recently been using have been uniaxial strain instead of the typical uniaxial stress and there is an obvious difference in the elastic modulus of the material system, which in this case is \( \alpha \)-Ti in Ti-6Al-4V.  

While searching the web for a simple display of the necessary equations, I came across [this post](http://csmbrannon.net/2012/08/02/distinction-between-uniaxial-stress-and-uniaxial-strain/) that details the differences uniaxial stress and uniaxial strain for a linear-elastic, isotropic material.  In summary, the "constrained modulus" is higher than the elastic modulus.  

However, their equations are too simplistic to apply for our transversely isotropic material.  Isotropic materials have two independent elastic constants (E and \( \nu \)) and transversely isotropic materials have five independent elastic constants \(( C_{11}, C{33}, C_{44}, C{12}, and C_{13} )\).  So the \( \sigma = E \epsilon \) looks like:

$$  \left( \begin{array}{ccc} 
\phi(e_1, e_1) & \cdots & \phi(e_1, e_n) \ 
\vdots & \ddots & \vdots \ 
\phi(e_n, e_1) & \cdots & \phi(e_n, e_n) 
\end{array} \right) 
\left( \begin{array}{c} y_1 \ \vdots \ y_n \end{array} \right) 
$$

$$ 
\phi(x,y) = \phi \left(\sum_{i=1}^n x_ie_i, \sum_{j=1}^n y_je_j \right) = \sum_{i=1}^n \sum_{j=1}^n x_i y_j \phi(e_i, e_j) = \ (x_1, \ldots, x_n) 

\left( \begin{array}{ccc} \phi(e_1, e_1) & \cdots & \phi(e_1, e_n) \ \vdots & \ddots & \vdots \ \phi(e_n, e_1) & \cdots & \phi(e_n, e_n) \end{array} \right) \left( \begin{array}{c} y_1 \ \vdots \ y_n \end{array} \right) 
$$
