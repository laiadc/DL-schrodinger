# Deep learning methods for excited wave functions of molecular potentials

A deep learning approach to generate the fundamental and excited eigenfunctions of multiple Hamiltonians.

This repostory contains the code used to reproduce the eigenstates of molecular potentials. The results are illustrated in a set of [Jupyter](https://jupyter.org/) notebooks. The whole code is the result of the work in --link to paper--. Any contribution or idea to continue the lines of the proposed work will be very welcome.

**Remark**: We recommend the readers to view the notebooks in [Google Colaboratory](https://colab.research.google.com/) for nicer presentation and correct visualization of the figures. To open the notebooks in Google Colaboratory one can click on the links below, or use the button [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]() found in the first line of every notebook.

In this work, the neural networks are trained with Hamiltonians belonging to the same family of functions. Then, we expect the neural networks to be able to generalize and reproduce the wavefunctions of more general Hamiltonians. Two different settings are considered:

+ **Training with random polynomial potentials**: In this case, the training data consists of a set of random Hamiltonians with polynomial potentials of (up to) degree four. That is,

\begin{equation}
H(x) = \frac{p^2}{2m} + V(x), \quad V(x) = \alpha_0 + \alpha_1 x + \alpha_2 x^2 + \alpha_3 x^3 + \alpha_4 x^4
\label{eq:1}
\end{equation}

and in two dimensions,

\begin{equation}
H(x,y) = \frac{p_x^2 + p_y^2}{2m} + V(x,y), \quad V(x,y) = \sum_{i+j\leq4} \alpha_{ij} x^i y^j 
\label{eq:2}
\end{equation}

Once the network is trained, we ask the network to reproduce the wave functions of more general, non-polynomial potentials. In this work, we chose to test the network using Morse potentials, which model the potential energy of a diatomic molecule. The Morse potential can be written as

\begin{equation}
V(x) = D_e(e^{-2a(x-x_e)} - 2e^{-a(x-x_e)})
\label{eq:4}
\end{equation}   

where $x$ is the distance between the atoms, $x_{e}$ is the equilibrium bond distance, $D_{e}$ is the well depth (defined relative to the dissociated atoms), and $a$ controls the 'width' of the potential (the smaller $a$ is, the larger the well). 
