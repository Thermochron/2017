Pecube exercise
===============
As mentioned in the tutorial materials, Pecube is an powerful numberical tool for quantifying rates of tectonic and erosional processes recorded in thermochronometer data.
The questions below are designed to give you some sense of how some of the different parameters in Pecube affect thermochronometer ages, and which of these parameters may be most important to consider in measured thermochronometer ages.

Problem 1
---------
Input files
~~~~~~~~~~~
- `fault_parameters_block_uplift.txt <../../_static/docs/Day-5/fault_parameters_block_uplift.txt>`__
- `topo_parameters_block_uplift.txt <../../_static/docs/Day-5/topo_parameters_block_uplift.txt>`__

Questions
~~~~~~~~~
We'll start with exploring the effects of uplift rate and the duration of uplift on crustal temperatures and resulting thermochronometer ages.
For this problem, you should make the following changes to the input files above:

1. Run a series of models where you vary the uplift velocity between 0.1 mm/a and 5 mm/a.
    How does the uplift velocity affect thermochronometers with a low closure temperature like apatite (U-Th)/He?
    Do ages continue to get younger as the uplift velocity is increased?
    What about higher temperature systems like zircon fission-track or :sup:`40`\ Ar/:sup:`39`\Ar in muscovite?
    Is the behavior similar to low closure temperature systems?
    Are there cases where the ages don't make sense?
    Record your results of your experiments in a spreadsheet.

2. Set the uplift velocity back to 1 mm/a and now let's consider the effect of the duration of uplift from 5-50 Ma.
    Similar to above, explore this effect in a series of experiments where you only change the length of time the model runs, from 5 to 50 Ma.
    Again, do you see any differences in which thermochronometer systems record the effects of the duration of uplift?
    Record your results for at least one low-temperature and one intermediate temperature thermochronometer system for each duration of uplift in a spreadsheet.
    
3. Reset the duration of the experiments to 20 Ma and now consider the effect of the timing of uplift from 1-20 Ma.
    As before, we only want to change when the uplift occurs in this part of the problem, by modifying the timing of uplift in the ``fault_parameters.txt`` file.
    Record the results of your experiments for the same thermochronometers above in your spreadsheet.

4. Feel free to explore the effects of some of the other parameters such as the model thickness, thermal diffusivity, heat production, and temperature at the base of the model on low- and intermediate-temperature thermochronometers.

Based on your experiments above, how do the different parameters affect the thermal field in the crust and the cooling ages?
Which thermochronometers might be most sensitive to recent changes in the rate or timing of uplift in nature?
Are there any limits that you might consider for various thermochronometer systems?

Problem 2
---------
Input files
~~~~~~~~~~~

- `fault_parameters_Bhutan_vertical.txt <../../_static/docs/Day-5/fault_parameters_Bhutan_vertical.txt>`__
- `topo_parameters_Bhutan_vertical.txt <../../_static/docs/Day-5/topo_parameters_Bhutan_vertical.txt>`__

Questions
~~~~~~~~~
Our goal in this problem is to explore how changes in topography affect cooling ages predicted using Pecube.
As we have seen, low-temperature thermochronometers can be sensitive to the geometry of the Earth's surface because of the bending of the isotherms in the crust beneath the topography.
In this problem we will continue to use vertical block uplift, but now include a topography file from the Himalaya of Bhutan.
For this problem, you should make the following changes to the input files above:

0. Before you start this problem you will need to create a directory where the Pecube output will be stored.
   If you are in a Terminal window in the Pecube base directory you can simply type

   .. code:: bash

    mkdir RUN02

1. Start by exploring the effects of changes in topographic relief with time by making changes to section (9) of the ``topo_parameters.txt`` file.
    Topographic relief can be scaled by the amplification factor with a value of 0 corresponding to no relief (i.e., flat topography), and a value of 1 corresponding to modern relief from a digital elevation model.
    How do different values of the relief amplification factor between 0 and 1 affect the range of thermochronometer ages at the surface?
    Is the effect similar for low- and intermediate-temperature thermochronometers?
    How do changes to the amplification factor affect the fit to the observed ages given at the end of the Pecube simulation?
    As for the previous problem, record the results of your experiments in a spreadsheet.

2. Reset the topographic amplification factor to 1.0 and let's now explore how the timing of changes to the amplification factor affects the ages.
    You can explore changing the amplification factor by adding an additional time step in the tectonomorphic scenario (input 7 in the ``topo_parameters.txt`` file) and an additional line for its timing in section (9) of the ``topo_parameters.txt`` file.
    Consider times for changes in relief between 1-10 Ma, which are the time over which the relief change will occur.
    How does a recent change in relief compare to more gradual changes in relief?
    Do you see differences between the change recorded in low- versus intermediate-temperature thermochronometers?
    What about growth of relief versus a decrease in relief?
    How does this change the pattern of cooling ages and fit to the observed ages?
    Record what you changed and the results in your spreadsheet.

3. Now let's consider the effect of how the relief is generated by using both the amplification factor and the topographic offset factor.
    In the scenarios above we have held the minimum elevation at 0.0 and changed relief by increasing elevations across the model.
    An alternative is that the relief has formed by keeping the peak elevations high and having rivers carve into the landscape.
    This scenario could be considered by setting the topographic offset factor to be similar to the height of the mountain peaks (~7 km) with no relief, then increasing the relief factor to 1 at the same time the topographic offset factor is decreased to 0.
    This would simulate a 7-km high plateau landscape initially that morphs into the modern topography during the time the relief is changed.
    For a scenario like that above, how does it change the ages you see at the surface?
    Are there other scenarios you could consider?
    How would you design them?
    Feel free to play around and record your results in your spreadsheet.

Problem 3
---------
Input files
~~~~~~~~~~~

- `fault_parameters_Bhutan_fault.txt <../../_static/docs/Day-5/fault_parameters_Bhutan_fault.txt>`__
- `topo_parameters_Bhutan_fault.txt <../../_static/docs/Day-5/topo_parameters_Bhutan_fault.txt>`__

Questions
~~~~~~~~~
In this problem we're going to use a set of input files based on experiments described in a recent paper on the tectonics and rates of rock exhumation in the Himalaya of [Bhutan]_.
The key difference from above is that we're now going to use the Pecube fault model to explore how some of the parameters related to the fault geometry affect the predicted ages.

0. Before you start this problem you will again need to create a directory where the Pecube output will be stored.
   If you are in a Terminal window in the Pecube base directory you can simply type

   .. code:: bash

    mkdir RUN03

1. Here the problem is a bit more open ended.
    Feel free to explore the effects of changes to the geometry of the faults, the slip rate, the partitioning factor between overthrusting and underthrusting, and some of the thermal model parameters on the misfit to the observed age data.
    The fault geometry at the start should provide a good fit to the observed ages, but some of the other factors can be adjusted to improve the misfit.
    Which parameters have the largest effects, and what changes improve the misfit to the observed age data?
    Which set of parameters provides the best fit to the age data?
    Is it easy to predict how a given change in the model will affect the age misfit?
    Does it seem like making incremental changes is an efficient way to determine which parameters provide a good fit to a set of observed ages?
    Record the results of your experiments in your spreadsheet as for the previous problems.

.. [Bhutan] Coutand, I., Whipp, D.M., Grujic, D., Bernet, M., Fellin, M.G., Bookhagen, B., Landry, K.R., Ghalley, S.K. and Duncan, C., 2014. Geometry and kinematics of the Main Himalayan Thrust and Neogene crustal exhumation in the Bhutanese Himalaya derived from inversion of multithermochronologic data. *Journal of Geophysical Research: Solid Earth*, 119(2), pp.1446-1481, `https://dx.doi.org/10.1002/2013JB010891 <https://dx.doi.org/10.1002/2013JB010891>`__.