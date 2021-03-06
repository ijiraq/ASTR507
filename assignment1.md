# Determine if particular KBOs are in mean-motion resonance

**Read the article [Resonance Dynamics in the Kuiper Belt](RePrintVersion.pdf).** 

*Minor planets that are only recently discover and have short observational arcs are identified by a set of letters and numbers. For now we won’t go into what those designations mean, but the objects have names like K00A00A.*
 
(15 POINTS) 1 - Using the python version of [Rebound](https://rebound.readthedocs.io/en/latest/index.html) compute the evolution of the 2:1 resonance argument 
for minor planets K13GD8G, K15RR7Y and K15VG6A.   (See the *Hints* before you start.)

Although these minor planets all have semi-major axis values consistent with a 2:1 orbital commenserability with Neptune (the minor planet goes around the Sun once each time Neptune makes two solar orbits) not all are in mean-motion resonance with that planet.  

Determine which of those minor planets **are** and which **are not** in the **2:1** mean-motion resonance. 

 - *Hints*:  

   - Use the rebound integrator to compute the orbital evolution of the particles mentioned above. 
   - To install rebound follow the instructions in the [Quick Start guide to setup rebound](https://rebound.readthedocs.io/en/latest/python_quickstart.html)
   - Once you have Rebound installed follow the [C-G Comet](https://rebound.readthedocs.io/en/latest/ipython/Churyumov-Gerasimenko.html) to become comfortable with rebound and learn some useful python ploting.
   - For the TNO integration please be sure to sim.add('Uranus') and sim.add('Neptune').   Adding objects in order of distance from the Sun helps rebound keep the centre of mass straight.
   - *If Python and Notebooks are new to you and you want some guidence, please contact me.*
   - In rebound use the ‘WHFast’ integrator (others work to but WHFast is precise enough for this problem and quick)
   - Integrate for 1E5 years and plot the time evolution of the resonant arguments.
   - Use a time-step of 0.1 years with 1000 time outputs  (see the quick start example to see how to record values)
   - `dt = 0.1*2*np.pi` for example. 
   - Use a time-step of 0.1 years with 1000 time outputs  (see the quick start example to see how to record value
   - Use the `sim.compute_orbits()` function to compute the keplerian elements at each step.
   - The objects returned by compute_orbits calls are of type `orbit` and have elements `a,e,inc,Omega,omega,M` and also `lamda` (represented as *l*) as object as attributes.
   - One might use the python code snippet below to compute the resonant argument (shown here for the 3:2 resonance) at each timestep (calling `compute_orbit` [or `compute_orbits`] at the end of each time step) and then store the evolution of the keplerian elements. 
     ```
        orbit = sim.compute_orbit(4)
        omega_bar = (orbit.Omega + orbit.omega)
        theta_32  = 3*orbit.l - 2*orbit.l  - omega_bar
     ```
     - orbit.l is the *mean longitude* of the object in its orbit.  This is the sum of *Omega* (the location where the orbit plane crosses the reference plane) *omega* (the distance from this nodal point to the pericentre location) and *M* (the mean-anomally, or how far from pericentre the object would be if the object moved uniformly around the orbit, ie the mean or average rate of motion).  *mean longitude* is represented by *lambda* in the paper given at the start of this question.
     
     
2 - Determine which Neptune mean-motion resonance K14UM9M is located in, if any.

- *Hints*: 
   - Use the semi-major axis of the TNO and Neptune and eq. 1 from the reading to determine the integer prediod ratio of Neptune:K14UM9M (example values might be 3:2, 2:1, 5:4, etc) of the possible mean-motion resonance.
   - Use rebound to compute the evolution of the resonant arguement relvant to the ratio above and determine if that argument osscilates our is confined.
   


Email me (jjk@uvic.ca) if you have other questions. 
