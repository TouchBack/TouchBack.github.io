---
layout: post
date: 2014-03-06
title: Leap/Arduino Analog Communication
---

The Python software now receives the position of a hand from the Leap Motion, calculates a number between 0-255 for each axis, calculates a strength for the motor (between 0 and 255) dependent on the distance away from the Leap Motion, and sends that to the Arduino through a Serial Connection. A special type of data structure is used to store the data, called a **F**airly **L**ightweight **O**bject **R**eadabilit**Y**-**A**ssisting **N**otation (FLORYAN). The Arduino then parses it, and the corresponding RGB and motor values are converted into an analog signal and sent to the correct outputs. 

We had run into a memory leak issue when uses the String class in the Arduino. Apparently, Arduino Strings have a known memory leak issue, so that was causing our Arduino to freeze and stop accepting input. After switching to character arrays, the issue was fixed. 

\- Justin