---
layout: post
title: 'Tesseract'
subTitle: 'Autonomous Event'
logo: /img/event/tesseract/logo.png
actions:
  -
    text: 'T'
    caption: 'Tutorial'
    link: '../../tutorial/event/tesseract/'
---


#### Introduction

It’s a time fraught with tension for the Avengers, charged with bringing the Tesseract, containing the Space Stone, one of the six Infinity Stones home to safety. The stone’s immense power has attracted hordes of villains and power hungry beings around the universe, who are lying in ambush. It is your job to map out a safe and secure path for Tony Stark to get home with the stone. His life, and the fate of the entire universe, is in your hands!

#### USP

*   Line Following Mechanism
*   RFID Cards Reading
*   Path Planning and Optimization


#### Problem Statement

To build an autonomous robot capable of traversing through the arena through a safe and optimized path generated by solving algorithms on data transmitted by RFID cards, to reach the end point.

#### General Description and Event Setup

*   The arena will be a 6x6 grid, with white lines on a black arena.

*   It is a virtual multidimensional arena with multiple levels stacked one on top of the other, aligning perfectly.

*   Each intersection of white paths, called a node, will have an RFID tag, transmitting integer data.

*   The data transmitted will be of the format- (level number, number of points of ambush around, above and below it). For example, ((1,2), (2,1)) at one node means at the 1st level, there are 2 ambush points all around it and on the 2nd level, there is 1 ambush point all around it. (The start node is safe.)

#### Arena

##### Both Round1 and Round 2

![](/img/event/tesseract/arena.jpg){:.img-responsive}

All dimensions are in cms. ALl RFID Cards are placed beneath the arena (readable using the sensor from above the arena).

##### Arena specifications

*   The distance between each node will be 30 centimetres.
*   The dimensions of each node will be 4x4 centimetres.
*   The outer dimensions of the arena will be 200 x 200 cm.
*   The dimensions are to be considered with a maximum tolerance of 10%.

##### RFID Card Specifications

*   Universal readable using 13.56MHz RC522 RFID Reader Sensor

*   “Credit Card” sized plastic white MIFARE RFID Cards

##### Robot Specification

*   The robot must fit in a cube of side 17.5 centimetres with a tolerance of 10% in its dimensions.

*   No part/mechanism of/on the bot should exceed the given dimensions before the commencement of the event.


##### Event Rules

*   The bot has to traverse the arena using line following mechanism.

*   The initial run can be traversed by the bot in whichever way it so chooses, starting from the start node, storing data from all the tags as it goes.

*   Once the bot has traversed the entire arena, (it has reached the diagonal end) it has to display the correct location of all the points of ambush on the LCD display, in the format - (x,y,z) - where z is the level number.


##### Restarts and Timeouts

* A maximum of **2 Timeouts** of **1 minute** each may be taken. **Penalty** will be awarded for each timeout and robot will start from its stopping position on the arena.

* The participant’s robots can have a maximum of **2 restarts**. A penalty will be imposed on the team for every restart that they take.

* After the restart, the participant’s robot will be set to its **initial** position. Timer will be set to zero and the run will start afresh with the addition of the **penalty** for **restart**.

* A timeout can be taken **anytime** at the user’s discretion.

* A restart can **only** be taken if there is a genuine **technical** fault in the robot. Team ROBOTIX may refuse a restart if the reason does not sound genuine enough, and their decision will be binding and final.

#### Round 1

##### Task

*   The arena will consist of 1 level. The bot has to traverse the arena and read the data from the RFID tag on each node.

*   After the first run, at the end point, the bot will have to display all the ambush points in the aforementioned format.

*   From the end point, the bot has to traverse the arena through a path free of ambush points and reach the starting point.

*   There will be just one such path.


#### Round 2

##### Task

*   The arena will consist of 3 virtual levels. The bot has to traverse the arena and read the data from the RFID tag on each node.

*   After the first run, at the end point, the bot will have to display all the ambush points in the aforementioned format.

*   From the end point, the bot has to traverse the arena through a path free of ambush points and reach the starting point.

*   Every time the bot changes levels during its journey, the level to which it is going should be displayed on the seven segment display, in the format - (level number).

*   There will be 2 paths, one with higher energy (where higher energy refers to using more nodes on the higher levels and every level has a 20% increase in its energy), and one with lower energy.

*   The paths will have different number of segments (distance between two nodes ) and different number of turns.

*   The bot has to traverse the arena using the lower energy path, or the fastest path (with lesser number of segments), depending on the total number of ambush points. If there are an odd number of points, the fastest path should be taken, and vice-versa.


##### Scoring Formula

* **Positives**

*   Base Score – 1000(A)

*   Traversal – 200(B)

*   Detection/display of each correct ambush point – 40(C)

*   Each safe node traversed while returning- 30(D)

*   Correct constraint followed in Round 2- 400(E)

    

* **Negatives**

*   For each ambush point traversed while returning: 20(G)

*   For each timeout: 100(F)

*   For each restart: 150(G)

*   For damaging arena: 400(H)

**Formula:**

{% highlight ruby %}
A+B+40*C+30*D+400*E-20*G-100*F-150*G-400*H
{% endhighlight %}

**Note:**

* **Example 1:**

Trial demonstration for a 3x3 arena-

*   Readings from RFID Tags:
![](/img/event/tesseract/ex11.jpg){:.img-responsive}


*   After analyzing and solving the readings from RFID, the ambush points to be safe from during the return journey are shown below.
*   Row, Column indices displayed by the bot on the LCD display before the return journey: (1,2), (2,3), (3,1).
![](/img/event/tesseract/ex12.jpg){:.img-responsive}

*   Return path followed by the bot:
![](/img/event/tesseract/ex13.jpg){:.img-responsive}


##### General Rules

* Maximum number of participants allowed per team: **4 people**.

* The participants will be provided with **220 Volts, 50 Hz** standard AC supply.

* Only **16 bit** microcontrollers or below will be allowed.

* Participants will have to arrange for any other power supply required for their robot.

* Teams cannot tinker with their robots during the run.

* [LEGO kits](http://en.wikipedia.org/wiki/Lego_Mindstorms) or its spare parts are not allowed.

* The decision of the Team Robotix will be **final** and **binding**.

* The rules are subject to change.

It is suggested to the participants to try making a wireless robot, powered by a battery on-board.

**Links to Tutorials:**

For relevant tutorials check [ROBOTIX TUTORIALS](https://www.robotix.in/tutorial/).

##### Contact

###### Anirudh Roy

Email: **[anirudh.roy@robotix.in](mailto:anirudh.roy@robotix.in)**

Ph. no: **+91 7011549352**

###### Manthan Patel

Email: **[manthan.patel@robotix.in](mailto:manthan.patel@robotix.in)**

Ph. no: **+91 9033034268**

