# TIMER_V0
This is the first of many iterations of the engineering design process with the intention of making a timer product from scratch. 
##### Context: 
This idea resulted from the frustration and problem that occurred from not being able to focus on my tasks due to being distracted from my phone. And while perhaps some of you might just propose that I just not use the phone or put it away. 



### Build 
#### Goal: 
Design a timer from scratch

#### Constraint: 
Speed

##### Hardware (links included):

###### Required Items 
If you have Breaboard wires and the ability to solder, then you only need one option from each numbered required from this section.
  1. External DC Audio Speaker 
       1. [continous noise](https://amzn.to/3NEzoDs)
       2. [intermittent noise](Ghttps://amzn.to/3TthQhk)
  2. . Timer Circuit
    1. [Seven Segment Display (Type-C)](https://amzn.to/47bdf6)
    2. [LED Display (Type-C or Micro-Usb)](https://amzn.to/3O03DFd)
  3. Trigger Switch
     1. [Micro Limit Switch (Momentary)](https://amzn.to/488LcWz)
     2. [Push Button (Momentary or latching)](https://amzn.to/3RBcuOw)
##### Optional & Supplementary


#### Step 1: Configure Timer
After gathering of all components, let's go ahead and grab the timer pcb and configure the equipment for a test run. Follow these steps to configure a 10 second timer.

  ##### Powering the circuit
  1. Easiest: Through USB cable 
  2. Easier: DC cable pins (battery-powered or not)

For the sake of just configuring and testing the circuit, we'll go through the easiest way to power the circuit, which is through the usb connectors on the pcb. Depending on what type of circuit you bought, you can grab either a usb-c (or micro usb) cable and connect it to the port. If you decide you don't want to use an external cable and take advatage of the has a WIDE input voltage (6V - 30V) and external source. 

 - Note: If powering externally with battery:  Note: Keep in mind that the source has to have higher current capabilities with minimal flunctuations in as the circuit is used for different applications. For example, a simple 9V battery will most not likely be enough to power the circuit and speaker at time of execution.



#### Step 2: Configuring the Timer


 For this timer and other options similar to this one, there are many different configurations possible. 


Since we just want to set a time prior to the execution of a speaker we will utilize Mode _________  which enables us to set a time(___) prior to powering on the load and a time,____, which will specify the  duration of which the load will go on. If you would like to learn more about the different possible modes please refer to documentation of which you can access via this link.


#### Step 3: Attach Trigger Switch
Next, we need to attach a trigger load in which when pressed, it will initiate the delay prior to the output being held for time (op)


#### Step 4: Attach external Speaker as Load
Now that the trigger works to start the small delay configured for a quick test run, let us attach the speaker to the output pins 

#### Step 4: Test Timer
Once everything has been configured, you should hear a satisfying beep of your circuit once the time delay has counted down to zero for a specified amount of time. I recommend to lower the time the load Will run to minimize noise and Power used during output.
#### Step 5: Attach Supporting Hardware 
Since you need a way to place all components in a secure location, we're going to go ahead and create supporting hardware in which we can organize the components so the connections aren't severed while the timer is supposed to run and we can essentially use it anywhere a USB Port is allowed.
- DIY hardware
- 3D printed

#### Step 1: Configure Timer