
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

![Alt text](content/example-motor-schematic.png)

![Alt text](content/example-motor-arrangement.png)

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

---


## KVLs

![Alt text](content/example-motor-KVLs.png)


$$ + V_{A-NA} - V_{DA} - V_{DA} = 0 \tag{1}$$  <!-- .element: style="color:blue"-->  

$$ +V_{A-G}-V_{RA}-V_{DA}=0 \tag{2}$$ <!-- .element: style="color:red"-->  

$$ +V_{A-B} +V_{DB} + V_{RB} - V_{RA} - V_{DA} = 0 \tag{3}$$ <!-- .element: style="color:green"-->  

$$ +V_{AN-G} - V_{RA} + V_{DA} = 0 \tag{4} $$ <!-- .element: style="color:darkorchid"-->  

$$ +V_{AN-BN} - V_{DB} + V_{RB} - V_{RA} + V_{DA} \tag{5} $$ <!-- .element: style="color:cyan"-->  

$$ +V_{A-BN} - V_{DB} + V_{RB} - V_{RA} - V_{DA} \tag{6} $$ <!-- .element: style="color:deeppink"-->  

&nbsp;  
...rearranging...  

`$$
\begin{align} 
V_{A-NA} &= 2 \cdot V_{DA} \\ 
V_{A-G} &= V_{RA} + V_{DA} \\
V_{A-B} &= V_{DA} + V_{RA} - V_{RB} - V_{DB} \\
V_{AN-G} &=  V_{RA} - V_{DA} \\
V_{AN-BN} &= V_{DB} - V_{DA} + V_{RA} - V_{RB} \\
V_{A-BN} &= V_{DA} + V_{DB} + V_{RA} - V_{RB}
\end{align} $$`

---

## Simplify

![Alt Text](content/example-motor-schematic.png)
  
We can see that there are no conducting closed loops that would allow current to flow through the HRG resistors $RA$ and $RB$, such that $V_{RA}$ and $V_{RB}$ are 0. With this information we can simplify  equations (2)-(6).  

`$$
\begin{align*} 
V_{A-G} &= V_{DA} \tag{2} \\
V_{A-B} &= V_{DA} - V_{DB} \tag{3} \\
V_{AN-G} &= -V_{DA} \tag{4}\\
V_{AN-BN} &= V_{DB} - V_{DA} \tag{5}\\
V_{A-BN} &= V_{DA} + V_{DB} \tag{6}
\end{align*} $$`

---

## Plug and Chug

It was given that phase to return voltage, i.e., $|V_{A-NA}|$ is 5000V. We can arbitrarily establish a reference phase angle for phase A.  To keep things simple, we'll choose $\phase{0^\circ}$ for phase A quantities. Using equation (1) we solve for $V_{DA}$:
$$V_{DA} = 2500V\phase{0^\circ} \tag{1}$$  

Using equations (2) and (4), we solve for $V_{A-G}$ and $V_{AN-G}$:

`$$
\begin{align*}
V_{A-G} &= 2500V\phase{0^\circ} \tag{2} \\
V_{AN-G} &= -2500V\phase{0^\circ} \tag{4}\\
\end{align*}$$`

&nbsp;  

## Equation List

`$$
\boxed{
\begin{align*} 
V_{A-NA} &= 2 \cdot V_{DA} \tag{1} \\
V_{A-G} &= V_{DA} \tag{2} \\
V_{A-B} &= V_{DA} - V_{DB} \tag{3} \\
V_{AN-G} &= -V_{DA} \tag{4}\\
V_{AN-BN} &= V_{DB} - V_{DA} \tag{5}\\
V_{A-BN} &= V_{DA} + V_{DB} \tag{6}
\end{align*}}$$`


Note: Equations (2) and (4) are the easiest to solve because they don't involve a sum of quantities with different phase, and thus can be calculated as a simple sum.

---

## Sums with Differing Phase

Equations (3), (5), and (6) contain sums (or differences) with differing phases, so these cannot be simply added.  
&nbsp;  

Because this is a balanced 3-phase system, we can establish a reference such that phase A voltages are at a phase angle of 0.  This means phase B voltages are at a phase angle of $\tfrac{2\pi}{3}$ (or 120 degrees).  
&nbsp;  

Because this is a balanced 3-phase system, we know that both phases have the same magnitude, i.e., $|V_{DA}|=|V_{DB}|=2500V$.  We use these facts, plus some trig, geometry, three-phase rules, phasor math, or vectors (pick your poison) to find the rest of the voltages that involve sums of quantities with differing phase.

&nbsp;  

## Equation List

`$$
\boxed{
\begin{align*} 
V_{A-NA} &= 2 \cdot V_{DA} \tag{1} \\
V_{A-G} &= V_{DA} \tag{2} \\
V_{A-B} &= V_{DA} - V_{DB} \tag{3} \\
V_{AN-G} &= -V_{DA} \tag{4}\\
V_{AN-BN} &= V_{DB} - V_{DA} \tag{5}\\
V_{A-BN} &= V_{DA} + V_{DB} \tag{6}
\end{align*}}$$`

---

## Plug and Chug


`$$ 
\begin{align*} 
|V_{A-B}| &= 4330V \tag{3}\\
|V_{AN-BN}|&=4330V \tag{5}\\
|V_{A-BN}|&=2500V  \tag{6}
\end{align*} $$`

![Alt Text](content/example-motor-phasor-sums.png)

&nbsp;  

## Equation List

`$$
\boxed{
\begin{align*} 
V_{A-NA} &= 2 \cdot V_{DA} \tag{1} \\
V_{A-G} &= V_{DA} \tag{2} \\
V_{A-B} &= V_{DA} - V_{DB} \tag{3} \\
V_{AN-G} &= -V_{DA} \tag{4}\\
V_{AN-BN} &= V_{DB} - V_{DA} \tag{5}\\
V_{A-BN} &= V_{DA} + V_{DB} \tag{6}
\end{align*}}$$`

---

## Objective

**Does this meets requirements?**  
**Is it ok?**  
  
We have all voltages of concern.

`$$
\begin{align*} 
|V_{A-G}| &= 2500V \\
|V_{A-B}| &= 4300V \\
|V_{A-AN}| &= 5000V \\
|V_{AN-G}| &= 2500V \\
|V_{A-BN}| &= 2500V \\
|V_{AN-BN}| &= 4300V \\
\end{align*} $$`

![alt text](/content/mil-e-917-table-1.png)

---

Wait...What about that requirement to operate with a ground?

---

## Schematic With A Ground

![Alt Text](content/example-motor-schematic-with-ground.png)