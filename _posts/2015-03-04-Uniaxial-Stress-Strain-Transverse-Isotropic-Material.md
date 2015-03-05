---
layout: post
title: Uniaxial Stress and Uniaxial Strain for Transversely Isotropic Material
date: 2015-02-27
author: Matthew W. Priddy
meta: Mechanics, 
cover: "/images/IMAG1336.jpg"
---

Some of the boundary conditions I have recently been using have been uniaxial strain instead of the typical uniaxial stress and there is an obvious difference in the elastic modulus of the material system, which in this case is $$\alpha$$-Ti in Ti-6Al-4V.  

While searching the web for a simple display of the necessary equations, I came across [this post](http://csmbrannon.net/2012/08/02/distinction-between-uniaxial-stress-and-uniaxial-strain/) that details the differences uniaxial stress and uniaxial strain for a linear-elastic, isotropic material.  In summary, the "constrained modulus" is higher than the elastic modulus.  

However, their equations are too simplistic to apply for our transversely isotropic material.  Isotropic materials have two independent elastic constants (E and $$\nu$$) and transversely isotropic materials have five independent elastic constants ($$C_{11}, C_{33}, C_{44}, C_{12},$$ and $$C_{13}$$).  So the $$\sigma = E \epsilon$$ looks like:

$$
\begin{pmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{33} \\ \sigma_{13} \\ \sigma_{23} \\ \sigma_{12} \\ 
\end{pmatrix} = 
\begin{pmatrix}
  c_{11} & c_{12} & c_{13} & 0 & 0 & 0 \\
  c_{12} & c_{11} & c_{13} & 0 & 0 & 0 \\
  c_{13} & c_{13} & c_{33} & 0 & 0 & 0 \\
  0 & 0 & 0 & c_{44} & 0 & 0 \\
  0 & 0 & 0 & 0 & c_{44} & 0 \\
  0 & 0 & 0 & 0 & 0 & c_{66} \\
\end{pmatrix}
\begin{pmatrix}
\epsilon_{11} \\ \epsilon_{22} \\ \epsilon_{33} \\ \gamma_{13} \\ \gamma_{23} \\ \gamma_{12} \\ 
\end{pmatrix}
$$

## Three-Dimensional Hooke's Law

The above matrix can be reduced to the following equations for stress

$$
\begin{align}
  \sigma_{11} &= c_{11}\epsilon_{11} + c_{12}\epsilon_{22} + c_{13}\epsilon_{33} \\
  \sigma_{22} &= c_{12}\epsilon_{11} + c_{11}\epsilon_{22} + c_{13}\epsilon_{33} \\
  \sigma_{33} &= c_{13}\epsilon_{11} + c_{13}\epsilon_{22} + c_{33}\epsilon_{33}
\end{align}
$$

and, if we invert the C matrix, they can also be written for strain

## Uniaxial Stress

If the stress-state is 1D, lets say $$\sigma_{22}=\sigma_{33}=0$$, then from the above equation it can be shown that

$$
\begin{align}
  \sigma_{11} &= c_{11}\epsilon_{11} + c_{12}\epsilon_{22} + c_{13}\epsilon_{33} \\
  \sigma_{22} &= c_{12}\epsilon_{11} + c_{11}\epsilon_{22} + c_{13}\epsilon_{33} = 0 \\
  \sigma_{33} &= c_{13}\epsilon_{11} + c_{13}\epsilon_{22} + c_{33}\epsilon_{33} = 0
\end{align}
$$


## Uniaxial Strain

On the other hand, if the strain is applied such that $$\epsilon_{22}=\epsilon_{33}=0$$, then the stress-state reduces to

$$
\begin{align}
  \sigma_{11} &= c_{11}\epsilon_{11} \\
  \sigma_{22} &= c_{12}\epsilon_{11} \\
  \sigma_{33} &= c_{13}\epsilon_{11}
\end{align}
$$

and the 

