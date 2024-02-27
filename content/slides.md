# Creepage and Clearance

## Related topics: Dialectrics, Electric Fields, Corona, and Arcs

[Print This Slide Deck](?print-pdf)

---

# $ 3 \cdot 10^{6} $

Note: What is this number?

---

## Creepage Definition
>"Creepage distance along the surface of an insulating material is the shortest distance between uninsulated energized parts or between an uninsulated energized part and ground."  
> MIL-DTL-917

![](content/creepage_and_clearance.png)

Note: Not to be confused with Creep - a propensity for materials to slowly deform underload over time.

---

## Clearance Definition
>"Clearance distance is the shortest point-to-point distance in air between uninsulated energized parts or between an uninsulated energized part and ground."  
> MIL-DTL-917  

![](content/creepage_and_clearance.png)

---

## Invocation

Depending on equipment's specification effectivity date, Creepage and Clearance requirements are invoked through MIL-DTL-917 or MIL-E-917.

Note: This means MIL-E-917 in many cases.

---

## What are the requirements?

------

## MIL-E-917
![alt text](content/mil-e-917-table-1.png)

Note: 
- A, B, and C are ratings of 0-50VA, 50-2000VA, and greater than 2000VA respectively.
- Open vs Enclosed is per MIL-STD-108.

------

## MIL-DTL-917

The requirements are the same as E-917 up to 1000 volts.

![alt text](content/mil-dtl-917-table-3.png)

Between 1-15KV, the spec invokes IACS (UR) E11. 

Note: 
- A, B, and C are ratings of 0-50VA, 50-2000VA, and greater than 2000VA respectively.
- Open vs Enclosed is per MIL-STD-108.

------

## MIL-E-917 and MIL-DTL-917

>"Use of electrical parts or assemblies such as potentiometers, connectors, printed wiring assemblies, and similar devices having lesser creepage and clearance distances is permissible provided these parts and assemblies conform with applicable military specifications, and their energized portions are enclosed to protect against entry of dust and moisture."

------

## IACS (UR) E11
Clearance requirements:
![alt text](content/e11.png)  

For creepage, IEC 60092-503:2007 is invoked.

---

## Application Example: Motor Terminal Box

------

## Application Example: Motor Terminal Box

The component in question is a 5KV 3-phase open-wye motor temrinal box in concept design.  The proposed design for internal buswork has them spaced 3 inches apart from each other, and at least three inches apart from the enclosure.  Does this meet requirements? Is this ok?

Note: Those are not the same question!
------

## Application Example: Motor Terminal Box

Step one is determine the peak voltages between all the components...  
...what is the terminal voltage?  
...Is that an RMS value?   
...Is that a Phase-to-Return Voltage?    
...Is that a Phase-to-Phase Voltage?  
...What is the drive topology?    
## Ask!


------

## Application Example: Motor Terminal Box

You ask, and the supplier provides some additional documentation.  
- The terminal voltage is 5KV, as measured Phase-to-Return.  
- The motor is powered by a one cascaded H-Bridge VFD per phase, which features a mid-point high resistance ground.  
- The system has a requirement to continue operation with a ground present in the system.

------

## Application Example: Motor Terminal Box

![Alt text](content/motor_terminal_schematic.png)

------

Phase-to-Return Peak: $ 5000V $
Phase-to-Ground Peak: $ 2500V $
Phase-to-Phase Peak: $ 2500V \cdot \sqrt{3} = 4330V $

------


$ 5000V \cdot \sqrt{2} = 7071V $
$ $


------

## Slide 4

And some math (no local katex):
$$ J(\theta_0,\theta_1) = \sum_{i=0} $$  

$$ \frac{1}{2} = 0.5 $$

---

## Slide 5 - Lets do a wall of text

>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Risus feugiat in ante metus dictum at. Sit amet nisl purus in mollis nunc sed id semper. Lacus sed turpis tincidunt id aliquet risus feugiat in. Est lorem ipsum dolor sit amet consectetur adipiscing elit pellentesque. Mauris vitae ultricies leo integer malesuada nunc vel. Elit duis tristique sollicitudin nibh sit amet commodo. Duis at consectetur lorem donec massa sapien. Facilisis gravida neque convallis a cras semper auctor. Lobortis mattis aliquam faucibus purus. Nam at lectus urna duis convallis convallis tellus id. Nisl tincidunt eget nullam non nisi est sit amet. At imperdiet dui accumsan sit amet nulla. Amet nisl purus in mollis nunc sed id. Donec ultrices tincidunt arcu non sodales neque sodales ut.
