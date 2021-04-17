
# Extruder Force Comparison
#### BY: Razgriz, Anlin, The Annex Team
#### Updated: 2021-04-16
--------------

**NOTE:** If you have an extruder you'd like us to compare, and the data on its motor (if we don't have it yet) let us know! [Join our discord](https://discord.gg/MzTR3zE), we'd love to talk about it.

Don't like math? [Skip to the plots](###%20Force-Flow%20Curves) (but keep the context in mind!)

----------
Extruder performance is a critical part of a well-functioning 3d printer. Here, we examine the filament force performance vs. flow rate of various extruder designs:

NEMA 14 (LDO-36STH17-1004AHG)
- [Sherpa Mini](https://github.com/Annex-Engineering/Sherpa_Mini-Extruder) (10-tooth 5:1 and 8-tooth 6.25:1 variants)
- [Orbiter](https://www.thingiverse.com/thing:4223085) (7.5:1)
- [Ascender](https://github.com/Annex-Engineering/Folded_Ascender-Extruder) (20:1 "Double Folded" variant)

NEMA 17 (LDO-42STH20-1004AS1)
- [BMG](https://www.bondtech.se/product/bmg-extruder/) (and equivalents, e.g. Voron Clockwork)
- [Bondtech LGX](https://www.bondtech.se/product/lgx-large-gears-extruder/) (~6.996:1)
- Bondtech Mini (BMG-style dual drive gear, 1:1 off NEMA 17- Used in [Prusa](https://help.prusa3d.com/en/guide/5-extruder-assembly_82960/) i3 MK3s)
- [Creality Extruder](https://creality3d.shop/collections/extruder-kit/products/creality-3d-all-metal-mk-8-extruder-feeder-drive-aluminum-1-75mm-for-cr-10-cr-10s-ender-3) (40-tooth brass gear, ~11mm diameter, 1:1 off NEMA 17)

Where relevant, we also examine the differences between the 17.5mm and 20mm models of the LDO-36STHxx-1004AHG round NEMA 14 motor. 


## Why Force?
Comparing the force that different extruders can produce allows us to incorporate the characteristics of the motor, gear reduction, and drive gear into a comparison that shows roughly how well they're able to handle high material flow rates. This doesn't entirely encapsulate extruder performance - far from it, it's very much a single part of the puzzle. Factors like gear size allowing longer engagement (as in the Orbiter and LGX), backlash, packaging, and many others all play a part. For reference, here's a compiled list of the weights of each extruder (except for the Bondtech Mini, which is now off the market), 

#### Extruder Weight
| Extruder Name    | Motor               | Motor Weight | Extruder Weight | Package Weight |
|------------------|---------------------|--------------|-----------------|----------------|
| Sherpa Mini      | LDO-36STH17-1004AHG | 70           | 40              | 110            |
| Sherpa Mini (8t) | LDO-36STH17-1004AHG | 70           | 40              | 110            |
| Ascender         | LDO-36STH17-1004AHG | 70           | 62              | 132            |
| Orbiter          | LDO-36STH17-1004AHG | 70           | 65              | 135            |
| BMG              | LDO-42STH20-1004AS1 | 127          | 75              | 202            |
| Bondtech Mini    | LDO-42STH20-1004AS1 | -            | -               | -              |
| Bondtech LGX     | LDO-42STH20-1004AS1 | 150          | 120             | 270            |
| Creality         | LDO-42STH20-1004AS1 | 127          | 49              | 176            |

## Force Multiplier Calculation
To determine the filament force, we need need to know the overall gear reduction of an extruder, its efficiency, and the effective diameter/radius of its drive gear - that is, approximately where it meshes with the filament itself. With these data, we can define a "force multiplier value", which allows us to determine the output force for a given input torque. It's calculated by dividing the overall reduction by the drive gear radius and multiplying by the drive gear efficiency. 

```
force_multiplier [N/(N*mm)] = efficiency * gear_reduction / drive_gear_radius [mm]
```

A higher force multiplier value translates to increased pushing force for a given torque input, but higher is not strictly better, as it will require the motor to spin faster. This becomes important when considering flow rate, as stepper motors generally drop off in torque as their rotational speed increases. This means the pushing force of a given extruder will drop off faster with flow rate if it has a higher reduction. We can tell there's going to be a "sweet spot" for this value for a given motor and range of flow rates.

The following table lists out the data we're using for our various extruders. Note that the gear radius is a bit hard to measure exactly, and we're relying on it being *relatively* correct, especially relative to other extruders sharing the same gears. 

#### Extruder Characteristics

| Extruder Name    | Motor   | Drive Gear   | Reduction Geartrain | Efficiency | Overall Reduction | Drive Gear Radius [mm] | Force Multiplier [N/(N*mm)] |
|------------------|---------|--------------|---------------------|------------|-------------------|------------------------|-----------------------------|
| Sherpa Mini      | NEMA 14 | Bondtech 5mm | 50:10               | ~95%        | 5.000             | 3.6                    | 1.32                        |
| Sherpa Mini (8t) | NEMA 14 | Bondtech 5mm | 50:8                | ~95%        | 6.250             | 3.6                    | 1.65                        |
| Ascender         | NEMA 14 | Bondtech 5mm | 20:1                | ~36%*        | 20.00             | 3.6                    | 2.00                        |
| Orbiter          | NEMA 14 | Bondtech 8mm | 7.5:1               | ~90%        | 7.500             | 5.2                    | 1.30                        |
| BMG              | NEMA 17 | Bondtech 5mm | 50:17               | ~95%        | 2.941             | 3.6                    | 0.78                        |
| Bondtech Mini    | NEMA 17 | Bondtech 5mm | 1:1                 | 100%       | 1.000             | 3.6                    | 0.28                        |
| Bondtech LGX†     | NEMA 17 | Bondtech LGX | 45:14, 37:17        | ~90%        | 6.996             | ~8.9                    | 0.75                        |
| Creality         | NEMA 17 | Brass Gear   | 1:1                 | 100%       | 1.000             | 5.5                    | 0.18                        |

\*Worm drive efficiency depends heavily on the friction between the driving and driven gear - this value isn't well characterized for the Ascender - more on this topic in the future!

† We don't have the data on the LGX motor itself, so we've assumed it's similar in performance to the LDO 20mm motor used for the other NEMA 17 extruders. 
 
## Motor Speed/Torque

To create extruder force-flow curves, we also need to know the torque-speed characteristics of the motors used. For simplicity, we're going to use the pull-out torque curve, although the actual dynamics of torque and speed are more complex than this. These curves have been provided by LDO for the following motors, and are shown in Figure 1. Note that there's incomplete data for these curves at higher speeds. In order to approximate this, we'll use a linear extrapolation, indicated by the dashed line on the curves.

![\[\]](https://i.imgur.com/tY4pY67.png)

We can convert this to flowrate by incorporating the filament, drive gear, and reduction. We'll use the standard 1.75mm. This gives us a cross-sectional area of `A = Pi * D²/4 = Pi * (1.75mm)²/4 = ~2.405 mm²`. Then, for a given flow rate (in `mm³/s`), we can determine the filament speed, and thus the motor speed, as such:

```
filament_speed [mm/s] = flow_rate [mm³/s] / filament_area [mm²]
drive_gear_circumference [mm/revolution] = 2 * Pi * drive_gear_radius
motor_speed [revolutions/minute] = filament_speed [mm/s] * (60 [s/min]) * gear_reduction / (drive_gear_circumference [mm/revolution]) 
```

From here, we can determine the motor speed for a given flow rate for each extruder. These are just linear with flow rate, so we'll just compare the motor speeds at a fixed value of 20 mm³/s. We can see that this, for the most part, scales with gearing; The aggressive 20:1 ratio of the Ascender gets the motor sweating, while the direct driving Creality and Bondtech Mini maintain a very leisurely pace. 

#### Extruder Motor Speed at 20 mm³/s Flow Rate

| Extruder                 | RPM |
|--------------------------|------------------|
| Sherpa Mini (36STH17)    | 110              |
| Sherpa Mini 8t (36STH17) | 138              |
| Ascender (36STH17)       | 441              |
| Orbiter (36STH17)        | 115              |
| BMG (42STH20)            | 65               |
| Bondtech Mini (42STH20)  | 22               |
| Bondtech LGX (42STH20)   | 62               |
| Creality (42STH20)       | 14               |



## Force-Flow Curves

Now that we've got all the data we need, we can take a look at our force performance!

![Extruder Force vs. Flow Rate](https://i.imgur.com/gKzr1WR.png)

The Ascender again makes a splash, with its 20:1 worm reduction producing massive force that quickly drops off as the motor speeds up. 

The Sherpa Mini and its 8-tooth variant both perform admirably, with a drop off from around 180 to 120 N across the flow rate range.

Interestingly, the Orbiter performs very similarly to the Sherpa Mini - the larger drive gears and the larger reduction "cancel each other out", so to speak. 

The BMG itself, as well as the new Bondtech LGX, offer comparable performance to each other as far as force is concerned. 

The Bondtech mini-style ungeared extruder, as well as the Creality brass gear, are both languishing at the bottom. They simply do not put out much force at any flow rate, and will quickly run into backpressure issues.

## NEMA 14: 17mm vs 20mm?

Finally, let's take a look at what happens when we compare the Sherpa Mini (10 and 8 tooth), Orbiter, and Ascender with the 17mm and 20mm variants of the LDO-36STH*. We can see that, for the Sherpa Mini and Orbiter, given this motor's lower torque at low speeds, it actually *loses* performance below 30-40 mm³/s! On the other hand, the Ascender benefits greatly from the longer torque curve, reaching its maximum force around 25 mm³/s. All extruders end up benefiting across a longer range.

![Extruder Force vs. Flow Rate for 17mm vs 20mm motor](https://i.imgur.com/vV7GXok.png)

-------------
## Conclusions
Extruder force provides an interesting look at an important performance aspect of a printer's extruder. From looking at the data, we think there's some notes to be made.

Our big takeaway: **ungeared extruders should be left in the past**. They simply don't utilize everything a stepper motor can provide, and their force is abysmally low compared to geared options.

Moving from the 17mm to the 20mm motor on the Sherpa Mini or Orbiter seems to have marginal benefit unless you're *really* pushing plastic - you're adding additional weight and volume for a loss in performance at the flow rates most extruders can put out. 

Bondtech's BMG remains a great extruder solution, and it's given us the parts to make great designs, but there's a lot of room for improvement. It's outperformed in size, force and weight by the Orbiter (\~135g) and Sherpa Mini (\~110g). 

We'd love to dig into the LGX more - while its force curve is outperformed by other extruders, the increased diameter and filament grip may offer benefits not captured by this analysis. 



-----------

Thanks for reading! Remember: this analysis isn't absolute, and as mentioned before, performance is captured by a *lot* more than just force. 

*Thanks to Jason and LDO motors for providing the test data for their motors, their continued support of Annex and the 3D Printing community at large.*
