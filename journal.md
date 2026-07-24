---
title: "hackbook-mobo"
author: "Rabieulawal.h"
description: "a laptop motherboard from which you can swap the compute mudule to upgrade it"
created_at: "2026-07-17"
---

# July 17th: Finding the base

So i wanted to make a laptop but needed to make a shipable project before arcana so i chosed to make a motherboard. i really need to spend about 75hrs on this to get finded for my flight and if i cant make those hours i wont be able to make it to arcana :( .
anyways this day was a mess i wanted to find a base like a compute moudule to build upon cuz getting good cpus for laptops from the manufacturars is very hard so i spent the time looking at different compute mudules which i could use initally i decided to use the raxda cm5 which was arm bassed and way more powerful then the pi CM5 but when i tried to find documentation or guides on how to make a carirar board, it was limited.
they did a refrence pcb and schematics but they were in altium format and i used easyeda and no matter how much i tried i could not import them. so then i looked at the lattepanda Sigma but it was a think SBC instaed of a CM so i could not use it then i found the lattepanda MU
which was a compute moudule which comes in 2 variations 1. the intel N100 cpu 3. the inted I3 N305 which is good and way more powerful then any arm CM and also gives you native support for windows and games so i chsed to make a board which will use that CM

then i looked at orther opensource boards and almost left easyeda for Kicad but then remembered that i have a potato laptop




<img width="1909" height="955" alt="image" src="https://github.com/user-attachments/assets/e30183fe-8265-441d-9858-b2ef690b1b54" />

<img width="1383" height="791" alt="image" src="https://github.com/user-attachments/assets/2b349d1c-12fc-42a8-a840-699833e5c0f5" />

view the lapse <a href="https://lapse.hackclub.com/timelapse/8sIibp9u_gPk"> here </a>

**Total time spent: 4h**


# July 18th: starting to make the schematic

today i started to make the schamatic from strach i did look at the offical board for refrence thu

the MU exposes 260 pins via a SO-DIMM conector so i started to make the motherboard finally i started by adding the conector and then added the USB 3.0 and USB 2.0 ports along with the required safty and the decopouling caps needed for usb3.
then i went on to add the pcie stuff so the MU exposes 9 pcie lanes my plan was that i will add 2x M.2 m-key slots each using 2 lanes and a M.2 E-key slot using 1 lane and the remaining 4 lanes would be used for adding an external gpu later.
but i found out that the USB 3.0 ports use a pcie lane too so then i made 1 M.2 M-key slot with 4 lanes instead so we can get faster speeds i was able to wire up the M-key slots but not the E-Key is this day.




<img width="793" height="587" alt="image" src="https://github.com/user-attachments/assets/196be080-09a7-4454-beed-ff64917efe61" />

<img width="774" height="565" alt="image" src="https://github.com/user-attachments/assets/9b23d6a0-5911-4953-9c31-7124b2de6287" />

view the lapse <a href="https://lapse.hackclub.com/timelapse/5_vfc3R1NDdu"> here </a>
and 

**Total time spent: 5h**

# July 19th: adding power and sound

i first wired the leftover M.2 E-key slot and then went over so make the power section i chosed if i wanted a simple 12v barrel jack or USB-C power delivery i chosed usb-c but only for power delivery so you can nt plug anything in which amkes sense as you will be charging the laptop or a lot of time and adding usb suport over thaere just wastes a usb pin

so the Mu supported from 9-20v so i made the usb-c ak for 20v then i found out that if i am going to use the eDP port to add a laptop screen which i would for a laptop then i would need to supply the same voltage which the display needs so i needed to give it 20v 
for that i added a step-up/step-down buck which will take the 5-20v from the usb and give me 12v which will go to the MU then anorther Step down buck converter which would give me 5v from the input voltage to power the usb and lastly i needed power for the m.2 slots now it would be hard and expensive to find a converter whch would work if the ssds were at max load so i added 2 converter which would power 2 saprate 3.3v power rails.

then i added the fan header i chosed to add 12v fans as they can provide more airflow but then i would not be able to send info abt the fan back to the MU 
then i added the battery charging system which would charge the battery and provide power when needed now i needed to chose a battery which i looked online and could not find a slim replacement then i found a dell battery which was not only 87Wh which was near my goal of abt 95wH and also was small enough to fit in the case as well 
then i started to make the sound system i wanted this to sound very good and i did not add any jack cuz they are pretty old fashioned now days so i added an audio aplimfier and ports where speacker could be plugged into 
but i could not find a good one and ended the day oh and i also added a display port as well 

<img width="802" height="561" alt="image" src="https://github.com/user-attachments/assets/b8b1718c-202b-439c-b404-76c9e6b243b2" />
<img width="871" height="523" alt="image" src="https://github.com/user-attachments/assets/d88cab28-7ec4-40e4-b29a-76c7f6301f7d" />
<img width="474" height="390" alt="image" src="https://github.com/user-attachments/assets/9e5c9ff4-cec0-49cb-b69f-8207bfe20159" />
<img width="947" height="328" alt="image" src="https://github.com/user-attachments/assets/10ac30cd-1abb-4576-b516-9b404742328d" />



the lapse for this day are here
<a href="https://lapse.hackclub.com/timelapse/e6BJlXP0E2l9"> lapse 1 (17 min) </a>

<a href="https://lapse.hackclub.com/timelapse/UzW4XwU9ijQr"> lapse 2 (15 mins) </a>

<a href="https://lapse.hackclub.com/timelapse/UzW4XwU9ijQ"> lapse 3 (26 mins) </a>

<a href="https://lapse.hackclub.com/timelapse/4yO9-tS6QsLz"> lapse 4 (2.5 hrs) </a>

<a href="https://lapse.hackclub.com/timelapse/tx_Q4U2pJNyh"> lapse 4 (4.5 hrs) </a>

**Total time spent: 8h**


# July 20th: mic and keyboard idea

this day i stared by finding the pin for the speker and then i added a port where you can plug wires to the power button then i added the microphone stuff so and 2 slots where you can plug 2 mics into as well so you can have some good audio then i added the battry holder for the CMOS battery so the laptop can remeber things and added a power led which will turn on while chafrging off then done and blink if a fault is found then i thinked off adding a keyboard and touch pad at the back of the motherboard so i can make the laptop very thin but then decided not to do that as that would have decresed upgeadbility so its better if you can make wat ever keyboard pcb you want and put it on top of the mobo so you are can custom buttosn or anyting you want which open a door for some very nice mods 

<img width="674" height="397" alt="image" src="https://github.com/user-attachments/assets/cd74126d-d06d-43d7-954b-bb18ece08db4" />
<img width="514" height="542" alt="image" src="https://github.com/user-attachments/assets/c468c70f-73b6-46ce-8f22-9eaa3d852996" />
<img width="507" height="312" alt="image" src="https://github.com/user-attachments/assets/924ebb65-68d6-4251-b245-891bbf5759be" />


you can view the lapse <a href="https://lapse.hackclub.com/timelapse/imT_KYaWfusl"> here </a>

**Total time spent: 2hr and 15mins**


# July 21th: finalising the schematic

this day i finalisined the schematic fixed all the net errors and fixed conections which were not done i also added a reset buton on the mobo so you can reset if needed and also added a header which is conected to usb 2 so that you can add what ever keyboard you want on it
then i converted it into pcb and hecked what size i want the mobo to be for my 14 inch laptop and then finlly placed some of the compenents on the motherboard 

<img width="489" height="372" alt="image" src="https://github.com/user-attachments/assets/d679cad9-75b8-404a-9ff5-1cc5a65b6c19" />

<img width="734" height="426" alt="image" src="https://github.com/user-attachments/assets/c15e16bb-dfb7-4620-9556-52e63a30087f" />

you can view the lapse <a href="https://lapse.hackclub.com/timelapse/J0sNRB-f07MA"> here </a>

**Total time spent: 2hr and 45mins**

# July 22th: starting the pcb desgin

i just aranged all the componenets on to the pcb now how do i yap on that and yes i still have not aranged the audio stuff like the mic and specker yet.
also i fixed a usb-c conector cuz it did not have a 3d model
i made this a 6 layer pcb 

L1        smd stuff and short traces 
L2        Solid GND
L3        High speed signals
L4        GND plane
L5        low speeds stuff
L6        low speed stuff + power + back side smd traces



<img width="461" height="424" alt="image" src="https://github.com/user-attachments/assets/87c82fc1-eafd-451c-a397-5596d8390116" />

you can view the lapse <a href="https://lapse.hackclub.com/timelapse/s4lgSFZhRGzL"> here </a>

**Total time spent: 4.5hr**

# July 23th: doing some wiring

this day i wired the pcbs short conections like all the resistor and capsitors on the m2 and power stuffon the top ;ayer only and also added usb diffrencical pairs one of which i broke and fixing it broke all the pairs and now i have a random traffic jam in the pcb ill have to see what to do with that 
i also wrote all of m journals from my real journal on to github

<img width="676" height="451" alt="image" src="https://github.com/user-attachments/assets/999311c9-36d8-4736-8094-62256d447f93" />

<img width="768" height="605" alt="image" src="https://github.com/user-attachments/assets/929ede01-794f-475a-b7a7-0944e30fd2d7" />


the lapse for this day are here

<a href="https://lapse.hackclub.com/timelapse/paLhetz1VoBc"> lapse 1 (2hrs) </a>

<a href="https://lapse.hackclub.com/timelapse/7OWOgC5KflWf"> lapse 2 (1hr) </a>

<a href="https://lapse.hackclub.com/timelapse/gbw1T7mWE8Z-"> lapse 3 (15 mins) </a>

<a href="https://lapse.hackclub.com/timelapse/0AtCXQS3zhZm"> lapse 4 ( 20 mins) </a>

<a href="https://lapse.hackclub.com/timelapse/Bl70RRqhfBTj"> lapse 4 ( 10 mins) </a>

<a href="https://lapse.hackclub.com/timelapse/7J0VacIkP8DO"> lapse 5 ( 1hr) </a>

<a href="https://lapse.hackclub.com/timelapse/vJk3yUXgJNWP"> lapse 6 ( 1.5hr) </a>

**Total time spent: 6h and some mins**




