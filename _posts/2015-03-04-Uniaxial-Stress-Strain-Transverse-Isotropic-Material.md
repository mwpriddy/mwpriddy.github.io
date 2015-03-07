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

However, their equations are too simplistic to apply for our transversely isotropic material.  Isotropic materials have two independent elastic constants (E and $$\nu$$) and transversely isotropic materials have five independent elastic constants ($$C_{11}, C_{33}, C_{44}, C_{12},$$ and $$C_{13}$$).  So the relationship between stress and strain $$\left(\sigma_{ij} = C_{ijkl} \epsilon_{kl}\right)$$ looks like:

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

For the duration of this post, let us assume that shear stresses/strains are zero.  This will become clear in later sections of this discussion, mainly because were aren't applying any shearing to our deformed volume.  Also, lets assume the material is fully anisotropic because that will include any arbitrary crystal orientation of the material.  3D Hooke's law is now:

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
\label{eqn: Hooke3D}
$$

From the above equation, we can see there are only 6 independent stiffnes matrix values due to symmetry.  

## Uniaxial Strain

If the strain is applied in a uniaxial manner, such that $$\epsilon_{11}=\epsilon_{app}$$ and  $$\epsilon_{22}=\epsilon_{33}=0$$, then the stress-state reduces to

$$
\begin{align}
  \sigma_{11} &= c_{11}\epsilon_{11}  \\
  \sigma_{22} &= c_{12}\epsilon_{11}  \\
  \sigma_{33} &= c_{13}\epsilon_{11} 
\end{align}
$$

If we perform similar uniaxial strain deformation (i.e. $$\epsilon_{22}=\epsilon_{app}$$ and $$\epsilon_{33}=\epsilon_{app}$$) that provides us with 9 equations and only 6 unknowns.  Therefore, we have sufficient information to determine the six elastic constants.  

## Uniaxial Stress

However, the Young's modulus of the material is recorded from uniaxial stress boundary conditions, meaning $$\sigma_{11}=\sigma_{app}$$ and $$\sigma_{22}=\sigma_{33}=0$$.  But, from Eqn. \ref{eqn: Hooke3D}, Hooke's law is not a trivial solution for this stress-state, because there are multiple non-zero strain components, as shown below.

$$
\begin{align}
  \sigma_{11} &= c_{11}\epsilon_{11} + c_{12}\epsilon_{22} + c_{13}\epsilon_{33} \nonumber \\
            0 &= c_{12}\epsilon_{11} + c_{22}\epsilon_{22} + c_{23}\epsilon_{33} \\
            0 &= c_{13}\epsilon_{11} + c_{23}\epsilon_{22} + c_{33}\epsilon_{33} \nonumber
\end{align}
$$

Again, a similar procedure can be performed for uniaxial stress loadings in the y- and z-directions, e.g. $$\sigma_{22}=\epsilon_{app}$$ and $$\sigma_{33}=\epsilon_{app}$$.  

We can also define the compliance matrix, which is simply the inverse of the stiffness matrix, as shown below.

$$
\begin{equation}
\begin{pmatrix}
\epsilon_{11} \\ \epsilon_{22} \\ \epsilon_{33} \\ 
\end{pmatrix} = 
\begin{pmatrix}
  s_{11} & s_{12} & s_{13} \\
  s_{12} & s_{22} & s_{23} \\
  s_{13} & s_{23} & s_{33} \\
\end{pmatrix}
\begin{pmatrix}
\sigma_{11} \\ \sigma_{22} \\ \sigma_{33} \\ 
\end{pmatrix}
\longrightarrow
\begin{pmatrix}
  s_{11} & s_{12} & s_{13} \\
  s_{12} & s_{22} & s_{23} \\
  s_{13} & s_{23} & s_{33} \\
\end{pmatrix} =
\begin{pmatrix}
  c_{11} & c_{12} & c_{13} \\
  c_{12} & c_{22} & c_{23} \\
  c_{13} & c_{23} & c_{33} \\
\end{pmatrix}^{-1}
\end{equation}
$$

Given the compliance matrix,the elastic modulus for each loading direction is easily determined given uniaxial stress boundary conditions.

$$
\begin{equation}
\begin{align}
  \epsilon_{11} &= s_{11}\sigma_{11} \longrightarrow E_{1} = \frac{1}{s_{11}} \nonumber \\
  \epsilon_{22} &= s_{22}\sigma_{22} \longrightarrow E_{2} = \frac{1}{s_{22}} \\
  \epsilon_{33} &= s_{33}\sigma_{33} \longrightarrow E_{3} = \frac{1}{s_{33}} \nonumber
\end{align}
\end{equation}
\label{eqn: ElasticModuli}
$$

Therefore, after determining the stiffness matrix, a simple matrix inversion can be used to determine the elastic moduli for the three orthogonal loading directions of a 3D specimen.

## Application of Above Solution

Like I stated previously, we have been employing uniaxail strain boundary conditions for some of our linear-elastic simulations recently.  In order to determine the elastic modulus of those 3D polycrystalline digital microstructures, we will employ the method described above.  The digital microstructures are loaded in three orthogonal directions (x-, y-, and z-directions) where the overall strain is known $$\left( \epsilon_{app} \right)$$ for the loading direction and the stress components are known for each element (voxel).  A volume average of the stress components provides the value for each macroscopic normal stress, which can then be used to calculate the individual components of the stiffness matrix.

$$
\begin{equation}
\langle \sigma_{kl} \rangle = \displaystyle \sum_{i=1}^{N} \frac{\sigma_{kl}}{N} 
\end{equation}
\label{eqn: VolAvg}
$$

Once the stiffness matrix is determined, invert the stiffness matrix and the elastic moduli are known for each loading direction, per Eqn. \ref{eqn: ElasticModuli}.

*Featured image courtesy of [GT Digital Archive](http://www.comm.gatech.edu/resources/photo-video).
