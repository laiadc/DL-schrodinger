# Deep learning methods for excited wave functions of molecular potentials

A deep learning approach to generate the fundamental and excited eigenfunctions of multiple Hamiltonians.

This repostory contains the code used to reproduce the eigenstates of molecular potentials. The results are illustrated in a set of [Jupyter](https://jupyter.org/) notebooks. The whole code is the result of the work in --link to paper--. Any contribution or idea to continue the lines of the proposed work will be very welcome.

**Remark**: We recommend the readers to view the notebooks in [Google Colaboratory](https://colab.research.google.com/) for nicer presentation and correct visualization of the figures. To open the notebooks in Google Colaboratory one can click on the links below, or use the button [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]() found in the first line of every notebook.

In this work, the neural networks are trained with Hamiltonians belonging to the same family of functions. Then, we expect the neural networks to be able to generalize and reproduce the wavefunctions of more general Hamiltonians. Two different settings are considered:

+ **Training with random polynomial potentials**: In this case, the training data consists of a set of random Hamiltonians with polynomial potentials of (up to) degree four. That is,

<img src="https://render.githubusercontent.com/render/math?math=H(x) = \frac{p^2}{2m} + V(x), \quad V(x) = \alpha_0 + \alpha_1 x + \alpha_2 x^2 + \alpha_3 x^3 + \alpha_4 x^4">


and in two dimensions,

<img src="https://render.githubusercontent.com/render/math?math=H(x,y) = \frac{p_x^2 + p_y^2}{2m} + V(x,y), \quad V(x,y) = \sum_{i+j\leq4} \alpha_{ij} x^i y^j"> 

<p align="center"><img src="https://github.com/laiadc/DL-schrodinger/blob/main/Images/example_poit1D.png"  align=middle width=400pt />
</p>
<p align="center">
<em>Three examples of random polynomial potentials (left) and their associated eigen functions for the fundamental state (middle) and the 10th excited state (right). </em>
</p>

Once the network is trained, we ask the network to reproduce the wave functions of more general, non-polynomial potentials. In this work, we chose to test the network using Morse potentials, which model the potential energy of a diatomic molecule. The Morse potential can be written as

<img src="https://render.githubusercontent.com/render/math?math=V(x) = D_e(e^{-2a(x-x_e)} - 2e^{-a(x-x_e)})">

where x is the distance between the atoms, xe is the equilibrium bond distance, De is the well depth (defined relative to the dissociated atoms), and a controls the 'width' of the potential (the smaller a is, the larger the well). 

<p align="center"><img src="https://github.com/laiadc/DL-schrodinger/blob/main/Images/morse_example.png"  align=middle width=400pt />
</p>
<p align="center">
<em>Three examples of random polynomial potentials (left) and their associated eigen functions for the fundamental state (middle) and the 10th excited state (right). Example of a Morse potential with and its eigen functions for the energy levels n=0,1,2,3. </em>
</p>
