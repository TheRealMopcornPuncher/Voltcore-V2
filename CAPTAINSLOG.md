**This project seeks to heavily improve and upgrade the Voltcore 3d printer with a height extension, new motherboard, klipper modifications, and new electronics.**
# Project phase 2 (To be treated as a new project)
## PERMISSION GRANTED BY ALEX REN TO CONTINUE WORKING ON THIS PROJECT FOR HIGHWAY.

---

### Project info:
Made by: @Amaya and @Jonathan G 
Repository link: https://github.com/TheRealMopcornPuncher/VoltCore-V2

BOM: https://docs.google.com/spreadsheets/d/1q4xtd6th8_cM6Qn8iwp2R4_8qS0gYeFDji75B9E_PQI/edit?usp=sharing
! Sections separated by black cells, lower section represents BOM for this project. !

Image dump: https://drive.google.com/drive/folders/1CzOQAVNjcckL8AMjF_pA2h7jqu7bDclE?usp=sharing

Fusion 360 Project Link: N/a

Total calculated hours: 13 hours

---
# Day 29
### April 24th

After getting permission from Alex, we're continuing this project and making it actually work! As well as severely upgrading our major oversights.

The following upgrades will be implemented:
- Extend height and modify frame
- Fix motherboard issues
- Create custom voltage regulators for both the raspberry pi and the motherboard, respectively
- More to come later on as we work

Total time elapsed: 1 hrs

---

# Day 30

### June 1st

Happy pride loves <3

Today, I'll be remodeling and rejointing the CAD assembly of Voltcore into a new and improved design that should actually work in real life this time.

To begin, I'll reassemble the frame.

![Bottom frame image](https://hc-cdn.hel1.your-objectstorage.com/s/v3/455ffc18b062616104de7c46508d86c65febef1b_image.png)
(Bottom frame assembly)

Took me a minute to remember how the hell you put images here, but I'm doing it more often from now on for Alex's sake. (NOT MAD - I SHOULA DONE THIS FROM THE START, IK)

One of the major issues with the way we assembled the printer in CAD before stemmed from the fact that we were using a single file to combine minor modules into one single device. This creates major issues later down the road when you need to change things because suddenly, the ONE poorly modelled bracket you created 17 log entries ago has broken 87 other joints in the file. To fix this on "take two" of this project, we'll be finalizing the designs of major modules and combining them into the final printer only when said modules are completed in their own respective folders and files.

My current dilemma is picking whether or not I should fully assemble the major modules or do that in the complete printer CAD assembly file.

Or, I could make two versions of the major modules, split by assemblies with all their respective components or just the bare frame structures.

I think I'll just finish the assemblies with all their components.

![Slightly more assembled bottom frame image](https://hc-cdn.hel1.your-objectstorage.com/s/v3/f989f2215c31deb8114b969681c9292347db9749_image.png)
(With Y axis attached)

The bottom frame still needs the electronics mountings, but I think I wanna opt instead for a side mount this time around.

Speaking of the electronics, we need mounting for the following:
- Voltage regulator from battery to the mainboard
- Voltage regulator from mainboard OR battery into the RPI for Klipper firmware
- Mainboard

Jeez, with a side mounted mainboard and RPI we really are just ripping pages out of Prusa's book aren't we TT oh well.

Anyways, we'll leave the bed for now and work on the gantry.

![In progress image of upper frame/gantry](https://hc-cdn.hel1.your-objectstorage.com/s/v3/ed94aa00e3b17c2f19d6c6754a6357e27fc46be8_image.png)
(Extended 100mm in height from older versions)

We previously had issues with the filament spool holder not having enough clearance, and our solution to that in the past significantly increased the size profile of the printer, so I've remodeled the entire component to make use of vertical space.

![Spool holder image](https://hc-cdn.hel1.your-objectstorage.com/s/v3/e0d8b1513e1dcee3fdc498589528d5317c7422a0_image.png)
(Improved spool holder)

For the remaining components I need to add for this upper part of the frame, we need the extruder, and the side mounts for our electronics.

After that, we should be ready for a full assembly with the hardware (screws and whatnot) and all components put together :D

Though, the belt tensioner for the gantry needs a serious upgrade, so I may be forced to redesign the entire thing again.

Total time elapsed: 3 hrs

---

# Day 31
### June 2nd

Today will be dedicated to attempting to finalize the CAD assembly of all previous modules for Voltcore (since we are redoing everything). Afterwards, I will spend my time working on the new components.

I started the work for today by doing a bit of maintenance around the log. (Adding the total hours up from every entry). I found a neat way to automate the process by programming a small tool to add the hours for me by pulling the hours listed after the words "Total time elapsed: " and before "hrs"

Then, after that quick little maintenance job, I decided to work on modeling the side mounting hardware for the mainboard and the raspberry pi. Regarding the pi, we'll have the budget for a Raspberry Pi 0w 2, so the mount will use that device's profile instead of the original Pi 0w (no clue if they're different, too lazy to google.)

![Mainboard diagram](https://i.imgur.com/ovnYgTu.jpg)
(Diagram of creality 4.2.2 mainboard mounting dimensions)

![Old mainboard mounting solution image](https://hc-cdn.hel1.your-objectstorage.com/s/v3/8222bf469672b1ea9b6dc910a37df682c85eaf48_image.png)
(Old mounting solution)

Using the dimensions provided in the diagram above, we'll be remaking the mainboard mounting hardware. A nice little upgrade this time around is the fact that we can actually add a cooling fan for the steppers, since we didn't really know what we were doing for that previously. The old design was terrible, it was flimsy and shook like crazy, and generally just had a ton of oversight.

Thanks to the fact that this embarrassment of a component exists, we can now create the upgrade.

The hard part will definitely be routing the cables. The mounting hardware needs to be rigid enough to stay put while the resistance of the cables presses against the sides of the module. In addition to that, we'll need to likely do a clearance check with my calipers to see the maximum height of the board with all cables attached. I will do this now.

! Quick update, after taking a small break and coming back to the google sheet containing our BOM, I learned that there *is* no available for purchase creality 4.2.2 motherboards. !

Design will pivot to the Big Tree Tech SKR PICO (V1) motherboard.

![BTT SKR PICO V1 Mounting diagram](https://hotend.s23.cdn-upgates.com/_cache/b/9/b9965915701fbb4f62c89ce6b18cafe4-2759.jpg)
(Above is a diagram displaying the necessary dimensions for mounting the motherboard, courtesy of hotend.eu)

Now with the motherboard chosen and the diagram provided, we can design an actual mounting bracket for the component. 

God why does no one ever fully dimension a product... TAKE NOTES FROM MCMASTERCARR FOR THE LOVE OF. breatttthhh breathing. I'm fine.

Anyways, I have no idea what the mounting specifications are for this device since the only thing I have to go off of is this vague diagram of a raspberry pi zero w underneath the SKR PICO V1's mounting holes, and... I guess that's their way of saying it's M2.5??? Kinda stupid, but sure, whatever.

![Terribly demonstrated diagram of SKR PICO mounting holes](https://media.printables.com/media/prints/419749/images/3479539_32346841-3f11-49f7-8e0c-8fa8d38b03be/thumbs/inside/1920x1440/jpg/pxl_20230310_054143612.webp)
(Okay, I lied, this is a real life image, couldn't find the stupid diagram I mentioned earlier.)

The image I found above this text gives me a few ideas for mounting the electronics, and buddy, AM I EXCITED.

But nerdy b.s. contained, I think this confirms that it's the same mounting hole dimensions across both boards.

God how low have I sunken from the social ladder to have programmed an entire executable for counting hours from text files in a single hour...

![Updated motherboard mounting bracket](https://hc-cdn.hel1.your-objectstorage.com/s/v3/5f6963cd2ac22a9c4a620af23072367efe76aa36_image.png)

Anyways this is what I came up with for the motherboard's mounting bracket. Super simple for now, but I need to create a second half for the cooling fan.


Total time elapsed: 4 hrs

---


# Day 32
### June 3rd

New days, new ideas. I was thinking about how we could mount the fan, when I thought about how the SKR PICO looks. Then, I noticed the heatsink over the stepper drivers, and I immediately realized that the open air motherboard image we saw before with this board was using passive cooling.

For good measure, I will still add a fan, but I can tell it's a lot less necessary.

![Extending fan mount](https://hc-cdn.hel1.your-objectstorage.com/s/v3/98128011832982a010262903db8bc9db554842d4_image.png)

This fan mount extends from the side and creates a rigid overhang for the fan to attach to above the motherboard. This mount works for us since it removes the need to factor clearance, io, or anything else in the construction of an enclosure, since this design is still devoid of one.

With the mainboard and fan shroud mounts designed, we can design an additional mount for the raspberry pi 0w, though from the previous images it seems that it might not be necessary. Better to be safe than sorry though.

Total time elapsed: 2 hrs

---

# Day 33
### June 4th

Beginning with some general file maintenance, I added all of the new screws from the assortment kit that I added to the BOM recently. 

There's only really one new size, M2, but we were running low on leftovers from the last screw kit, so it's better to be safe then sorry and just get enough for the entire project.

! Migrating logs to a new file to distinguish work between the V1 and V2 phases of Voltcore. !

Just created a new repository to store all new work regarding this second phase to Voltcore since the first attempt I made to submit the project to highway was declined. I'm hoping they'll see it's a new project, but we'll cross that bridge when we get there.

Anyways, back to actual work. I need to finish adding the hardware into the electronics mount and create a mount for the raspberry pi zero w.

![Fully implemented mainboard mounting assembly](https://hc-cdn.hel1.your-objectstorage.com/s/v3/2c823c481b381826f3b127588f9da1540480c7f4_image.png)
A little bit of hardware later and the mainboard is good to go, now for the pi.

This mount is very simple, considering the nearly 100% flat base of the Pi Zero.

![Raspberry Pi Zero 2 W Mount](https://hc-cdn.hel1.your-objectstorage.com/s/v3/98bb1899ad19e45898dc508397237e8bd1befc29_image.png)

Just some inset slots for the hex nuts and the right thickness to match our screw length.

The pi itself will need to feed power from (most likely) the mainboard, so either ANOTHER mount for that, or we find some other way to efficiently modify our existing solutions to incorporate one.

I'm losing speed for now, so I'm going to take a break and come back to work on that.

It seems that the SKR PICO thoughtfully has an already implemented connector dedicated for connecting a raspberry pi, so additional hardware is not necessary. The mount should suffice as is, given a slight depression on the bottom to account for any bulge leftover from solder jointing.

![Fully assembled Pi mount](https://hc-cdn.hel1.your-objectstorage.com/s/v3/e5c7ef3a8c2d77b5f2f4c8c304d545538d7c04be_image.png)


Now with all of the modules fully assembled onto the upper frame:
![Upper frame assembly](https://hc-cdn.hel1.your-objectstorage.com/s/v3/2fdcda1148223f3ef6fd1638abf7c9a4013f185c_image.png)
It's coming along pretty nicely at this point, but obviously there's still the gantry to take care of, and storage for the battery.

I think that the smartest location for storing the battery is, again, whichever solution utilizes the vertical profile of the printer, since we're still trying to keep this machine relatively portable.

To store the battery, we'll need some kind of lock-in under carriage to slot it into. The carriage would ideally be made of aluminum so that the heat generated from the battery wouldn't cause any kind of deformation. An additional fan or heatsink may also be necessary to deploying the device considering the potential for extreme heat generation from the battery.

Moving to other modules, the gantry requires a minor adjustment to the tuning mechanism. It took me a bit to remember how I designed it to function, considering I have little to no organizational or proper journaling skills, but I quickly remembered the sliding carriage I designed to tension via a screw (very similar to the tensioning device employed on the Ender 3 V3 SE).

Anyways, I ended up extending the amount of space it can tension by about 3mm.

I'm thinking that stabilizers will ALSO need to be deployed for the linear rods, which we'll ALSO need to buy new 300mm long versions for to accompany the extended height of this upgrade. I will add this to the bill of materials, now.

Although I haven't done a complete calculation and clearance simulation for the extended height, if I had to estimate the improvement, I'd say it's fairly substantial. Our previously calculated (and measured) build volume clocked in at 100x100x60 (x, y, z - mm). Those numbers are, for obvious reasons, dissatisfactory. The height improvement from this upgrade should be able to double the height, and then some, hopefully increasing to about somewhere <150 mm.

Regarding a task list for tomorrow, I recommend the following:
- Add updated gantry to Upgrade Major Modules folder
- Fix motors and brackets to the base
- Model stabilizers for the linear rods to fix at the top of the upper frame
- Add linear rods
- Begin finalizing battery storage solution
- Brainstorm additional upgrades

Hats off to you two tomorrow, good luck & goodnight for now ^^

Total time elapsed: 3 hrs

---

# Day 34
### June 5th



Total time elapsed: 0 hrs

---
