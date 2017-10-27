Introduction to Pecube
======================  

General overview
----------------
[Pecube]_ is a numerical modelling program used to simulate heat transfer in the lithosphere and to predict thermochronometer ages.
Pecube uses the finite element method to calculate time-dependent temperatures in 3D including the effects of heat conduction, advection, and production.
What is somewhat unique with Pecube is that the surface topography can evolve freely with time and there is a fairly flexible kinematic model built in, which allows users to define fault geometries and slip rates within their model domain.
Pecube can be used for standard forward modelling of a given region or set of ages, or to invert thermochronometer data using the Neighbourhood Algorithm [NA]_.

The general time-dependent heat transfer equation solved in Pecube is shown below

.. math::

    \rho c \left( \frac{\partial T}{\partial t} + V \cdot \nabla T \right) = \nabla \cdot k \nabla T + \rho H

where :math:`\rho` is density, :math:`c` is heat capacity, :math:`T` is temperature, :math:`t` is time, :math:`V` is the advection velocity, :math:`k` is thermal conductivity, and :math:`H` is the heat production.
The various terms can be broken out based on their role in heat transfer as follows.

.. math::

    \rho c \underbrace{(\frac{\partial T}{\partial t}}_\text{Time dependence} + \underbrace{V \cdot \nabla T}_\text{Advection} ) = \underbrace{\nabla \cdot k \nabla T}_\text{Conduction} + \underbrace{\rho H}_\text{Production}

We won't go into any detail for our course, but here we can at least see the equation and its components.



Outline
-------

- General overview of Pecube and how it differs from the other models we've used
  
  - 3D heat transfer model (conduction, advection, material properties, topography, kinematics, etc.)
  - Age prediction algorithms (comparison to Dodson)
  - Differences from DiffArg (Crystal scale model of Ar diffusion with a specified thermal history)
  - Differences from HeFTy (Modeling ages data again, focussed only on the effect of the cooling history - no connection to physical process)
  - Aims of software
  - Advantages and disadvantages

- Using Pecube

  - Overview of the input file (quick, simple pre-configured example)
  - Running Pecube (test, run)
  - Post processing output
  - Visualizing output in ParaView

- Comparison with data

  - Thermal field (general structure, heat flow)
  - Age comparison (goodness-of-fit, 

- Designing your own models

  - Preparing a model, what do we need? (Ages, topography, material properties)
  - General design principles (spatial extent, model thickness, boundary conditions, etc.)
  - Optimization

- Pecube models of various scenarios

  - Changes in relief
  - Active faults

- Advanced topics

  - Data inversion using Pecube


.. [Pecube]
    Braun, J., 2003. Pecube: A new finite-element code to solve the 3D heat transport equation including the effects of a time-varying, finite amplitude surface topography. *Computers & Geosciences*, 29(6), pp.787-794, `https://doi.org/10.1016/S0098-3004(03)00052-9 <https://doi.org/10.1016/S0098-3004(03)00052-9>`__.

    Braun, J., Van Der Beek, P., Valla, P., Robert, X., Herman, F., Glotzbach, C., Pedersen, V., Perry, C., Simon-Labric, T. and Prigent, C., 2012. Quantifying rates of landscape evolution and tectonic processes by thermochronology and numerical modeling of crustal heat transport using PECUBE. *Tectonophysics*, 524, pp.1-28, `https://doi.org/10.1016/j.tecto.2011.12.035 <https://doi.org/10.1016/j.tecto.2011.12.035>`__.

.. [NA]
    Sambridge, M., 1999. Geophysical inversion with a neighbourhood algorithm—I. Searching a parameter space. *Geophysical Journal International*, 138(2), pp.479-794, `https://dx.doi.org/10.1046/j.1365-246X.1999.00876.x <https://dx.doi.org/10.1046/j.1365-246X.1999.00876.x>`__.

    Sambridge, M., 1999. Geophysical inversion with a neighbourhood algorithm—II. Appraising the ensemble. *Geophysical Journal International*, 138(3), pp.727-746, `https://dx.doi.org/10.1046/j.1365-246x.1999.00900.x <https://dx.doi.org/10.1046/j.1365-246x.1999.00900.x>`__.