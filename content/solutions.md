
# Application Example: Motor Terminal Box

---

## Schematic

![Alt text](content/motor_terminal_schematic.png)

---

## KVLs

![Alt text](content/motor_terminal_kvls.png)


---

## KVLs
$ + V_{A-NA} - V_{DA} - V_{DA} = 0 $  <!-- .element: class="fragment highlight-blue" data-fragment-index="1"-->  

$ V_{A-NA} = 2 \cdot V_{DA} $ &nbsp;&nbsp;&nbsp;&nbsp; (1)<!-- .element: class="fragment"-->  

$ V_{B-NB} = 2 \cdot V_{DB} $ <!-- .element: class="fragment"-->  

$ +V_{A-G}-V_{RA}-V_{DA}=0 $ <!-- .element: class="fragment highlight-red" data-fragment-index="2"-->  

$ V_{A-G} = V_{RA} + V_{DA} $ &nbsp;&nbsp;&nbsp;&nbsp; (2)<!-- .element: class="fragment"-->

$ V_{B-G} = V_{RB} + V_{DB} $ <!-- .element: class="fragment"-->

$ +V_{A-B} +V_{DB} + V_{RB} - V_{RA} - V_{DA} = 0 $ <!-- .element: class="fragment highlight-green" data-fragment-index="3"-->  

$ V_{A-B} = V_{DA} + V_{RA} - V_{RB} - V_{DB} $ &nbsp;&nbsp;&nbsp;&nbsp; (3) <!-- .element: class="fragment"-->

---

## KVLs

We know from the given information that $ V_{A-NA} = 5000V $.  
Therefore, we know from equation (1) that $V_{DA} = 2500V$.
  
&nbsp;  
By inspecting the circuit we can see that there are no conducting closed loops that would allow current to flow through the high resistance ground resistors $RA$ and $RB$.  
Therefore, we know that $V_{RA} = 0$ and from equation (2) that $V_{A-G} = V_{DA} = 2500V$.  

&nbsp;  
Since this is a three phase system, if we assume phase A voltages are at a phase angle of 0, then phase B voltages are at a phase angle of $\tfrac{2\pi}{3}$ (or 120 degrees). We also know that both phases have the same magnitude, i.e., $|V_{DA}|=|V_{DB}|=2500V$.
This relationship, in conjunction with equation (3) yields $V_{A-B} = \sqrt{3} \cdot 2500V = 4330V$.





---

## Slide 5 - Lets do a wall of text

>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Risus feugiat in ante metus dictum at. Sit amet nisl purus in mollis nunc sed id semper. Lacus sed turpis tincidunt id aliquet risus feugiat in. Est lorem ipsum dolor sit amet consectetur adipiscing elit pellentesque. Mauris vitae ultricies leo integer malesuada nunc vel. Elit duis tristique sollicitudin nibh sit amet commodo. Duis at consectetur lorem donec massa sapien. Facilisis gravida neque convallis a cras semper auctor. Lobortis mattis aliquam faucibus purus. Nam at lectus urna duis convallis convallis tellus id. Nisl tincidunt eget nullam non nisi est sit amet. At imperdiet dui accumsan sit amet nulla. Amet nisl purus in mollis nunc sed id. Donec ultrices tincidunt arcu non sodales neque sodales ut.
