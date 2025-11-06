**Charles Liu**
Astronomy 138 - Dr. Matthew Duez
January 25th 2025

___

> Consider Saturn's moons Titan and Rhea.

___

**A)** Look up the mass, radius, semimajor axis, and period of each of the two moons.  Convert them to SI units (m, kg, s).  See the sample calculation at bottom.

*Titan*

Mass ${= 1,345.5 \times 10^{20} \text{kg} = 1.3455 \times 10^{23} \text{kg}}$

Radius ${= 2,575 \text{ km} = 2.575 \times 10^6 \text{ m}}$

Semimajor Axis ${= 1221.87 \times 10^3 \text{km} = 1.22187 \times 10^9 \text{m}}$

Orbital Period ${= 15.945421 \text{ days} = 15.945421 \times 24 \times 60 \times 60 }$
${= 1377684.3744 = 1.3776843744 \times 10^6 \text{ s}}$

*Rhea*

Mass ${= 23.1 \times 1020 \text{ kg} = 2.31 \times 10^{21} \text{ kg}}$

Radius ${= 763 \text{ km} = 7.63 \times 10^5 \text {m}}$

Semimajor Axis ${= 527.04\times10^3 \text{ km} = 5.2704 \times 10^5 \text{ km} = 5.2704 \times 10^8 \text{m}}$

Orbital Period ${= 4.5175 \text{ days} = 4.5175 \times 24 \times 60 \times 60 = 390312 = 3.90312 \times 10^5}$

___

**B)** Using (Newton's generalization of) Kepler's 3rd law, infer the mass of Saturn from the orbit of each moon.  Assume that the mass of the moons are negligible compared to the mass of Saturn.

*Newton's Generalization of Kepler's Third Law:*

${P^2 = \dfrac{4\pi^2}{G \times M}a^3}$

*Titan*

${(1.377 \times 10^6)^2 = 4\pi^2(1.22187 \times 10^9)^3/(6.67 \times 10^{-11} \times \text{M})}$

${\implies (6.67 \times 10^{-11} \times M) \times (1.377 \times 10^6)^2 = 4\pi^2(1.22187 \times 10^9)^3}$

${\implies M =5.782 \times 10^{26} \text{ kg}}$

*Rhea*

${(3.90312 \times 10^5)^2 = 4\pi^2(5.2704\times10^8)^3/(6.67 \times 10^{-11} \times \text{M})}$

${\implies (6.67 \times 10^{-11} \times M) \times (3.90312 \times 10^5)^2 = 4\pi^2(5.2704\times10^8)^3}$

${\implies M = 5.688 \times 10^{26} \text{ kg}}$

___

**C)** Look up the accepted mass of Saturn.  Compute the differences between your mass estimates and the accepted value, expressed as percentages of the accepted value.  Would you say your mass estimate is consistent with the accepted value?

The accepted mass of Saturn is ${5.685 \times 10^{26}}$

*Titan*

${\dfrac{|5.782 \times 10^{26} - 5.683 \times 10^{26}|}{5.683 \times 10^{26}} = 0.0174}$

Using Titan to calculate Saturn's mass, the error is roughly ${1.74\%}$

*Rhea*

${\dfrac{|5.688 \times 10^{26} - 5.683 \times 10^{26}|}{5.683 \times 10^{26}} = 0.0003519}$

Using Rhea to calculate Saturn's mass, the error is roughly ${0.035\%}$

*Explanation*

Since both of these percentages are extremely small (${< 2\%})$, I would say my masses are consistent with the accepted value.
___

**D)** Compute the gravitational force of Saturn on each moon.

*Titan*

${F = \dfrac{Gm_1m_2}{d^2} = \dfrac{6.67 \times 10^{-11} \times 1.3455 \times 10^{23} \times 5.683 \times 10^{26}}{(1.22187 \times 10^9)^2} = 3.416 \times 10^{21} N}$

*Rhea*

${F = \dfrac{Gm_1m_2}{d^2} = \dfrac{6.67 \times 10^{-11} \times 2.31 \times 10^{21} \times 5.683 \times 10^{26}}{(5.2704 \times 10^8)^2} = 3.152 \times 10^{20} N}$

___

**E)** Compute the gravitational forces of the moons on each other, let us say at a moment when the moons are aligned in their orbits and are as close to each other as they come.

In using Kepler's 3rd law to find the mass of Saturn, we assumed that the gravity of Saturn is the only force felt by the moons, that the gravitational pull of the moons on each other could be ignored.  Comment on whether that seems to have been a safe assumption.  It is a safe assumption if the gravitational pull each moon feels from Saturn is much greater than the gravitational pull the moons feel from each other.

*Gravitational Force of Moons on Each Other:*

${F = \dfrac{(6.67 \times 10^{-11}) \times 1.3455 \times 10^{23} \times 2.31 \times 10^{21}}{(1.22187\times10^9-5.2704\times10^8)^2} = 4.21 \times 10^{16}}$

*Explanation*

Since Saturn’s gravitational pull is magnitudes larger (${16}$ is much smaller than ${21}$ and ${20}$) than other moon’s pull (even when they are closest to the moon in question), other moon’s gravitational force is insignificant ignoring it is a relatively safe assumption.

___

**Citations**
Dave Williams. “Saturnian Satellite Fact Sheet.” NASA. Accessed January 22, 2025. [](https://lco.global/spacebook/solar-system/saturn/#:~:text=It%20is%20the%20second%20largest,kg%20or%2095.16%20Earth%20masses)[https://nssdc.gsfc.nasa.gov/planetary/factsheet/saturniansatfact.html](https://nssdc.gsfc.nasa.gov/planetary/factsheet/saturniansatfact.html).

“Saturn Fact Sheet.” NASA. Accessed January 22, 2025. 
https://nssdc.gsfc.nasa.gov/planetary/factsheet/saturnfact.html.

___