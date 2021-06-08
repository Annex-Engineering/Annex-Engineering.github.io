
# Rebreather - Comparision with Alternative Fan Options
#### BY: Papejelly, The Annex Team
#### Updated: 2021-06-8
--------------

For a well-functioning filtration system design, the characteristics of the fans are critical. The filtration system designs that we will talk about here are the [Nevermore micro](https://github.com/0ndsk4/VoronUsers/tree/0ndsk4/printer_mods/0ndsk4/Nevermore_Air_Filter/Nevermore_Micro) and [Annex Rebreather](https://github.com/Annex-Engineering/Rebreather). 


![\[\]](https://i.imgur.com/Ao0v1Kn.png)

*On the left the Nevermore Micro from xceled#2905, on the right the Annex Rebreather from papejelly#1768*

----------
## Motivation
Some users have expressed their concerns about the fans that were selected for the Annex Rebreather design. The claims are, that the static pressure of the fan is too low to properly function, which in turn leads to the claim that the filter only works at half the speed of the Nevermore micro. In this short write-up a small test with a calibration bag is conducted to draw a conclusion, in an attempt to debunk these claims.


## Why a calibration bag?
A [calibration bag](http://www.storeldar.com/CalibrationBag10LiterLDAR1126TVAphx21.aspx) is a cheap way to measure for example the amount of flow from a fan. Calibration bags can be found in chemical refineries and industrial plants to calibrate sensors such as the [phx21](http://indusinstruments.com/indus-engineering/project/phx21-flame-ionization-detector/).


#### Fans tested
- [Delta BFB0512HH](https://www.delta-fan.com/products/dc-centrifugal-fans/BFB0512HH-F00.html)
- [Delta KFB04512HHAF0C](https://www.delta-fan.com/KFB04512HHAF0C.html)


## Testing methodology
A plastic bag with a volume of roughly 60L is used as calibration bag. The same bag was used for all tests. The fan inside the housing of the respective filter will blow up the plastic bag. 

The goal is to see what time it takes for each to blow up the calibration bag fully hard, delivering both flow and pressure. Each fan is measured 6 times.

![\[\]](https://i.imgur.com/kQ1cRx1.jpg)


## Measurements

| Delta BFB0512HH (s)   | Delta KFB04512HHAF0C (s)    |
|-----------------------|-----------------------------|
| 24.74                 | 35.10                       |
| 23.65                 | 37.28                       |
| 21.49                 | 39.11                       |
| 21.33                 | 36.90                       |
| 22.50                 | 38.49                       |
| 22.13                 | 36.18                       |
 
 
## Calculations

| Fan                   | Average time in seconds     |
|-----------------------|-----------------------------|
| BFB0512HH             | 22.64                       |
| KFB04512HHAF0C        | 37.18                       |
| Dual KFB04512HHAF0C*  | 18.59                       |

\* For the dual KFB04512HHAF0C the time is assumed to have halved compared to single.

#### Conclusion
What can be concluded from the table above, is that dual KFB04512HHAF0C’s blow up a 60L bag hard more quickly than a single BFB0512HH. Other observations are that the KFB04512HHAF0C’s operate at a lower noise ceiling, and the BFB0512HH is able to blow up the bag to a more "solid" state, due to the static pressure afforded by the fan.

One of the goals of Rebreather was to refine the nevermore micro design and not use glue to mount the fans. With this experiment it shows these fans suffice. The options that lie ahead in the future are to test the dual [KFB0612HAFDB’s](https://www.delta-fan.com/technology/KFB0612HAFDB.html) once they come back in stock. One can also conclude that using dual 5015 fans would be an even more powerful design (but thus requires glue again). The success of the design is also highly dependent on the physical size and contact area of the pellets in the cartridge.

#### Pricing
When it comes to pricing it heavily depends on which model fan you chose for the Nevermore Micro. A good 5015 blower such as the Delta BFB0512HH can be found for around 12 euro. The spec fan for Rebreather can be found around 8 euro. For the total pricing you would be looking at 12 euro vs 14 euro for the fans making the price difference negligible. One could substitute to a cheap gdstime 5015 but can expect a big performance decrease. 

**NOTE:** Cheaper fans often do not flow at the same rate as a fan from a proper manufacturer, as they are not engineered to the same standards. Future testing could be performed to determine how much slower/lower volume a typical "clone" fan will flow.

**NOTE:** Feel free to replicate the test. If you have any suggestions or ideas you like to share you can find us on [Discord](https://discord.gg/MzTR3zE)

-----------

Thanks for reading! Remember: this analysis isn't perfect. With more expensive tools a better analysis could be performed.

