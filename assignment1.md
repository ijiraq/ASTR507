# Determine if particular KBOs are in mean-motion resonance

** Read the article [Resonance Dynamics in the Kuiper Belt](RePrintVersion.pdf). ** 

* Minor planets that are only recently discover and have short observational arcs are identified by a set of letters and numbers. For now we won’t go into what those designations mean, but the objects have names like K00A00A. *
 
1 Using the python version of [Rebound](https://rebound.readthedocs.io/en/latest/index.html) compute the evolution of the 2:1 resonance argument 
for minor planets K13GD8G, K15VG6A and K15VG6A.  

Although these minor planets all have semi-major axis values consistent with a 2:1 orbital commenserability with Neptune (the minor planet goes around the Sun once each time Neptune makes two solar orbits) not all are in mean motion resonance with that planet.  

Determine which of those minor planets are and which are not in the 2:1 mean motion resonance. 

 - Hints:  

   - Use the rebound integrator to compute the orbital evolution of the particles mentioned above. 
   - To install rebound follow the instructions in the [Quick Start guide to setup rebound](https://rebound.readthedocs.io/en/latest/python_quickstart.html)
   - Once you have Rebound installed follow the [C-G Comet](https://rebound.readthedocs.io/en/latest/ipython/Churyumov-Gerasimenko.html)
   - If Python and Notebooks are new to you and you want some guidence, please contact me.
   - In rebound use the ‘WHFast’ integrator (others work to but WHFast is precise enough for this problem and quick)
   - Integrate for 1E4 years and plot the time evolution of the resonant arguments.
   - Use a time-step of 1 year with 1000 time outputs  (see the quick start example to see how to record values)
   - Use the ’sim.compute_orbits()’ function to compute the keplarian elements at each step.
   - The objects returned by compute_orbits calls have elements a/e/inc/Omega/omega/M/lambda as attributes.
     When I did this I used python code like the following snippet 
     ```
        orbit = sim.compute_orbit(4)
        omega_bar = (orbit.Omega + orbit.omega)
        theta_32  = 3*orbit.l - 2*orbit.l  - omega_bar```


2 Determine which Neptune mean motion resonance K14UM9M is located in, if any.


- Hints: 

 - email jjk@uvic.ca if you have other questions. 
