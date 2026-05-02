---
layout: project
title: Nutcracker Design Project
description: Design project
technologies: [N/A]
---

For a class, we were tasked with designing a nutcracker using the skills we've learned about FBD analysis. With this we were to understand the purpose of mechanical advantages and how they are used in every day situations. 

Find (objective): 
* Design a nutcracker

Given Information: 
* The average load needed to crack a Macadamia Nut = 220 N 
* The average max grip strength of a male = 50kg --> 500N 
* The average radius of a nut = 20mm 

Plan and solution: 
![Plan and Solution to design a nutcracker]({{ "/assets/images/Plan-Solution.png" | relative_url }}){: .center-image style="display: block; width: 350px"}

![Photo of nutcracker]({{ "/assets/images/hw-4.png" | relative_url }}){: .inline-image-r style="width: 200px"}

However, this design is not very viable because theoretically if the distance between the nut and the lever is 60mm, the distance between the lever and the force would be 240mm, which makes for a really big nut cracker and require full force. 

We then were asked to design a nutcracker with a linear actuator in mind, so using the same dimensions and forces, I chose a linear actuator that would best fit the specification and miimize the size of the actuator. 

Eventually I ended up choosing the IP65 mini linear actuator, which has a max force of 1001N, which means that if the horizontal distance between the lever and the nut is 60 mm, using the linear actuator would result in the horizontal distance between the lever and the nut to be only 133 mm, which is HALF of the distance found in the previous scenario. 

However, when I started to consider the nutcracker as a non-rigid beam, we had to change the way we approached the problem. In this scenario, the FBD of ONE handle looked like this: 

![free body diagram]({{ "/assets/images/fbd.png" | relative_url }}){: .center-image  style="width: 250px"}

The first thing I figured out was where the location of maximum deflection is. Assuming that the deflection at A and B are both 0, we can find the max deflection will occur at C because it is the superposition of the rigid rotation about B and local bending it experiences at C. 

When considering the type of material to use, I first found the deflection limit to be (0.02*133mm)= 2.66mm. Using this information, I found v(x) and M(x) in sections to find the shear force and moments at different points along the beam. Knowing point C is the location of max deflection, we can the moment equation EIy''=M to find EIy''= −203.17x^3+ 370⟨x − 60⟩^3 + C1x + C2, where using the boundary conditions that y at A(x=0) and B (x=60mm) are 0, we find C2=0 and C1= 7.31 Nm  

Plugging x = 133 mm in, we find EI·y(133) = −236,870,914 N·mm³. Setting this equal to the deflection limit of 2.66 mm gives the minimum required flexural rigidity: EI ≥ 89,050,000 N·mm^2. After consulting the chart, I ended up choosing Al 7075-T6 because of the size constraints and it has the highest E, meaning geometrically, it can be the smallest. 

When choosing the size I decided to go with a hollow cylinder because it is spatially efficient. This leaves me with a Imin of 1.24200 × 10^-9, in which I assume it has a rectangular cross section such that b=h/2, which results in the dimensions h = 13.1 mm and b= 6.6mm. 

This leaves us with the final design of: 
![final design]({{ "/assets/images/final.jpg" | relative_url }}){: .center-image style="display: block; width: 400px"}

