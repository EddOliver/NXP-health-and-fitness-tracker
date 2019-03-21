# NXP-health-and-fitness-tracker
Two wearable devices that become a fitness tracker using the NXP Rapid IoT prototyping kit, ESP8266 board and AWS. Alexa compatible!

<img src="">

Things used in this project:

Hardware components:
- NXP Rapid IoT Prototyping Kit
- Li-Ion Battery 100mAh	
- Custom case
- Pulse Oximeter & Heart Rate Sensor based on MAX30100	
- NodeMCU ESP8266 Breakout Board
- push button
- Straps
- Wrist Stap ( a chunky one)

Software apps and online services:
- Arduino IDE	
- NXP IDE
- AWS IoT	
- Amazon Web Services AWS IoT
- AWS DynamoDB	
- Alexa Skills Kit	
- AWS Lambda	

Hand tools and fabrication machines:
- Soldering iron 
- Digital Multimeter

## Story
DISCLAIMER: This application is used for demonstrative and illustrative purposes only and does not constitute an offering that has gone through regulatory review. It is not intended to serve as a medical application. There is no representation as to the accuracy of the output of this application and it is presented without warranty.

## Introduction
For this contest I decided to change the way to approach IoT. This time instead of something theoretical or unproven, the end product has to be something designed for daily use, in this case something very useful for myself. Apart from that I want something with a huge market and preferably should be trending.

One aspect of my persona that I wish to share is that I'm kind of a meathead. I like to go lift weights and there is a series of products which are trending right now that have always dissappointed me....

Be it an activity band, fitness watch or a clip-on tracker – there's no shortage to choose from. Fitbit, Garmin, Xiaomi, Misfit and Polar are the leaders in the game, with bands to suit every budget and fitness level.

<img src="https://hackster.imgix.net/uploads/attachments/782570/image_iVmFRKGOLQ.png?auto=compress%2Cformat&w=740&h=555&fit=max">

BUT most of them have two main problems. The first one is that most of them do a poor job for tracking weight training, the second one has to be in relation with the heart rate monitor they have. Most of them have the heart rate sensor on the back, big mistake, that area moves around a lot and not even the best sensor will make sense of what you are doing so you get faulty readings. In this case it is much better having the sensor on the side and just take sporadic reading or if you really need continuous reading a chest sensor is much better.

The second main problem is that they are not adapted to my workload which is mainly anaerobic, or hoisting weights.

Getting back to the project, lets check on the NXP prototyping kit:

<img src="https://hackster.imgix.net/uploads/attachments/782192/supported_bxwj0I6vqY.png?auto=compress%2Cformat&w=740&h=555&fit=max">

So we have most of the needed sensors for a fitness tracker in the package: Motion sensors, environmental ones, a touch interface, a couple indicators and BLE.

Let's try and build a Fitness tracker with this, mainly focused on anaerobic exercise, but with aerobic capabilities as well (sometimes you have to do that dreaded cardio).

## Solution
The solution will be a small fitness tracker that monitors several aspects such as motion and environmental ones, and on the side I probably will add some other capabilities.

By re-engineering clinically validated technologies with new and out of the box IoT technologies like the NXP kit, the device will measure temperature and motion. The wearable will be powered by its own little battery and will wirelessly transmit health data to a central monitoring application which will help the user. You don't have to have all the sensors integrated into one project. I don't need to know light intensity to do my exercise.

A second wearable will be developed via the ESP8266 Node MCU board and it will track Heart rate and blood oxygenation via the MAX30100.

And just for fun I want a web-based dashboard and to be able to consult everything with Alexa.

This should be very fun, we will build two wearables and connect them together in a single platform.

<img src="https://hackster.imgix.net/uploads/attachments/780411/image_zl9Epxs0wr.png?auto=compress%2Cformat&w=740&h=555&fit=max">

## Mechanical build.
We will have to build a case to transform the IoT kit into a watch.

I got into Autocad and designed the following "case" (files at the bottom):

<img src="https://hackster.imgix.net/uploads/attachments/767391/autocad_image_dKk7MH4swV.png?auto=compress%2Cformat&w=740&h=555&fit=max">

After that I went to my local Laser Cutting provider and the resulting pieces are these:
<img src="https://hackster.imgix.net/uploads/attachments/779589/image_SPqAlwHGqb.png?auto=compress%2Cformat&w=740&h=555&fit=max">

For the heart rate wearable I want something different from a watch, so I'll re-purpose a sports Wrist wrap with the MAX30100, a little acryllic, a Node MCU ESP8266 board, and a 500 mAH Lipo battery.

<img src="https://hackster.imgix.net/uploads/attachments/782256/20190226_133045_VIgDNAeyxr.jpg?auto=compress%2Cformat&w=740&h=555&fit=max">

Everything will be assembled with a couple screws and some straps and velcro. And some wire.

<img src="https://hackster.imgix.net/uploads/attachments/782258/20190226_231930_rCs6pzfuFC.jpg?auto=compress%2Cformat&w=740&h=555&fit=max">

<img src="https://hackster.imgix.net/uploads/attachments/782259/20190226_232606_AGum87sFNw.jpg?auto=compress%2Cformat&w=740&h=555&fit=max">

NXP's Atmosphere IDE development
Now that we have a base to work from it's time to program everything in the IDE.

If you need help setting up you can follow the following guides on the NXP's Rapid IoT prototyping kit:

https://www.nxp.com/support/developer-resources/rapid-prototyping/nxp-rapid-iot-prototyping-kit:IOT-PROTOTYPING?tab=In-Depth_Tab

Now we can proceed, as previously stated we want to track both Temperature/humidity and Motion in terms of steps.

As of now, there are quite a lot of guides on how to develop your Rapid application but I will include several tips in order to proceed.

The temperature is quite straight forward just allocate this sensor form the list on the right:

<img src="https://hackster.imgix.net/uploads/attachments/780427/image_pm0G0cqQMO.png?auto=compress%2Cformat&w=740&h=555&fit=max">
Get it connected to a function node, an interval node, a BLE GATT node and an Emmbeded icon display node like so:

<img src="https://hackster.imgix.net/uploads/attachments/780428/image_TsYJbeeMti.png?auto=compress%2Cformat&w=740&h=555&fit=max">


<img src="">
<img src="">

<img src="">

<img src="">
<img src="">

<img src="">

<img src="">
<img src="">

<img src="">

<img src="">

To be finished: check the whole proyect at: https://www.hackster.io/Edoliver/health-and-fitness-tracker-753695

