---
layout: page
title: Formula SAE
---
# FSAE

I have participated in FSAE since 2015, initially as a competitor and now as a mentor to my former team and volunteer tech inspector.

## FSWiki

Emily Anthony started the <a href="https://fswiki.us">FS Wiki</a> to create an open knowledge sharing platform for the Formula Student and FSAE community. I encourage all FSAE compeititors who will listen to use the site and contribute when they can.

This project aligns very closely with my personal approach to engineering and student competition. I have been a strong advocate, long-time user, and frequent contributor. I have added the majority of the IC powertrain content on the site <!--(possibly to the detriment of all users lol)--> as well as information regarding data collection, analysis, and visualization. I have shared a large quantity of data that was taken when I was in college as examples for students to use.

I am particularly proud of the <a href="https://fswiki.us/Intake">intake design</a> page for its completeness and the collaborative effort made by the community. Another point of pride is the graphics I made for the pages for <a href="https://fswiki.us/Tensioner">chain tensioning</a> and <a href="https://fswiki.us/Throttle">throttle design</a>.

The grahics for the pages were made in inkscape, a free design software that can be found here: <a href= "https://inkscape.org/">https://inkscape.org/<a>

## Alumni Outlook and Accomplishments

### Suspension: Winning the battle, after losing the war

My senior year FSAE competition ended anticlimactically. Our car failed 3 laps into endurance after our lower control arm buckled, leading to a failed steering rack, and an undriveable car. The puzzling part: there's a bend right in the middle of the lower aft link. The car was rounding a slow corner, maybe 0.3-0.5 g of lateral acceleration. We were all stumped. Lo and behold, the car that gets built after the pandemic, which continued to use our suspension geometry, breaks their lower control arm. I get this picture in March of 2022:

![A broken lower wishbone from a formula Sae car](/docs/assets/2020_LCA_failure.jpg)
* Apparently we passed on a bit too much of the torch *

That looked eerily familiar. My nemesis had returned. Along with some other alumni, we brainstormed with the team to try to dig into what went wrong. I started by digging into how they designed the suspension links: what forces were they expecting, and how did they predict them. The low hanging fruit would be undersized links causing an expected failure. They were using the same calculations we were in 2019, a discovery I should have seen coming. This meant we missed something my year, so I felt some level of responsibility. The Matlab script said it should work, and the buckling load calculations showed a factor of safety I felt comfortable with.

The calculations we ran in 2019 modeled the maximum lateral acceleration we could achieve. However, they simplified one key aspect: the wheel turn was negligible. After all, the same acceleration can be achieved at an arbitrarily high radius of curvature, so we can ignore it... right? Except we weren't seeing failure at max a_y. From a video I was sent of the recent failure, I did some back of the napkin math: width of a parking space 2.5m, the car took 8-10 frames to cross parking space, 30 frames per sec = ~8-9 m/s, skid pad radius ~20m gives a_y of ~4m/s or 0.5g which makes sense for Cooper Union.

This meant our model was ignoring something really big, big enough to break the car 2 years running. The failure on both occured at low speed, near full lock. Steer angle was not represented in our model. That proved to be our bugbear.

![A very crappy sketch of a wheel turning and changing the direction of force application](/docs/assets/napkin_sketch.png)
* Jimmy Neutron would have called this a "brain blast" *

### Aero

I have a complicated relationship with aero devices on Cooper Union's FSAE cars, and most FSAE cars in general. Aerodynamics as a field and as used in professional motorsports is neigh unimpeachable. It's like a magic sauce sprinkled to make everything better and faster. To complicate things further: I built Cooper Union's first set of wings during the summer of my freshman year at Cooper with a gravity-fed hot wire cutter me and another student designed and built in a day. As you can see below, these wings really stressed the "concept" in "proof of concept"

![A picture of Simon lying next to the wings described above. The wings are blue and sanwiched between plywood end plates. Ben is leaning over them pointing. His face is obscured for privacy and "BEN" is written over it](/docs/assets/wings_v1.jpg)
*The very first wings that ever did go on that car*

This being said, I saw aero as an idea grow from an unimplemented senior project to a convoluted mess of foam, plastic, composites, and vinyl that cost the team untold man-hours and had zero imperical data to back it up. Every year, the team dutifully pumped out pretty pressure maps, and colorful flow analyses. Every year, we cut foam, sanded molds, and stuck our big NACA contraption on the back of our racecar. Every year, we promised we would get data to back it up, and every year we didn't. (until now haha, ty Aidan).

Each year I write an email to the team stating the following: I believe that a select few people were instrumental in getting the team to focus on aero, and with their graduation, I think it's wise to look at the resources and personnel that the team has at its disposal, especially because even with said dedicated members, the team had issues getting aero finished. This is ever more pressing after covid.

As an alumni, the most important thing to me is to see the car in person, and to see the team have a fundamental and complete understanding of the work they've done. The simpler the car, the easier this will be, and aero is not necessary for the car to run, or for the car to do well in competition.

I know it can feel kinda lame to go backwards in terms of technology, and that's definitely something we had to fight when I was on the team. I'm pretty confident that finishing the car earlier and more completely will be more than worth it.

## The Glory Days

### 2019 Season: Powertrain Lead

![The 2019 car at a test day. It is in the rain, the ground is wet. The engine is screaming. Life is good.](/docs/assets/2019_test_day_car.jpg)
*The 2019 car at the last test day before competition. Rain is pouring, the ground is wet. The engine is screaming. Life is good. Note: Aero is not on the car, as it had not been finished.* 

As a senior, I was given the job to lead the powertrain subsystem. Having never worked in powertrain in FSAE before, my approach was to make sure the work we did under my direction was bulletproof. I focused on documentation, data collection, and knowledge transfer.

##### <a href="/2019_FSAE.html">Read More</a>

### 2018 Season: President

![Final shot of the 2018 car. There are no wings on it. The main focus is the front left wheel which is turned to the right.](/docs/assets/2018_comp_car.jpg)
*Final shot of the 2018 car after competition*
