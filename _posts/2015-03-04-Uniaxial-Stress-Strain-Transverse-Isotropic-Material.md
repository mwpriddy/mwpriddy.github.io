---
layout: post
title: Uniaxial Stress and Uniaxial Strain for Transversely Isotropic Material
date: 2015-03-04
author: Matthew W. Priddy
meta: Mechanics 
cover: "/images/TT-5912.jpg"
---

Some of the boundary conditions I have recently been using have been uniaxial strain instead of the typical uniaxial stress and there is an obvious difference in the elastic modulus of the material system, which in this case is $$\alpha$$-Ti in Ti-6Al-4V.  

While searching the web for a simple display of the necessary equations, I came across [this post](http://csmbrannon.net/2012/08/02/distinction-between-uniaxial-stress-and-uniaxial-strain/) that details the differences uniaxial stress and uniaxial strain for a linear-elastic, isotropic material.  In summary, the "constrained modulus" is higher than the elastic modulus.  

However, their equations are too simplistic to apply for our transversely isotropic material.  Isotropic materials have two independent elastic constants (E and $$\nu$$) and transversely isotropic materials have five independent elastic constants ($$C_{11}, C_{33}, C_{44}, C_{12},$$ and $$C_{13}$$).  So the $$\sigma = E \epsilon$$ looks like:

$$
\begin{equation}
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
\end{equation}
$$

## Three-Dimensional Hooke's Law

For the duration of this post, let us assume that shear stresses/strains are zero.  This will become clear in later sections of this discussion, mainly because were aren't applying any shearing to our deformed volume.  Also, lets assume the material is fully anisotropic, therefore Hooke's law now looks something like

$$
\begin{equation}
\begin{pmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{33} \\ 
\end{pmatrix} = 
\begin{pmatrix}
  c_{11} & c_{12} & c_{13} \\
  c_{12} & c_{22} & c_{23} \\
  c_{13} & c_{23} & c_{33} \\
\end{pmatrix}
\begin{pmatrix}
\epsilon_{11} \\ \epsilon_{22} \\ \epsilon_{33} \\ 
\end{pmatrix}
\end{equation}
$$

For general anisotropic elasticity, we can see there are 3 equations and 6 unknowns.  

## Uniaxial Strain

If the strain is applied in a uniaxial manner, such that $$\epsilon_{11}=\epsilon_{app}$$ and  $$\epsilon_{22}=\epsilon_{33}=0$$, then the stress-state reduces to

$$
\begin{align}
  \sigma_{11} &= c_{11}\epsilon_{11} \nonumber \\
  \sigma_{22} &= c_{12}\epsilon_{11}  \\
  \sigma_{33} &= c_{13}\epsilon_{11} \nonumber
\end{align}
$$

If we perform similar uniaxial strain deformation (i.e. $$\epsilon_{22}=\epsilon_{app}$$ and $$\epsilon_{33}=\epsilon_{app}$$ that provides us with 9 equations and only 6 unknowns.  Therefore, we have sufficient information to determine the six elastic constants.  

## Uniaxial Stress

However, the Young's modulus of the material is recorded from uniaxial stress boundary conditions, meaning $$\sigma_{11}=\sigma_{app}$$ and $$\sigma_{22}=\sigma_{33}=0$$.  However, 3D Hooke's law is not a trivial solution for this stress-state, because there are multiple non-zero strain components.

$$
\begin{align}
  \sigma_{11} &= c_{11}\epsilon_{11} + c_{12}\epsilon_{22} + c_{13}\epsilon_{33}     \nonumber \\
  \sigma_{22} &= c_{12}\epsilon_{11} + c_{22}\epsilon_{22} + c_{23}\epsilon_{33} = 0  \\
  \sigma_{33} &= c_{13}\epsilon_{11} + c_{23}\epsilon_{22} + c_{33}\epsilon_{33} = 0 \nonumber
\end{align}
$$

Again, a similar procedure can be performed for uniaxial stress loadings in the y- and z-directions, e.g. $$\sigma_{22}=\epsilon_{app}$$ and $$\sigma_{33}=\epsilon_{app}$$.  

It takes quite a few steps of algebra to solve for each strain component, or you can use your favorite mathematic intepretor like Mathematica.  But, this solution is a direct link to Young's modulus in each of the 3 loading directions.  The final equations for the relation between stress and strain in the 3 loading directions:

$$
\begin{align}
\sigma_{11} &= \left(\frac{c_{13}^2c_{22} - 2c_{12}c_{13}c_{23} + c_{12}^2c_{33} + c_{23}^2c_{11} - c_{11}c_{22}c_{33}}{c_{23}^2 - c_{22}c_{33}}\right)\epsilon_{11} \nonumber \\

\sigma_{22} &= \left(\frac{c_{13}^2c_{22} - 2c_{12}c_{13}c_{23} + c_{12}^2c_{33} + c_{23}^2c_{11} - c_{11}c_{22}c_{33}}{c_{13}^2 - c_{11}c_{33}}\right)\epsilon_{22} \\

\sigma_{33} &= \left(\frac{c_{13}^2c_{22} - 2c_{12}c_{13}c_{23} + c_{12}^2c_{33} + c_{23}^2c_{11} - c_{11}c_{22}c_{33}}{c_{12}^2 - c_{11}c_{22}}\right)\epsilon_{33} \nonumber
\end{align}
$$

*Featured image courtesy of [GT Digital Archive](http://www.comm.gatech.edu/resources/photo-video).
