---
layout: post
title: Extended Kalman Filter for State Estimation of an Omni-wheel Vehicle
---

This was an assignment for the Autonomous Mobile Robotics (ME597) course I'm taking. Given the vehicle shown below, we needed to come up with a motion model and then use simulated multi-rate GPS data to track the state of the vehicle. 

The reason that the Extended version of the Kalman Filter was used is because the wheel speeds affect the position of the vehicle in different ways depending on the heading.

Low accuracy GPS data was received at 10 Hz, with a more accurate measurement occuring at a rate of 1 Hz. The following figure shows the actual path in red, the estimated path in blue, with measurements in green. 

In addition, we needed to come up with an inverse model in order to generate a variety of paths. Here are some of the cooler paths, including a constant speed spiral and a couple of epicycloids.