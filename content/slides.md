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
- For > 1kV enclosed equipment, creepage and clearance requirements range between 500-2500 v/in (19685-98425 v/m)

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
> "Intermediate values may be accepted for nominal voltages provided that the next higher air clearance is observed."

> "In the case of smaller distances, appropriate voltage impulse test must be applied."

Clearance requirements:
>"Creepage distances between live parts and between live parts and earthed metal parts are to be in accordance with IEC 60092-503:2007 for the nominal voltage of the system, the nature of the insulation material and the transient overvoltage developed by switch and fault conditions."

Note:
- For > 1kV equipment clearance requirements range between 461-2381 v/in (18149-93740 v/m)

------

## IEC 60092-503:2007

IEC 60092-503:2007 is not easily accessible to NAVSEA engineers.  For now, I strongly suggest that, if you own equipment with voltages above 1kV, you email [commandstandards@navy.mil](mailto:commandstandards@navy.mil) with something like the following:
>To: commandstandards@navy.mil  
>Subject: MIL-DTL-917F references to IEC 60092-503:2007 (via references to
IACS (UR) E11
>
>To whom it may concern,
>I am trying to obtain contact information for the technical owner of
MIL-DTL-917F.  For voltages above 1kV the specification points to IACS (UR)
E11 for creepage requirements.  IACS (UR) E11 in turn points to IEC
60092-503:2007 for creepage requirements.  I have been unable to locate this
specification in any technical libraries to which my organization (NAVSEA)
 has access, and would like the specification owner to provide guidance
for access.

Note: 
- Enough requests will provide a business case for them to subscribe.  
- Also, avoid invoking expensive specs in your equipment procurement specifications if at all possible.

------

## IEC 60092-503:2007

The IEC takes into account the *Proof Tracking Index* (PTI) aka the *Comparative Tracking Index* (CTI) of the material.

![alt text](content/cti-test.png)  
_Source: [UL](https://www.ul.com/services/comparative-tracking-index-cti-iec-60112)_

The conductive solution is almost instantly vaporized due to the $I^2R$, but in the process the test material will carbonize a little.  The test continues for 50 drops, and fails if more than a half amp flows for beyond 2 seconds, or the material catches on fire.  The voltage is increased if it passes.  Test voltages are 100V to 600V. Search youtube for test videos. 

### A Short Exercise
Test solution resistivity is $395\Omega\cdot\text{cm}$  
Droplet volume is $20\text{mm}^{3}$  
Electrode spacing is $4\text{mm}$  
Assume test voltage is $100\text{V}$  

What is the initial current?  
What is the initial power?

Note:
- R = 8.1 ohms
- I = 12.3 amps
- P = 1234 watts

------

## IEC 60092-503:2007

The IEC has different requirements for generators and main switchboards vs other equipment.

### For Main Switchboards and Generators:

- 443-1527 $\tfrac{v}{in}$ for 300V-PTI Material  (17440-60118 v/m)
- For 600V-PTI material the values are 20%-30% higher.  (22913-73307 v/m)
$~~$  


### For Other Equiment:
- 665-1995 $\tfrac{v}{in}$ for 300V-PTI Material  (26181-78543 v/m)
- For 600V-PTI material the values are 20%-60% higher. (42307-126921) v/m


---

## Why are the requirements?

The purpose of clearance requirements is to prevent electrical arcs and corona discharge.  

The purpose of creepage requirements is preventing or minimizing surface tracking, which is really about preventing electrical arcs and corona discharge.

---

## How are the requirements?

Dry air at STP breaks down at $$\vec{E}=3\cdot 10^{6} \tfrac{V}{m}$$

Recall $$ V_{a-b} = \int_{a}^{b}\vec{E} \cdot d\vec{l} $$

To get an average electric field strength between two conductors we divide the voltage between two conductors, by the length.

### Clearance

MIL-E-917, MIL-DTL-917, and IACS (UR) E11 clearance requirements correspond to average electric fields of $$\vec{E}=[0.066 \text{ to }0.31] \cdot 10^{6} \tfrac{V}{m} $$ 

These values requirements contain factors of 10 to 50 margin with respect to the breakdown of air.  This margin will accomodate things like motion, geometric Electric field concentration, and humidity/particulate.

### Creepage

Creepage is a little more arcane.  The presence of conductive or semiconductive particulate on a surface is going to concentrate the electric field above the surface, between the particulate.  The presence of water droplets or other dielectrics will also concentrate the electric field above the surface, between the droplets.  Additionally, commercial specs will factor in tracking resistance of the materials employed.  Its no surprise then that creepage requirements generally involve more separation, especially in non-enclosed equipment.



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
