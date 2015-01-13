---
layout: post
title: Autonomous Boat Project
---

## Goal
Design a boat capable of navigating a 3 meter by 6 meter pool without human intervention or control, while maximizing the value of speed (i.e lap time) squared divided by mass. The dimensions of the vehicle were constrained to be able to fit into a cube of 30 cm.

## Electronics
The first thing our team did was build a test platform (shown below) in order to test our electronics. Obstacles avoidance was accomplished using a combination of IR range sensors and ultrasonic sensors, and a compass/gyro for determining the orientation of the boat during manoeuvers. The test platform used a single small motor and a rudder for propulsion and steering.

<img src="/assets/images/autonomous-boat/proto-hull.png" alt="Test platform"/>

## Prototype
With functioning electronics, we constructed a new prototype with a catamaran twin-hull design and a dual motor differential steering system. The second prototype was 3D printed, sanded and then coated with varnish for waterproofing. The photo below shows a comparison of the two platforms:

<img src="/assets/images/autonomous-boat/hull-comparison.png" alt="Comparing hulls"/>

After the catamaran hull was ready to go, the electronics were transferred over and the second motor was added:

<img src="/assets/images/autonomous-boat/final-electronics.png" alt="Catamaran electronics"/>

## Results
What resulted was a machine bred purely for speed... in a straight line. While our boat was without a doubt the fastest in a drag race, our design had some serious oversights. Because of its extremely low profile, the sensors would sometimes confuse the waves caused by the boat's wake for the wall of the pool. The only way for our boat to complete the course was to reduce speed significantly, to about a third of its maximum. We ended up 6th out of 36, a disappointing finished for us.

The whole point of this class was to learn about the design process and I can wholeheartedly say that I learned many things, usually the hard way.

* **High and dry is a good way for sensors to be. Or waterproof.**
* **Compasses are only as good as the magnetic field they're in.**
* **Decouple everything. Electrons are fickle.**
* **Design for manufacturing, assembly and repairs - someone has to do all three.**
* **A timely wrong decision is better than no decision.**
