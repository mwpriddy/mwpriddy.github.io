---
layout: post
title: Anisotropic Elasticity for HCP Crystal Structures
date: 2015-03-10
author: Matthew W. Priddy
meta: Mechanics 
cover: "http://demonstrations.wolfram.com/AnisotropicElasticityForHCPCrystalStructures/HTMLImages/index.en/popup_1.jpg"
---

When I was first learning about Mg and Ti alloys, I was having trouble picturing the anisotropic nature of their respective elastic moduli.  As was shown in a [previous post about uniaxial stress and strain](http://mwpriddy.github.io/blog/2015/03/04/UniStressStrain/), the the stiffness tensor for transversely isotropic materials (e.g. hexagonal close packed material systems) has five independent elastic constants and takes the following form:

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

But, the change in the elastic modulus can be hard to determine with an arbitrary material orientation.  Then I came across [Dr. Megan Frary's Wolfram Demonstration](http://demonstrations.wolfram.com/AnisotropicElasticity/) that graphically represents the elastic modulus for uniaxial stress loading versus material orientation for FCC crystal structures.  I also came across a similar, although in paper form, representation for HCP crystal structures in a journal article by [Tromans in (2011)](http://www.arpapress.com/volumes/vol6issue4/ijrras_6_4_14.pdf).

I thought it would be a good idea to create a Wolfram Demonstration from the concepts presented in Tromans (2011), following the example created by Dr. Frary, and the result is below; a Wolfram Demonstration GUI that graphically illustrates the elastic modulus versus orientation for all of the 24 different HCP metals.

<div align="center">
  <script type='text/javascript' src='http://demonstrations.wolfram.com/javascript/embed.js' ></script>
  <script type='text/javascript'>var demoObj = new DEMOEMBED(); demoObj.run('AnisotropicElasticityForHCPCrystalStructures', '', '439', '628');</script>
  <div id='DEMO_AnisotropicElasticityForHCPCrystalStructures'>
    <a class='demonstrationHyperlink' href='http://demonstrations.wolfram.com/AnisotropicElasticityForHCPCrystalStructures/' target='_blank'>Anisotropic Elasticity for HCP Crystal Structures</a> from the <a class='demonstrationHyperlink' href='http://demonstrations.wolfram.com/' target='_blank'>Wolfram Demonstrations Project</a> by Matthew W. Priddy
  </div><br />
</div>

The Wolfram Demonstration takes a little more time to code and document, but the result is something that multiple people can utilize and use as a learning tool.  Enjoy! 
