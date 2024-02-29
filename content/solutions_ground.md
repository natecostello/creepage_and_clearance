# Application Example: Motor Terminal Box

---

## Relevant Information

The component is a 5KV 3-phase open-wye motor terminal box in concept design.  

&nbsp;  

Details:
- Internal buswork and the grounded enclosure are separated by 3 inches
- 5KV is peak voltage measured phase-to-return
- The motor is powered by a 3-phase cascaded H-bridge drive which features a mid-point high resistance ground (HRG) on each phase.
- The system has a requirement to continue operation with a ground on a single phase.
- The performance spec invokes MIL-E-917

---

# Relevant Information

![Alt text](content/example-motor-schematic-with-ground.png)

![Alt text](content/example-motor-arrangement-with-ground.png)

---

## **Does this meets requirements?  Is it ok?**  


We need to determine the magnitude of the peak voltages between the various conductors, and evaluate whether the spacing meets the required spacing at those voltages.  We need to figure out:

`$$
\begin{align*} 
&V_{A-NA} \\ 
&V_{A-G} \\
&V_{A-B} \\
&V_{AN-G} \\
&V_{AN-BN} \\
&V_{A-BN} 
\end{align*} $$`


With the ground, we have a few more that we can no longer base on symmetry:  

`$$
\begin{align*}
&V_{B-G} \\
&V_{B-AN} \\
&V_{B-BN} \\
&V_{BN-G}
\end{align*} $$`

---

## KVLs

![Alt text](content/example-motor-KVLs-with-ground.png)

We have all the previous equations, plus a new one: 

$$ + V_{A-NA} - V_{DA} - V_{DA} = 0 \tag{1}$$  <!-- .element: style="color:blue"-->  

$$ +V_{A-G}-V_{RA}-V_{DA}=0 \tag{2}$$ <!-- .element: style="color:red"-->  

$$ +V_{A-B} +V_{DB} + V_{RB} - V_{RA} - V_{DA} = 0 \tag{3}$$ <!-- .element: style="color:green"-->  

$$ +V_{AN-G} - V_{RA} + V_{DA} = 0 \tag{4} $$ <!-- .element: style="color:darkorchid"-->  

$$ +V_{AN-BN} - V_{DB} + V_{RB} - V_{RA} + V_{DA} \tag{5} $$ <!-- .element: style="color:cyan"-->  

$$ +V_{A-BN} - V_{DB} + V_{RB} - V_{RA} - V_{DA} \tag{6} $$ <!-- .element: style="color:deeppink"-->  

$$ -V_{RB} + V_{DB} = 0 \tag{7}$$  <!-- .element: style="color:orange"-->    

---

## KVLs

...rearranging...  

`$$
\begin{align*} 
V_{A-AN} &= 2 \cdot V_{DA} \tag{1} \\ 
V_{B-BN} &= 2 \cdot V_{DB}\tag{1b}\\
V_{A-G} &= V_{RA} + V_{DA} \tag{2}\\
V_{B-G} &= V_{RB} + V_{DB} \tag{2b} \\
V_{A-B} &= V_{DA} + V_{RA} - V_{RB} - V_{DB} \tag{3} \\
V_{AN-G} &= V_{RA} - V_{DA} \tag{4} \\
V_{BN-G} &= V_{RB} - V_{DB} \tag{4b} \\
V_{AN-BN} &= V_{DB} - V_{DA} + V_{RA} - V_{RB} \tag{5} \\
V_{A-BN} &= V_{DA} + V_{DB} + V_{RA} - V_{RB} \tag{6} \\
V_{B-AN} &= V_{DB} + V_{DA} + V_{RB} - V_{RA} \tag{6b} \\
V_{RB} &= V_{DB} \tag{7}
\end{align*} $$`


---

## Simplify

![Alt Text](content/example-motor-schematic-with-ground.png)

We can see that there are no conducting closed loops that would allow current to flow through the HRG resistor $RA$, such that $V_{RA}$ is 0.  From our new KVL, we know that $V_{RB}$ = $V_{DB}$.  With this information we can simplify equations (2)-(6):  

`$$
\begin{align*} 
V_{A-G} &= V_{DA} \tag{2} \\
V_{B-G} &= 2 \cdot V_{DB} \tag{2b} \\
V_{A-B} &= V_{DA} - 2 \cdot V_{DB} \tag{3} \\
V_{AN-G} &= -V_{DA} \tag{4}\\
V_{BN-G} &= 0 \tag{4b} \\
V_{AN-BN} &= - V_{DA} \tag{5} \\
V_{A-BN} &= V_{DA} \tag{6} \\
V_{B-AN} &= V_{DA} + 2 \cdot V_{RB} \tag{6b}
\end{align*} $$`




---

## Plug and Chug

It was given that phase to return voltage, i.e., $|V_{A-AN}|$ and $|V_{B-BN}| are 5000V. We can arbitrarily establish a reference phase angle for phase A.  To keep things simple, we'll choose $\phase{0^\circ}$ for phase A quantities. Using equation (1) we solve for $V_{DA}$:
$$V_{DA} = 2500V\phase{0^\circ} \tag{1}$$ 

Using equation (1b) we solve for $V_{DB}$:
$$V_{DB} = 2500V\phase{120^\circ} \tag{1b}$$ 


Using equations (2), (2b), and (4), we solve for $V_{A-G}$, $V_{B-G}$, $V_{AN-G}$, $V_{AN-BN}$, and $V_{A-BN}$:

`$$
\begin{align*}
V_{A-G} &= 2500V\phase{0^\circ} \tag{2} \\
V_{B-G} &= 5000V\phase{120^\circ} \tag{2b} \\
V_{AN-G} &= 2500V\phase{180^\circ} \tag{4}\\
V_{AN-BN} &= 2500V\phase{180^\circ} \tag{5}\\
V_{A-BN} &= 2500V\phase{0^\circ} \tag{6}\\
\end{align*}$$`



# Equation List
`$$
\boxed{
\begin{align*} 
V_{A-AN} &= 2 \cdot V_{DA} \tag{1} \\
V_{B-BN} &= 2 \cdot V_{DB} \tag{1b} \\
V_{A-G} &= V_{DA} \tag{2} \\
V_{B-G} &= 2 \cdot V_{DB} \tag{2b} \\
V_{A-B} &= V_{DA} - 2 \cdot V_{DB} \tag{3} \\
V_{AN-G} &= -V_{DA} \tag{4}\\
V_{BN-G} &= 0 \tag{4b} \\
V_{AN-BN} &= - V_{DA} \tag{5} \\
V_{A-BN} &= V_{DA} \tag{6} \\
V_{B-AN} &= V_{DA} + 2 \cdot V_{RB} \tag{6b}
\end{align*}} $$`

Note: As in the ungrounded case, equations (2) and (4) are the easiest to solve because they don't involve a sum of quantities with different phase, and thus can be calculated as a simple sum.

---

## Sums with Differing Phase

Equations (3) and (6b) contain sums (or differences) with differing phases, so these cannot be simply added.  
&nbsp;  

Because this is a balanced 3-phase system, we can establish a reference such that phase A voltages are at a phase angle of 0.  This means phase B voltages are at a phase angle of $\tfrac{2\pi}{3}$ (or 120 degrees).  
&nbsp;  

Because this is a balanced 3-phase system, we know that both phases have the same magnitude, i.e., $|V_{DA}|=|V_{DB}|=2500V$.  We use these facts, plus some trig, geometry, three-phase rules, phasor math, or vectors (pick your poison) to find the rest of the voltages that involve sums of quantities with differing phase.

# Equation List
`$$
\boxed{
\begin{align*} 
V_{A-AN} &= 2 \cdot V_{DA} \tag{1} \\
V_{B-BN} &= 2 \cdot V_{DB} \tag{1b} \\
V_{A-G} &= V_{DA} \tag{2} \\
V_{B-G} &= 2 \cdot V_{DB} \tag{2b} \\
V_{A-B} &= V_{DA} - 2 \cdot V_{DB} \tag{3} \\
V_{AN-G} &= -V_{DA} \tag{4}\\
V_{BN-G} &= 0 \tag{4b} \\
V_{AN-BN} &= - V_{DA} \tag{5} \\
V_{A-BN} &= V_{DA} \tag{6} \\
V_{B-AN} &= V_{DA} + 2 \cdot V_{RB} \tag{6b}
\end{align*}} $$`

---

## Plug and Chug

`$$ 
\begin{align*} 
V_{A-B} &= 6614V\phase(139^{\circ}) 6615\tag{3}\\
V_{B-AN}&= 4330V\phase{270^{\circ}} \tag{6b}
\end{align*} $$`

![Alt Text](content/example-motor-phasor-sums-with-ground.png)

&nbsp;  

# Equation List
`$$
\boxed{
\begin{align*} 
V_{A-AN} &= 2 \cdot V_{DA} \tag{1} \\
V_{B-BN} &= 2 \cdot V_{DB} \tag{1b} \\
V_{A-G} &= V_{DA} \tag{2} \\
V_{B-G} &= 2 \cdot V_{DB} \tag{2b} \\
V_{A-B} &= V_{DA} - 2 \cdot V_{DB} \tag{3} \\
V_{AN-G} &= -V_{DA} \tag{4}\\
V_{BN-G} &= 0 \tag{4b} \\
V_{AN-BN} &= - V_{DA} \tag{5} \\
V_{A-BN} &= V_{DA} \tag{6} \\
V_{B-AN} &= V_{DA} + 2 \cdot V_{RB} \tag{6b}
\end{align*}} $$`

Note: 
4330 = sqrt(3)*2500  
6614 = sqrt(7)*2500

---

## Objective

**Does this meet requirements?**  
**Is it ok?**  
  
We have all voltages of concern.

`$$
\begin{align*} 
|V_{A-AN}| &= 5000V\\ 
|V_{B-BN}| &= 5000V\\
|V_{A-G}| &= 2500V\\
|V_{B-G}| &= 5000V\\
|V_{A-B}| &= 6615\\
|V_{AN-G}| &= 2500V\\
|V_{BN-G}| &= 0V\\
|V_{AN-BN}| &= 2500V\\
|V_{A-BN}| &= 2500V\\
|V_{B-AN}| &= 4330V\\
\end{align*} $$`


![alt text](/content/mil-e-917-table-1.png)

---

## Does this meet requirements?  NO

## Is it ok?

This is where we usually end up.  

### Are there other requirements we can leverage?

Looking a MIL-DTL-917, we end up at IACS (UR) E11.  For 6.6kV, the requirement is 90 mm or 3.54 inches for clearance, so nothing obvious to stand on there.

TODO: Insert discussion on creepage (need IEC spec).

### Whats our physics situation?

Our spacing is 0.0762 meters.  Our voltage is 6615V.  If were were to assume infinte plates and a uniform e-field, we'd have 

$$|E|= 8.7\cdot10^{4} \tfrac{V}{m}$$  

So we are a pretty large factor (34.5) from breakdown in STP dry air.  We'd have to look in detail at the geometry.  How well are the bus bars restrained?  Probably some FEA is called for.  Are there other applications that are bounding?  IGBT terminals?

### Can we change the design?

This equipment is in concept design, so there is likely flexibility to increase spacing or add insualting materials to increase the clearance.  If we go the insulating material route, we need to be mindful of dielectric constants and field concentration.  It is possible to insulate your way into a corona problem.

### Can we test?

Corona or PD testing could show how far from inception voltage the design is.  BIL could also provide confidence in the existing design.  Good luck with this route.


---

