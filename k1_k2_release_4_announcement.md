
# The K1 and K2 Release 4.0 Change of Structure Announcement aka "The Annex Manifesto"
#### A pile of word vomit, Mostly Written by Trails, Proofed for sanity by the Annex Dev Team
#### Updated: 02-04-2024
--------------

**NOTE:** Have a comment or an issue, please [Join our discord](https://discord.gg/MzTR3zE), we'd love to talk about it.

## Intro
Hi, my name is Trails, I've gone by a few other names in the 3dp arena (Feb and Volcom). My real name is Brandon, I'm in my 30s and I've been doing this whole “design a printer” thing for longer than most have been part of the community as a whole. I have a masters in Mechanical Engineering, and have worked in both the design and manufacturing space in a few industries for about 13 years. Today we are going to tell a story then have a quick one sided discussion on why K1 and K2 are going to a partially closed source model. Maybe we can also correct some misconceptions about Annex and what we stand for as a group.

## History
Annex was founded a few years ago, back before the mystical thing known as covid had taken over the land. The group started with a few members of the internal voron dev team and didnt quite like the direction some things were going; the Annex namesake came from an inside-joke about how all the real engineering in the was done off in the “annex” (ie: off in a ditch somewhere). Six months after "founding" Annex, I departed the Voron team and community, and took this as my “second full time job”. A few other community and dev members followed, most of whom make up the development team you see today.

When the collective was originally founded, there were two members, Matt (mattthebaker) and myself. Matt worked on what is now the beacon project and I focused on ~15 printer concepts until the K1 and K2 printers were dreamed up after a youtube rabbit-hole adventure. Most of these never saw the light of day. Others joined quickly, and out spun Ascender, Sherpa, K3, and Redoubt. All of these early designs had one thing in common, the creator didnt like what they saw, and wanted to make it better, safer, or just different. Some early members will remember the Matterhorn project, which used a modified stratasys XY drive setup with servos and a heated build chamber. This unfortunately was shelved due to cost (at the time), complexity, and lack of availablility of rapid sheet metal prototyping. Since starting, according to my wife, I have spent too much fucking time working on that hot melt glue gun in the dining room. We stopped counting at about 1500 hours of development, 2 long years ago. We dont discuss dollars spent, because thats just plain sad.

## Community
People have come and gone from the team, but the “directive” was always to build the “insert x here” you want to build, and give no fucks about what anyone else says. Given our community just crossed 10k members a few weeks ago, it seems that were doing exactly what the enthusiast community wants. While we dont have the size or grasp of Prusa/Bambu/Voron, each member of our community is important; Therefore, we want to make sure that our claims match what our users get when they “invest” in the purchase and build of one of our products.

## Safety, Commitments and Licensing
The team puts safety and the quality of the project above all else. Therefore it's up to each one's discretion if they open source their work that they likely sacrificed time from their job or family to perfect. Members of the Annex development team manage their own projects and each one/group of members reserves the right to release each project however they/the team feel is best. They could be open, closed, or a mix of both formats; licenses may also vary.


## Release 4 - A New Beginning
It turns out, while having a large community is great, it attracts some bad actors. We’ve seen some people try to take advantage of the community and peddle trash and toxicity. While most of these never make it onto the sourcing guide or community, they are still available on aliexpress and the like to tempt end users. In the interest of quality control (and let's be honest, funding development, because that's important too) the K1 and K2 motion system (ie: the XYZ system) will be going closed source for the R4 release. 

## Why the change?
The intention of the 4th release of these printers is to "move up market" and into the higher temp space (~125C). Things like the frame have been changed to make space for insulation, chamber heaters have been added ("youll burn your house down kid"), belts have been widened to stiffen the motion system, and PCBs have been redesigned to live in these spaces for a longer period of time. We have also moved the recommended hotend to "Chube Conduction" as this better aligns with the elimination/better packaging of fans on the toolhead (hint hint). 
<br><br>Bambu and Prusa have proven that we are a very small subset of the enthusiast community, as they've shown, with their entry into the ~2500$+ space, most people just want a turn key thing that works. Moving to billet for most parts and higher temp rated components (such as belts and rail carts) allows two things; a more rigid machine and better print quality in a huge range of materials. Unfortunately. this does nuke most to the reprapness of these printers. This is a change that we have elected to make to continue to push the performance and quality mark for our printer ecosystem. For anyone concerned about cost, or just having a reprap, we will continue to direct you to the K3 printer, and eventually K3+. Builders can also opt to use the older frames, not fit all the heating components and kick out quite a nice passive ASA/ABS printer for a few grand.

#### The items that will stay open source are as follows:
 - The frame
 - The panels, doors, and exterior structure
 - The electrical box
 - The toolhead (with a bounding box provided in the model)
 - The bed and heater
 - Anything not listed below

#### Item that will move to closed source
 - The X and Y drives and motor towers (the CNC and laser cut parts)
 - The z drive mechanism and its “joints” to the bed (the CNC and laser cut parts)
 - The wiring kit schematics (including carabiner)
 - The custom PCBs

#### What will be provided on release
 - eDrawings and 3D PDF of the machine
 - PDFs of the bed and heaters
 - X_T files of the frame, panels, doors, ebox and toolhead
 - STLs for anything still FDM printed
 - A Sourcing Guide

#### What will maybe come someday, no promises:
 - A manual


## Purchasing
Anything closed source will be available to purchase from either of the Annex stores, and other carefully selected partners. For other vendors, this doesn't mean you wont be able to sell it, it just means you need to be approved to, just like everything else.


## Open Beta
The R4 XY drive open beta will start soon (only currently applicable to K2). The Annex US Store will be the only source of the respective plates. These will be purchasable on a quote only basis, at cost + 10%, and manufactured by our carefully selected vendors to ensure high quality. I, Trails, run this store. We use sources that I have found during my time in manufacturing that “don't make shit” and/or provide a good value for the dollar. XY joints / belt tensioners are recommended to be machined aluminum, but designs exist for plastic (and thus will be provided when the time comes), this results in a 3-5hz reduction in input shaper results, depending on build volume.


## Closing Thoughts
The Annex team feels that we have been a pillar of innovation in this space. We want to continue bringing novel and exciting high performance designs to you all. It's this, or myself and other devs will fold up Annex and move onto the next fun thing. Bad actors in the community have delivered sub par products based on our innovations for years. These innovations all the while cost us, temporally, financially, and mentally. These actors give nothing of value back to the community and in our view this is unacceptable. We refuse to allow it to continue. Therefore moves like this feel like they are the only realistic option. Remember, just like life itself, in the end, you are entitled to nothing. Good things take time, commitment, and blood/sweat/tears. All of us have sacrificed something in our lives to bring cool Annex things to the community. Please don't ruin it for the rest of us. 

<br>
Signed,
<br>Trails