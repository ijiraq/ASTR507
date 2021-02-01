# Confirm that the relation between J<sub>2</sub>,J<sub>4</sub> and the precession of  &omega;&#771; and  &Omega;, and estimate the Laplace plane around Saturn. #

**See REBOUNDx for adding extra forces to REBOUND, in particular: [Graviational Harmonics](https://github.com/dtamayo/reboundx/blob/master/ipython_examples/J2.ipynb)**

***Submit your answer as a runable python notebook, using Markdown cells to explain and describe your work/answer.***

***Due Monday February 8 at 4PM***
 
(5 POINTS) 1 - Using the python version of [REBOUND](https://rebound.readthedocs.io/en/latest/index.html) and the 
[REBOUNDx](https://github.com/dtamayo/reboundx/) extra forces package, follow the evolution of test particles around Saturn and confirm the analytic 
expressions in Sections 2.6.2 of the text.  Place those test particles at the orbits of Mimas and Encaladus.  Report the precession rates as estimated by your simulation and as estimated by the analytic formula in degrees/day and in dimensionless units &Omega;/n.

(10 POINTS) 2 - Considering a series of circular orbits spaced between the exterior of Saturn and orbit of Tritan plot the inclination of Saturn's [Laplace plane ](https://en.wikipedia.org/wiki/Laplace_plane) versus orbital distance from Saturn in units of Saturn radii.  Compare the precession rates for these orbits with those determined in part 1.  At what distance from Saturn is the analytic determination of the precession rate acurate to 5%?  

*Hints* 
1 For part 1 only consider Saturn's mass and gravitational harmonics, i.e. don't include satelliates, rings or the Sun.
2 The test particles used in part 2 should have some eccentricty (1% or so) and inclination (1 degree or so) in their orbits such that &Omega; and &omega; are not poorly defined.
3 As in part 1, you can exclude the Sun and the other satellites and rings of Saturn.
4 Use the analytic expressions to estimate the precession periods to determine the time span / duration of integraton you need.
5 You can use the mean inclination of precessing particles to determine the inclination of the Laplace plane relative to the Saturn's equatorial plane.
