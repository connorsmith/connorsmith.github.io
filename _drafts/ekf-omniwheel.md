---
layout: post
title: Extended Kalman Filter for State Estimation of an Omni-wheel Vehicle
---

This was an assignment for the Autonomous Mobile Robotics (ME597) course I'm taking. Given the vehicle shown below, we needed to come up with a motion model and then use simulated multi-rate GPS data to track the state of the vehicle. 

The reason that the Extended version of the Kalman Filter was used is because the wheel speeds affect the position of the vehicle in different ways depending on the heading. Thus, the motion update equations are linearized about the current belief of the vehicle's heading.

Low accuracy GPS data (variance of x meters North and East) was received at 10 Hz, with a more accurate measurement (variance of x meters North and East) occuring at a rate of 1 Hz. A magnetometer with a variance of of x degrees was used to provide information about the vehicle's heading. The following figure shows the actual  vehicle path in red, the estimated path in blue, with measurements in green. 

The errors on the each of the state variables are shown here.

It can be observed that each time the more accurate GPS measurements were received the error dropped.

An addition requirement of the assignment was to come up with an inverse model in order to generate a variety of paths. The vehicle can only be controlled by adjusting the rotational speed of each of the three wheels, which is why the problem is not as trivial as simply specifying the desired velocity in the intertial coordinate frame.

This is a constant speed spiral, and the three wheel speeds needed to generate the trajectory.

This is an [epicycloid](http://en.wikipedia.org/wiki/Epicycloid), and the three wheel speeds needed to generate it.