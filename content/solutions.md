
# Application Example: Motor Terminal Box

---

## Schematic

![Alt text](content/motor_terminal_schematic.png)

---

## Terminal Box Layout

---

## Objective

**Does this meets requirements?**  
**Is it ok?**  
  
We need to determine the magnitude of the peak voltages between the various conductors, and evaluate whether the spacing meets the required spacing at those voltages.  Specifically, we need to figure out:
- $|V_{A-G}|$
- $|V_{A-B}|$
- $|V_{A-AN}|$
- $|V_{AN-G}|$
- $|V_{A-BN}|$
- $|V_{AN-BN}|$

---

## KVLs

![Alt text](content/motor_terminal_kvls.png)


---

## KVLs
$ + V_{A-NA} - V_{DA} - V_{DA} = 0 $  <!-- .element: class="fragment highlight-blue" data-fragment-index="1"-->  

$ V_{A-NA} = 2 \cdot V_{DA} $ &nbsp;&nbsp;&nbsp;&nbsp; (1)<!-- .element: class="fragment"-->   

$ +V_{A-G}-V_{RA}-V_{DA}=0 $ <!-- .element: class="fragment highlight-red" data-fragment-index="2"-->  

$ V_{A-G} = V_{RA} + V_{DA} $ &nbsp;&nbsp;&nbsp;&nbsp; (2)<!-- .element: class="fragment"-->

$ +V_{A-B} +V_{DB} + V_{RB} - V_{RA} - V_{DA} = 0 $ <!-- .element: class="fragment highlight-green" data-fragment-index="3"-->  

$ V_{A-B} = V_{DA} + V_{RA} - V_{RB} - V_{DB} $ &nbsp;&nbsp;&nbsp;&nbsp; (3) <!-- .element: class="fragment"-->  

&nbsp;  
...more KVLs...more algebra... <!-- .element: class="fragment"-->  

$ V_{AN-G} =  V_{RA} - V_{DA}$ &nbsp;&nbsp;&nbsp;&nbsp; (4) <!-- .element: class="fragment"-->  

$ V_{AN-BN} = V_{DB} - V_{DA} + V_{RA} - V_{RB}$ &nbsp;&nbsp;&nbsp;&nbsp; (5) <!-- .element: class="fragment"-->  

$ V_{A-BN} = V_{DA} + V_{DB} + V_{RA} - V_{RB}$ &nbsp;&nbsp;&nbsp;&nbsp; (6) <!-- .element: class="fragment"-->  

---

## Simplify
  
By inspecting the circuit we can see that there are no conducting closed loops that would allow current to flow through the high resistance ground resistors $RA$ and $RB$.  This tells us that $V_{RA}$ and $V_{RB}$ are 0. With this information we can simplify of equations (2), (3), (4), and (5).  
$V_{A-G} = V_{DA}$ &nbsp;&nbsp;&nbsp;&nbsp; (2)  
$V_{A-B} = V_{DA} - V_{DB}$ &nbsp;&nbsp;&nbsp;&nbsp; (3)  
$V_{AN-G} = -V_{DA}$ &nbsp;&nbsp;&nbsp;&nbsp; (4)  
$V_{AN-BN} = V_{DB} - V_{DA}$ &nbsp;&nbsp;&nbsp;&nbsp; (5)  
$V_{A-BN} = V_{DA} + V_{DB}$ &nbsp;&nbsp;&nbsp;&nbsp; (6)  

---

## Plug and Chug

We know from the given information that $|V_{A-NA}| = 5000V$  
&nbsp;  
Therefore, we know from equation (1) that $|V_{DA}| = 2500V$  
&nbsp;  
Likewise, $|V_{DB}| = 2500V$  
&nbsp;  
Note the magnitude bars now being applied!

---

## Plug and Chug

$|V_{A-G}| = |V_{DA}| = 2500V$  
&nbsp;  
$|V_{AN-G}| = |-V_{DA}| = 2500V$   
&nbsp;  
Again, equal magnitude but the signs are opposite between these two!

Notes: These are the easiest ones because the don't involve a sum of numbers with different phase, and thus can be calculated as a simple sum.

---

## Plug and Chug

Since this is a balanced three phase system, we can establish a reference such that phase A voltages are at a phase angle of 0.  This means phase B voltages are at a phase angle of $\tfrac{2\pi}{3}$ (or 120 degrees). We also know that both phases have the same magnitude, i.e., $|V_{DA}|=|V_{DB}|=2500V$.  We use these facts, plus some trig, three-phase rules, phasor math, or vectors (pick your poison) to find the rest of the voltages that involve sums of quantities with differing phase.

---

## Plug and Chug

$$|V_{A-B}| = 4330V$$
$$|V_{AN-BN}|=4330V$$
$$|V_{A-BN}|=2500V$$  

---

## Objective

**Does this meets requirements?**  
**Is it ok?**  
  
We have all voltages:
- $|V_{A-G}| = 2500V$
- $|V_{A-B}| = 4300V$
- $|V_{A-AN}| = 5000V$
- $|V_{AN-G}| = 2500V$
- $|V_{A-BN}| = 2500V$
- $|V_{AN-BN}| = 4300V$

**MIL-E-917 requires 3" for clearance and (for enclosed equipment) creepage and the minimum distance through air between our conductors is 3"**  

