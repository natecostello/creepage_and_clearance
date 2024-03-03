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

## Why are the requirements?

The purpose of clearance requirements is to prevent electrical arcs and corona discharge.  

The purpose of creepage requirements is preventing surface tracking, which is really about preventing electrical arcs and corona discharge.

---

## How are the requirements?

Dry air at STP breaks down at $$\vec{E}=3\cdot 10^{6} \tfrac{V}{m}$$

Recall $$ V_{a-b} = \int_{a}^{b}\vec{E} \cdot d\vec{l} $$

To get an average electric field strength between two conductors we divide the voltage between two conductors, by the length.

### Clearance

MIL-E-917, MIL-DTL-917, and IACS (UR) E11 clearance requirements correspond to average electric fields of $$\vec{E}=[0.066 \text{ to }0.31] \cdot 10^{6} \tfrac{V}{m} $$ 

These values requirements contain factors of 10 to 50 margin with respect to the breakdown of air.  This margin will accomodate things like motion, geometric Electric field concentration, and humidity/particulate.

### Creepage

Creepage is a little more arcane.  The presence of conductive or semiconductive particulate on a surface is going to concentrate the electric field above the surface, between the particulate.  The presence of water droplets or other dielectrics will also concentrate the electric field above the surface, between the droplets.  Additionally, commercial specs will factor in tracking resistance of the materials employed.  Its no surprise then that creepage requirements generally involve more separateion, especially in non-enclosed equipment.



---

## Application Example: Motor Terminal Box

------

## Application Example: Motor Terminal Box

The component in question is a 5KV 3-phase open-wye motor terminal box in concept design.  The proposed design for internal buswork has them spaced 3 inches apart from each other, and at least three inches apart from the enclosure.  

![Alt text](content/example-motor-arrangement.png)

Details:
- 5KV is a peak voltage measured phase-to-return
- The motor is powered by a 3-phase cascaded H-bridge drive which features a mid-point high resistance ground (HRG) on each phase.
- The system has a requirement to continue operation with a ground on a single phase.
- The performance spec invokes MIL-E-917

**Does this meet requirements? Is this ok?**

------

## Application Example: Motor Terminal Box

![Alt text](content/example-motor-schematic.png)

---

## Application Example: Drive IGBT
