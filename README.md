[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]


# TIMER_V0
This is the first of many iterations of the engineering design process with the intention of making a timer product from scratch. 
##### Context: 
This idea resulted from the frustration and problem that occurred from not being able to focus on my tasks due to being distracted from my phone. And while perhaps some of you might just propose that I just not use the phone or put it away. 



## Timer Assembly Guide
###### Goal: Design a timer from scratch

###### Constraint: Speed

### Hardware:
If you have Breaboard wires and the ability to solder, then you only need one option from each numbered required from this section.
###### Required Items (Choose one from each numbered item): 

  
1. **Timer Circuit**
    1. [Seven Segment Display (Type-C)](https://amzn.to/48rKJi9)
    2. [LED Display (Type-C or Micro-Usb)](https://amzn.to/3O03DFd)
  2.  **External DC Audio Speaker** 
       1. [continous noise](https://amzn.to/3NEzoDs)
       2. [intermittent noise](Ghttps://amzn.to/3TthQhk)
  3. **Trigger Switch**
     1. [Micro Limit Switch (Momentary)](https://amzn.to/488LcWz)
     2. [Push Button (Momentary or latching)](https://amzn.to/3RBcuOw)
###### Optional & Supplementary: 
*******[TODO] *******

# INSTRUCTIONS: 
#### Step 1: Configure Timer
After gathering of all components, let's go ahead and grab the timer pcb (Item #1) and configure the equipment for a test run. Follow these steps to configure a 10 second timer.

- **Powering the circuit**
  1. Easiest: Through USB cable 
  2. Easier: DC cable pins (battery-powered or not)
  
    For configuring and testing the circuit, we'll utilize the through the usb connectors on the pcb (**Easiest**) as utilizing pins could be a little too complex for beginners.  
1.  
Depending on what type of timer pcb variation you bought, you can grab either a USB-C or a Micro USB cable and connect it to the port. If you decide you don't want to use an external cable and take advatage of the has a WIDE input voltage (6V - 30V) that you can manually insert into the input pins, feel free to set that up.
  ###### Note: If using an external source, I highly recommend you utilize a DC power source that you can adjust the input voltage before integrating any custom battery sources. This is due to the input requiring higher current capabilities with minimal flunctuations in as the circuit is used for different applications. For example, a simple 9V battery will most not likely be enough to power the circuit and speaker at time of execution.



#### Step 2: Configuring the Timer


 For this timer and other options similar to this one, there are many different configurations possible.
 
 According to the [documentation](): For our Timer applications, P1-P4 will suit any testing and configuration we will require for hardware build. Please see note for  timer pcb variations.
 
 ```Note: For those using the Seven Segment Display Timer PCB variation, The configuration steps follow the exact ordering that the tutorial pcb variation does. For example, P2 will correspond to P1.2 (P3->P1.2, P4->P2) However, please feel free to fact check for understanding and browse at all possible configurations as well.auto```

## Timer PCB Functionality:
Due to the arrangement and numbering of pins across different variations, we will overview the timer PCB Hardware  into 3 main parts: **Power**, **Trigger**, **Relay** 
#### 1. **Power**: 
There are actually 2 ways you can power the circuit: 
   1.  Through the USB Socket Connection Port (**Easy**)
   2. Through pins via DC power source (**Could be Complex**)

  Due to the hundreds of variations and possibilities of powering through option 2, we will stick to powering the circuit via the USB connector to reduce complexity of build. 
> **Note:**
> If there is large interest and request, I will definitely be happy to provide different possibilities and options of powering via pins.

#### 1. **Trigger**:
With the circuit, the timer hardware needs a signal (from outside stimulus) to know that a countdown needs to begin, this is where the trigger comes into play. Due to the versatile logic in the timer circuit, one is able to configure both maintained and momentary switches with any number of poles (SPST, SPDT, DPDT). Here are some different types of buttons you can use:
- Push Button
- Rocker
- Slide


   If you want an explanation on how buttons work, please see this tutorial from Sparkfun

Using positive edges
  For those more experienced in digital logic, you might find the logic not unlike the logic you find in a positive edge-triggered flip-flop (With clk faster than a human can see). Nevertheless, for those without experience, here is a simple diagram to explain how a 
#### Modes P1-P4 Explanation:
  - **P1-P3**: Upon receiving a triggering signal, the all modes turn relay on for an OP time and then turns off. However, there are subtle variations depending on receiving another triggers after the OP time is counting down.
    - **P1**:Subsequent triggering signals during the OP time have no effect.
    - **P2**:Subsequent triggering signals during the OP time reset the timer.
    - **P3**:Subsequent triggering signals during the OP time reset the timer, causing the relay to turn off and stop the timing process.

  -  **P4**: When a triggering signal is received, the relay turns off after a CL time, then turns on for an OP time. Once the timer completes, the relay turns off.

###### 2. Configuring the timer Circuit:
We'll be using the P1-P3 (P1.1,P1.2,P1.3 for Seven Seg variation) for basic test runs and P4 for the final timer application. Here are the directions for changing timer hardware functionality:

- To configure different modes
> 1. Turn Power on
> 2. Hold Set until P* starts blinking
> 3. Use Up and Down buttons to choose mode P1-P4
> 4. Hold Set button until P* stops blinking
   
- Configuring Time Variables (OP, CL, etc...)
> 1. Turn on and ensure mode desired is seen on display (see step above if mode desired is incorrect)
>   2. Hold set until P* starts blinking
>   3. Press set once to configure first variable OP (or CL for those in P4 mode) 
>   4. Use Up and Down buttons to set time 
>      1. If no period is seen (Time is 0-999)
>   5.    

- Testing the Circuit:
  - Testing Mode: P3 (P1.3 for Seven Segment Variation) 
OP Time: 0003 (3 Seconds)
For my test run, we'll be using P3 with OP time "0003" since we want to test for simple execution of one push on our trigger with options to stop the relay during OP countdown in case there are problems with the output connection to our speaker. This will enable fast prototyping and minimal delay or complexity while adding safety measures.
- Running the Circuit (For everyday use):
  - Mode Used: P4 (P2 for Seven Segment Variation)
  - OP Time: 0900 (15 Minutes) 
  - CL Time: 0005 (5 Seconds)
When using the timer in real applications, I wanted to keep my breaks to 15 mins to not allow too long of a gap between work. Thus, the timer was configured for 0900 but feel free to modify based off your goals and needs.

#### Step 3: Attach Trigger Switch 
Next, we need to attach a trigger load in which when pressed, it will initiate the delay prior to the output being held for time (CL) on mode P4 and/or send power to the load that we will attach to the output connections.

You can use different switch options apart from the momentary push button since the timer hardware only turns on the countdowns on the start of a high output trigger. This means, the circuit allows even a latching switch (AKA SPST) to turn the trigger on or off for different durations without accidental triggers. 

##### Hardware Note [TODO: finish afff linkslater]:
Ideally, you don't need any soldering to do this project; however, depending on cost, materials, and/or preference, you might need or just want to solder connections to make sure each button prong has a cable, each connection is tightly secure, and there are no loose wires. 

Let's face it, soldering takes time, especially if you haven't learned the practice, or practiced solder lately. Before you commit or groan from the fact that you might, please take a look at these hardware options that literally remove the need to solder altogether. These prototyping essentials and wiring helpers I keep a part of my prototyping toolkit to remove the need to take annoying and arduous time in testing reducing hours, days, to even week delays in getting a working solution:

Wiring two different wires (No Breadboard, No Soldering, No Splicing required):
1. E-type inline connectors 
2. 1-to-1 inline connectors

Easy, Pain-free triggering and Speaker load Power supply options:
3. Micro-USB Cable splitters (1 Input, 2 Outputs)
4. Power Supply Module (For Trigger, and Speaker Load powering)
5. 9V Battery switch()

Connecting Prongs (No Breadboard, No Soldering, but Splicing Suggested)
1. Spade Connectors 
2. ...






After pulling out the cable or turning power off, you can connect the switch to the timer pcb (momentary push button). I utilized the positive and negative pins (left, bottom two pin connections) enabled by our 5V USB connection and attached one wire into the positive header from the 2 pins on the bottom left terminal connections on the timer hardware and placed to one terminal connection prong of my button hardware. Then, I attached the second prong to the High-level trigger input connection (or the positive trigger on seven segment variation) due to the output being ~5V due to powering from a usb connection. Lastly, I connected the ground terminal from our power supply enabled from the 5V connection to the common ground (middle pin of three). Once connection have been made, pressing the switchs enabled triggering of the relay, as confirmed with clickikng sound and LED notification without the need for an external source of power.



#####Note(TPDP) I the top input of the 5 of three connections)  After connection are secure and intact, I attached both ground  

Additionally,splice the  usb cable and utilize a bread board (or painless E-Type connectors) to allow several pins to access the consistent voltage source coming from  To do this, you can can connect a wire to the positive (indicated with '+' on hardware) terminal via screwdriver and connected the other end of the wire to one end of the momentary push button. 

- Note: If you are using a 3-pin type of connectors as seen in common relay switches, you can attach power to the NO (Normally Open) pin, and attach the common Ground circuit to the positive terminal of the triggering pin on the PCB
- Note #2: For those using external power supply, please keep in mind that your connections will be a little different than the directions above but will still utilize the 


#### Step 4: Attach external Speaker as Load
Now, we are ready to attach the speaker LED to the output of the relay. If you only used a usb connection (as shown in my design) to power the timer pcb, the timer pcb unfortunately does not have the ability to power the 2-pin speaker due to a reduced the amount of current flow from using only the 5V usb connection. 

- Note: Because I did not want to include an extra power source as I didn't want to make the hardware bulky or add too much wiring which could be ripped or cut, I used a two way splitter which 'hacked' the need for a battery or external power for our load as explained in the hardware documentation. There are many many variations of this, so please don't feel limited in having to purchase this item as well. You can use a 9V battery by itself, or attached to power supply and just feed it to the speaker with the wiring described in the following step.

#################finish this step ###########################

#### Step 4: Test Timer
Once everything has been configured, you should hear a satisfying beep of your circuit once the time delay has counted down to zero for a specified amount of time. I recommend to lower the time the load Will run to minimize noise and Power used during output.
#### Step 5: Attach Supporting Hardware 
Since you need a way to place all components in a secure location, we're going to go ahead and create supporting hardware in which we can organize the components so the connections aren't severed while the timer is supposed to run and we can essentially use it anywhere a USB Port is allowed.
- DIY hardware
- 3D printed

#### Step 1: Configure Timer

Attributions:
-------------------

  **Resource #1:**
  - [Button and Switch Basics](https://learn.sparkfun.com/tutorials/button-and-switch-basics/all) © 2013 by Sparkfun Electronics,  (Contributor "JIMBLOM") is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) 
     - Additionally, this guide uses images extracted from tutorial above with  contributor "JIMBLOM" ([Sparkfun-profile](https://www.sparkfun.com/users/69916?_ga=2.172188515.1921033785.1704438252-691382123.1704438252)) embedded in this guide.
 

License Information
-------------------

This product is _**open source**_! 

Please use, reuse, and modify these files as you see fit. Please maintain attribution to "Robjects" and release any derivative under the same license.



##### License 
This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg


