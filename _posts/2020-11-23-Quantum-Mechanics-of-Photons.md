---
layout: post
title:  "Quantum Mechanics of Photons"
author: Aadarsh 
categories: [ Quantum Mech, Quatnum Crypto ]
image: assets/images/divide_and_conquer.jpg
usemathjax: true
---






\documentclass[12pt,letterpaper]{article}
\usepackage{amsmath}
\usepackage{circuitikz}
\usepackage{amssymb}
\usepackage{hyperref}
\newcommand{\bd}{\textbf}
\usepackage{amsmath}
\usepackage{amsfonts}
\newcommand{\e}[1]{{\mathbb E}\left[ #1 \right]}
\documentclass{article}

\usepackage{braket}


\begin{document}

\title{Quantum Mechanics of Polarised Photons}


Classically, the polarisation of light refers to the direction of oscillation of the electric field. However, in the early 20th century, experiments like the photo electric effect proved that light can also behave like a stream of particles, called photons. However, when we accept this explanation the meaning of polarisation becomes unclear, as the stream of photons does not consist of an oscillating field. To understand whether polarisation exist at the individual photon level, scientists experimented with very low intensity light(eventually reaching an intensity where the light ray is a stream of individual photons) and noticed that these photons behaved in the exact same way a beam of polarised light behaves. As a result, they were forced to conclude that polarisation is an inherent property of each photon. 

\newline
Mathematically, we describe the polarisation of photons using polarised states, which are essentially vectors in a 2-dimensional vector space. The space is two dimensional because polarisation is always in the plane perpendicular to the direction of motion of the photon.  

Let $\ket{\theta}$ represent a photon moving in the z direction that is polarised at angle $\theta$ to the X axis. As the polarisation is restricted to the XY plane, any two perpendicular directions in the XY plane can act as a basis for the space. For now, let's consider the rectilinear basis, ie, horizontal and vertical directions as the basis set. Therefore, a photon can be represented as 
\begin{bmatrix}
    a \\
    b
\end{bmatrix}
where a and b are the coefficients of $\ket{0}$ and   respectively.
\newline
Now, lets try and find an operator to determine the polarisation given a particular state. To do this, we are going to assign values to the possible outcomes upon measuring with a particular polariser. If light is transmitted through the polariser we will give it value +1 and otherwise it will be assigned a vaule -1. 
Therefore, we can see that $P_x$ =
\begin{bmatrix}
1 & 0 \\
0 & -1 
\end{bmatrix}
is the operator to get the output for polarisation along the x-axis (horizontal). We can see that the eigenstates for this operator are 
\begin{bmatrix}
    1 \\
    0
\end{bmatrix}
 and
\begin{bmatrix}
    0 \\
    1
\end{bmatrix} with eigenvalues +1 and -1 respectively . Physically, this makes sense because the former eigenstate represents a photon polarised along the x - axis which will definitely get transmitted through the polariser and the latter eigenstate represents a photon polarised vertically which will not pass through the polariser. 

\newline
\newline

As we have seen earlier, any state $\ket{\theta}$ can be written as a superposition of any two perpendicular states, say  $\ket{0}$ and $\ket{90}$. Therefore, we get
\begin{equation}
    \ket{\theta} = \cos(\theta )*\ket{0} + \sin(\theta )*\ket{90}
\end{equation}
However, quantum mechanics tells us that when we measure the polarisation with a horizontal polariser, the photon collapses to one of the eigenstates of the horizontal polarisation operator, ie, it collapses to either horizontal or vertical polarisation. We can get the probabilities of collapse to each eigenstate by taking the square of the projection of the vector onto the corresponding eigenstate vector(as all vectors are unit vectors). Therefore, the probability of the photon collapsing to horizontal polarisation and subsequently getting transmitted through the polariser is $\cos^2 (\theta )$ and the probability of vertical polarisation is $\sin^2 (\theta )$.

It is important to realise that in this section, we have always considered $\ket{0}$ and $\ket{90}$ to form the basis that spans the space. However, any two independent vectors will form a basis and therefore any two vectors $\ket{\theta}$ and $\ket{90 + \theta}$ can form a basis for the space. Two of these basis are important for us, the rectilinear basis for by  $\ket{0}$ and $\ket{90}$ and the  diagonal basis formed by $\ket{45}$ and $\ket{135}$

The discussion in the previous few paragraphs leads to a very important question in the context of quantum cryptography protocols. Given a photon that is polarised at an angle theta to the x-axis which has collapsed to horizontal polarisation on measuring with a horizontal polariser, is it possible to figure out the angle theta?The answer to this question is no.What if we had a large number of photons in the same state?  In this case , theoretically atleast we would empirically get the probabilities of each collapse and hence find theta.However, the no cloning theorem in quantum mechanics states that we cannot make identical copies of arbitrary quantum states so this isn’t a feasible way to determine theta.What this means is,\textbf{post wavefunction collapse it is impossible to determine the polarisation prior to the measurement.}

The ideas in this article are key for the problems that we will be looking at in this series.
\end{document}
