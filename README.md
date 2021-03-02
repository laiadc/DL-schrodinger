# Deep learning methods for excited wave functions of molecular potentials

A deep learning approach to generate the fundamental and excited eigenfunctions of multiple Hamiltonians.

This repostory contains the code used to reproduce the eigenstates of molecular potentials. The results are illustrated in a set of [Jupyter](https://jupyter.org/) notebooks. The whole code is the result of the work in <a href = https://arxiv.org/abs/2103.00202> this paper</a>. Any contribution or idea to continue the lines of the proposed work will be very welcome.

**Remark**: We recommend the readers to view the notebooks in [Google Colaboratory](https://colab.research.google.com/) for nicer presentation and correct visualization of the figures. To open the notebooks in Google Colaboratory one can click on the links below, or use the button [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]() found in the first line of every notebook.

In this work, the neural networks are trained with Hamiltonians belonging to the same family of functions. Then, we expect the neural networks to be able to generalize and reproduce the wavefunctions of more general Hamiltonians. Two different settings are considered:

+ **Training with random polynomial potentials**: In this case, the training data consists of a set of random Hamiltonians with polynomial potentials of (up to) degree four. That is,

<img src="https://render.githubusercontent.com/render/math?math=H(x) = \frac{p^2}{2m} %2B V(x), \quad V(x) = \alpha_0 %2B \alpha_1 x %2B \alpha_2 x^2 %2B \alpha_3 x^3 %2B \alpha_4 x^4">


and in two dimensions,

<img src="https://render.githubusercontent.com/render/math?math=H(x,y) = \frac{p_x^2 %2B p_y^2}{2m} + V(x,y), \quad V(x,y) = \sum_{i+j\leq4} \alpha_{ij} x^i y^j"> 

<p align="center"><img src="https://github.com/laiadc/DL-schrodinger/blob/main/Images/example_pot1D.png"  align=middle width=600pt />
</p>
<p align="center">
<em>Three examples of random polynomial potentials (left) and their associated eigen functions for the fundamental state (middle) and the 10th excited state (right). </em>
</p>

Once the network is trained, we ask the network to reproduce the wave functions of more general, non-polynomial potentials. In this work, we chose to test the network using Morse potentials, which model the potential energy of a diatomic molecule. The Morse potential can be written as

<img src="https://render.githubusercontent.com/render/math?math=V(x) = D_e(e^{-2a(x-x_e)} - 2e^{-a(x-x_e)})">

where x is the distance between the atoms, xe is the equilibrium bond distance, De is the well depth (defined relative to the dissociated atoms), and a controls the 'width' of the potential (the smaller a is, the larger the well). 

<p align="center"><img src="https://github.com/laiadc/DL-schrodinger/blob/main/Images/morse_example.png"  align=middle width=600pt />
</p>
<p align="center">
<em>Three examples of random polynomial potentials (left) and their associated eigen functions for the fundamental state (middle) and the 10th excited state (right). Example of a Morse potential with and its eigen functions for the energy levels n=0,1,2,3. </em>
</p>

+ **Training with Morse potentials**: Let H be the Hamiltonian whose eigenfunctions we want to find. Suppose that H can be written as

<img src="https://render.githubusercontent.com/render/math?math=H = H_0 %2B H_1">


Where H0 is a Hamiltonian whose eigenstates are known. If H1 is small, then H0 is an approximation of H. The goal of this second part of the work is to see if a neural network trained with the Hamiltonian H0 can generalize and reproduce the wave functions of the Hamiltonian H. In this work we apply this framework to approximate the eigenstates of coupled Morse Hamiltonians: 

<img src="https://render.githubusercontent.com/render/math?math=H(x_1, x_2, p_1, p_2) = \frac{1}{2}(G_{11}p_1^2 %2B G_{22}p_2^2) %2B G_{12}p_1p_2 %2B U_M(x_1) %2B U_M(x_2)">

This Hamiltonian models the stretching dynamics of the H2O molecule. It is expressed in terms of bond-angle coordinates, where xi are the OH extensions and pi their associated momentum. The training consits of decoupled Morse potentials, which act as an approximation of the coupled Morse potential.

## Notebooks
(Currently tested on TensorFlow 2.0.0/2.1.0)

### [Random_potentials1D.ipynb](https://colab.research.google.com/github/laiadc/DL-schrodinger/blob/main/Random_potentials1D.ipynb)
Trains a neural network using random polynomial potentials in a 1-dimensional space. The network is tested using Morse potentials.

### [Random_potentials2D.ipynb](https://colab.research.google.com/github/laiadc/DL-schrodinger/blob/main/Random_potentials2D.ipynb)
Trains a neural network using random polynomial potentials in a 2-dimensional space. The network is tested using Morse potentials.

### [Coupled.ipynb](https://colab.research.google.com/github/laiadc/DL-schrodinger/blob/main/Coupled_morse.ipynb)
Trains a neural network using random decoupled Morse potentials. The network is able to reproduce multiple excited states of coupled Morse potentials. 

### [Results.ipynb](https://colab.research.google.com/github/laiadc/DL-schrodinger/blob/main/Results.ipynb)
This notebook summarizes the results of the paper and provides interactive plots created with *plotly* library.

## Contributions

Contributions are welcome!  For bug reports or requests please [submit an issue](https://github.com/laiadc/PFM_Bearing_Fault_Detection/issues).

## Contact  

Feel free to contact me to discuss any issues, questions or comments.

* GitHub: [laiadc](https://github.com/laiadc)
* Email: [laia.domingo@icmat.es](laia.domingo@icmat.es)

### BibTex reference format for citation for the Code
```
@misc{DLSchrodinger,
title={Deep learning methods for excited wave functions of molecular potentials},
url={https://github.com/laiadc/DL-schrodinger},
note={GitHub repository containing deep learning approach generating fundamental and excited eigenfunctions for molecular potentials.},
author={Laia Domingo Colomer, Florentino Borondo},
  year={2020}
}


