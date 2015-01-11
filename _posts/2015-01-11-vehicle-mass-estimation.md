---
layout: post
title: Real-time Estimation of Electric Vehicle Mass Using CAN Bus Signals
---

## The Goal
Real-time mass estimation was one of my projects during my coop term in Singapore. The goal of the project was to use CAN bus signals to estimate the mass of an electric vehicle (the Mitsubishi iMiEV, seen below) in real time, without augmenting the vehicle with any additional sensors. Accurate mass estimates can be used for numerous purposes, including fleet management and better range to empty estimates.

<img src="/assets/images/mass-estimation/imiev.png" alt="Mitsubishi iMiEV"/>

## CAN Bus Signals
Modern vehicles have numerous sensors built in, including wheel encoders, torque sensors and electrical sensors. The challenge part is knowing which signal belongs to which sensor. All of the signals are transmitted using the same format, which can be seen in the figure below:

<img src="/assets/images/mass-estimation/can_message_frame.JPG" alt="CAN Message Structure"/>

In order to figure out which signal corresponed to which sensor, I wrote a program to parse the incoming CAN bus messages and plot the signals in real time. The driving data was also logged so that it could be analyzed after the fact. After a week or two of testing, analysing and confirming hypotheses, the signals corresponding to the each of the wheel encoders, the motor torque, velocity were identified.

## The Model
In order to use the Kalman filter for vehicle state estimationm, I needed to come up with equations to describe the state dynamics through time. Basically, the torque from the motor can be propogated through the drivetrain to become force acting at the wheels, which serves drive the vehicle forward. Opposing the wheel force are friction and aerodynamic resistance. Additionally, the wheel encoders can be used to determine the actual distance travelled by the wheels over the interval between measurements. 

By comparing the torque output by the motor to the actual change in vehicle velocity over an interval, an estimate can be produced for the mass of the vehicle and its occupants and cargo. 

## The Experiment
The test track consisted of a level straightaway approximately 75 metres in length, as shown below:

<img src="/assets/images/mass-estimation/test-track.png" alt="Block 71 Test Track"/>

The testing procedure used one driver, with four passengers to vary the vehicle mass. Initially without passengers, the driver accelerated down the straightaway, braked, performed a three point turn, and accelerated back to the initial position, braking once more. Each time this sequence was executed, an additional passenger would enter the vehicle, until all four passengers where on board for the last run. The speed profile of a single section can be seen below:

<img src="/assets/images/mass-estimation/single-ae.png" alt="Single acceleration event"/>

Using the methodology discussed above, the average absolute error for the five runs was 1.0%, with the largest error being 2.7%. **This means that in the average case, the estimated mass of the vehicle, passengers and cargo was accurate within 14 kilograms.** 

<img src="/assets/images/mass-estimation/mass-estimate.png" alt="Mass estimate plot"/>

My experience in Singapore left me with a deep appreciation for electric vehicles and the enormous potential that they offer. The rate of innovation in this field is absolutely staggering, and I find the possibility of being a part of it truly exciting.