[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]


# TIMER_V0
-------------------

This is the first of many iterations of the engineering design process with the intention of making a timer product from scratch. 
##### Context: 
This idea resulted from the frustration and problem that occurred from not being able to focus on my tasks due to being distracted from my phone. And while perhaps some of you might just propose that I just not use the phone or put it away. 



## Timer Assembly Guide
-------------------
### Objectives:
-------------------

###### Goal: Design a timer from scratch

###### Constraint: Speed

### Supplies:
-------------------

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

### Timer Build Assembly Guide
-------------------


Let's go ahead and overview the timer PCB Hardware by breaking it down into 5 main parts: **Power**, **Trigger**, **Relay** 
#### 1. Powering the circuit: 
-------------------

According to the manual for our micro-usb timer hardware,there are 2 main ways that you can power the circuit: 
   1.  Through the USB Socket Connection Port (**Easy**)
   2. Through pins via DC power source (**Could be Complex**)
   
For the majority of this tutorial, we will stick to powering the circuit via the USB C socket connector to reduce complexity, cost and unecessary steps to fit with the speed constraint in the YouTube Video. 



Depending on what type of timer pcb variation you bought, you can grab either a USB-C or a Micro USB cable and connect it to the socket. 

> **Note:**
> For those planning to power the timer externally via external source, I **highly recommend** you to **read the documentation** closely and plan out all wire connections as configuration changes if you plan to use an external battery. Before getting any hardware for my first iteration, I still made costly mistakes that could have been avoided with careful reading.
> Take for instance a **9V DC Battery**: Although being in the input voltage range (**6-30V**) as seen in the [Timer Hardware Manual](/docs/TimerHardwareManual-MicroUSB.pdf), the power source will likely not turn on or worse, run out very quickly even if you manage to power the circuit. This is due to its low-current and sporadic flunctuations in current as the relay is turned on and off while in use. 

#### 2. Setting Timer Mode Instructions:
-------------------

Now that we have power to our pcb, let's go ahead and configure the timer pcb ([Item #1](https://amzn.to/48rKJi9)) for a test run.

Here are the directions needed for changing timer hardware functionality:

_For those using alternative timer hardware, please see note below for corresponding modes:_
> **Note**: For those using the Seven Segment Display Timer PCB variation, The configuration steps follow the exact ordering that the tutorial pcb variation does. For example, P2 will correspond to P1.2 (P3->P1.2, P4->P2) However, please feel free to fact check for understanding and browse at all possible configurations as well
> 
- **Modes P1-P4 Explanation**:
  - **P1-P3**: Upon receiving a triggering signal, modes P1-P3 all turn the relay on for a duration of pre-configured "OP" time until it turns off when the countdown hits zero. However, the sublety lies on what happens if a trigger is registered before the countdown "OP" hits zero.
    - **P1**:Subsequent triggering signals during the OP time have no effect.
    - **P2**:Subsequent triggering signals during the OP time reset the timer.
    - **P3**:Subsequent triggering signals during the OP time reset the timer, causing the relay to turn off and stop the timing process.

  -  **P4**: Mode P4 begins exactly as its predecessor with one extra pre-selected variable "CL" added. "CL" determines exactly how long the relay will be on, or "closed time" if you will. Which, if you plan to use in close-proximity with the dc audio speaker, you want to set to quick as the speaker can be an earful during timed breaks if you don't decide to muffle it.

- **To configure different modes (P1-P7)**
> 1. Turn Power on
> 2. Hold Set until P* starts blinking
> 3. Use Up and Down buttons to choose mode P1-P4
> 4. Hold Set button until P* stops blinking
   
 > 

- **Configuring Time Variables (OP, CL, etc...)**
> 1. Turn on and ensure mode desired is seen on display (see step above if mode desired is incorrect)
>   2. Hold set until P* starts blinking
>   3. Press set once to configure first variable OP (or CL for those in P4 mode) 
>   4. Use Up and Down buttons to set time 
>      1. If no period is seen (Time is 0-999)
>   5.  

- **Modes Utilized for timer build**:
We'll be using the P1-P3 (P1.1,P1.2,P1.3 on USB-C variation) for basic test runs and P4 (P2 on USB-C) after we finish all testing and are ready to finalize the prototype.
  - **Testing the Circuit:**
    - Test Mode: P3 (P1.3 for Seven Segment Variation) 
OP Time: 0003 (3 Seconds)
For my test run, we'll be using P3 with OP time "0003" since we want to test for simple execution of one push on our trigger with options to stop the relay during OP countdown in case there are problems with the output connection to our speaker. This will enable fast prototyping and minimal delay or complexity while adding safety measures.
- **Running the Circuit (For everyday use)**:
  - Mode Used: P4 (P2 for Seven Segment Variation)
  - OP Time: 0900 (15 Minutes) 
  - CL Time: 0005 (5 Seconds)
When using the timer in real applications, I wanted to keep my breaks to 15 mins to not allow too long of a gap between work. Thus, the timer was configured for 0900 but feel free to modify based off your goals and needs.


#### 3. Trigger Signal:
-------------------
 Next, we need to attach a trigger load in which when pressed, it will initiate the delay prior to the output being held for time (CL) on mode P4 and/or send power to the load that we will attach to the output connections. But before we start connecting pins and wires, let's overview how the trigger works with the micro-usb timer hardware.

With this variation of timer, there are two inputs that the circuit will recognize.


_`[show trigger diagram here]`_

1. High-level Trigger (3.0V-24.0V):
  the trigger is acknowledge at the rising edge meaning that both momentary and maintained (in off position) switches will turn on the circuit when you first press the button changing the trigger to the on position. With maintained switches, the circuit will not acknowledge the trigger until the next rising edge meaning you can keep it in the on position for as long as you like. 
  _`[show trigger diagram here]`_

1. Low-level Trigger (0V-0.2V): Similar to High-level trigger but voltage is high in the off position. For our specific timer usage, I do not recommend this method to those expecting to use the circuit in the medium to long run, especially when testing a prototype. This is due to the continuous presence of voltage at one of the terminals of the button. Over time, there will be voltage drops which could eventually fall in the low-level trigger range if circuit is running long-term.. Additionally, the posibility of accidental triggering is also much higher due to the possibility accidental stripping, tears, or breaks in the connections from moving the prototype which would be entirely avoided if a high-level trigger is utilized. 


Ultimately, the high-level trigger is ideal, as we can easily tie an external dc battery source with a toggle switch seperate from main power. This will incredibly increase the life-span of the battery, decrease material cost, and provide efficient modularity in case we want to upgrade, replace, or change the trigger source without reassembling the entire circuit. This is timer VERSION #0, and there is still much more to come so having organized and seperate parts Makes it incredibly easier to make on the spot changes which will increase my productivity and speed, even more in the long run.


_`[show timing diagram here with flip flop included]`_

  [diagram of flip flop vs diagram of imagined timer hardware timing diagram or animation]
  For educated Electrical Engineers like myself, your brain might be screaming (or cringing :P) "flip-flops! AHHHH!" or some other familiar Digital electronic synchronization circuit. 
  
  There are some differences of course to those pesky edge-triggered flippy flops. however, in real-time, "are they really even there...?" I mean, if flip-flop clocks fall so fast, are they really there?"

 


You can use different switch options apart from the momentary push button since the timer hardware only turns on the countdowns on the start of a high output trigger. This means, the circuit allows even a latching switch (AKA SPST) to turn the trigger on or off for different durations without accidental triggers. 

#### 4. Relay Overview:
In the timer hardware, our rela follows a standard configuration that is seen across all types of relays, with or without delay, potentials.

##### Relay functionality:


  You typically have three pins to set up with this standard: NC, COM/C, NO.

  When a momentary switch is not actuated, it’s in a “normal” state. Depending on how the button is constructed, its normal state can be either an open circuit or a short circuit.

  1. Normally Open (NO): This means that the circuit itself is broken in a normal state and is only a closed loop when the switch/button is pressed. it is not actuated meaning there is no current
  2. Normally Closed (NC): and the other hand, if the button is closed, unless it is actuated, it is considered a normally closed switch, where a press of the button will break the circuit, creating an open circuit
  3. Common Ground (C/COM): When attaching a button, common ground is the first terminal of the relay where you want to connect the first part of your circuit to. When the relay is off the normally closed (NC) and the Common Ground (C/COM) have continuity. conversely, when the relays turned on the normally open(NO) and the common ground (C/COM) have continuity. based off these principles, buttons are wired to one of the terminals NC or NO depending on use case. 

##### Relay Hardware Assembly:

for the reasons mentioned in the trigger, we will utilize the normally open and common ground  terminals on the PCB. This is due to the fact that we want an output to be created at the end of the countdown. this means that anytime  before the powering of the relay, the loop will be open. 

Note: Ideally, we should be able to use the PCB power supplied from microusb cable from the input bottom left 2 pins (shown as 5V on multimeter)

[show image]

 to configure relay pins NO and COM and the 2 wires from the audio speaker. I mean a microcontroller can power this speaker with a 3.3V output pin... it would make sense or so I thought...



But to my dissapointment, after frantically Losing my mind on why a 5V powered (with 3A!) couldn't make a Silly little audio speaker wail as load as sirens from a single 3.3V microcontroller pin, I took Another look at the manual provided in the box.

 After reading the world, smallest and finest of print, turns out that when powering the timer pcb with a micro USB cable, the 2 input pins on the bottom left corner provide a laughable 15 mA current.

 I was destroyed... I was humiliated... And I was bamboozled.

 Till that point, everything was flowing, smoothly, efficiently, ridiculously well in the path to rapid prototyping.up until that point, I was ready to tell Elon he had nothing on me.

 Disappointment turned to sadness to anger and frustration for a good three hours. and knowing myself, if I didn't make a move or try to do something, anything... All these years, all these unfinished projects were flashing through my thoughts at once. I was going to admit defeat. 


But maybe I'm tired of piles of unfinished projects that I give up on in the Time where my effort would most pay off if I stayed just a little bit longer. So... With those boiling inside of me.  I managed to Convert some of deep, deep sadness to engineering RAGE.
 

   An for those that, don't know about the rage, the engineering rage that comes from deep nerdy impulsivity. 
   
   Be aware. It's the real deal, yo.

    So through my engineering impulsivity, I decided to forget everything that I knew was true about electronics.

    I grabbed a pair of water strippers ad went nuts on every micro USB cable that dared be in my vicinity.
 ========================stopped making sense here =======


~~As I cut the fifth micro USB cable, and took a look at all these different types of wires and connectors on the ground,~~ After perpetual cycles of emotional damage, I finally decided to make a move and risk it all. 

I was going to make a **node** By the end of the night. No matter what it takes or how it looks.




 My first idea was to make a note someway somehow with wires, I knew several different options, but Nothing I imagined Would be  Elegant enough to associate with my beautiful first project. 
 
 
Nevertheless, since I was too tired to think, and I refuse to not hear my speaker whale at me, I decided to start cutting wires.
My intention was to hack and remove the need to hae an external power source for  a tiny speaker that can be powered by a microcontroller. the manual stated that I needed a 220 VAC power source to utilize and get my relay to work. Heck no.

Other options could include:
1. Taping both wires after twisting them.
2.  Using a spade connector and using hot air to solder them together
3.    using a soldering iron to make a blob of a connection between two micro USB cables.
4.    Finding a bread prototype that has connecting notes and  solder them together.


 I knew I could do better...

  And then I remembered. while ago, I bought a one input, two outputs, split micro USB cable that allowed you to utilize and transfer data with two different devices while being concurrently connected.my mind screamed a mixure of no and f you since I knew I would have to sacrifice one output and strip it in order to attach it to the screw terminals of the PCP..


Fortune favors the brave, right...?  
  
  
And although I am not particularly bad at soldering,I justified the microusb sacrifice by reasoning that I had a higher chance of burning my house down through soldering 
  Then, being shocked from the weenie little current, that that timer PCP neglected to mention. I made sure not to provide that one as an affiliate link in case you wanted to do something similar 



So with  illusion of a imaginary nearing finish line that did not exist. I attacked my electronic micro usb cables with the fire of 1000 suns. You see, I was determinator, and the junction node was my Sarah Conner. This is what came out of it.

  wasn't planning on  creating any 3-D prints I know all too well how much time it can add to a project you aren't, especially careful with constraints, so I grabbed the ugliest box in my vicinity and shoved all my separate components. Are there which ultimately Made my project look like it was made by a second grader.
its soul. 


    In Hindsight, I can't tell you if it was worth it, or not.  I found such a simplistic, elegant and beautiful alternative in record time. Which, after sticking it in the ugliest box, it looked like a second grader could do a better job.

     but it's all love here, nspiring others to be creative and build new and crazy technologies at whatever income, cultural background is what it is all about. 



 oh, and if you want to never struggle the way I did,here is a solution that would've saved me a day  in engineering ra
[llink to junction]
 thanks for sticking around!
=========================stopped here========
     [addddd outro here]

##### Hardware Notes [TODO: finish afff linkslater]:
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

### Attributions:
-------------------

  **Resource #1:**
  - [Button and Switch Basics](https://learn.sparkfun.com/tutorials/button-and-switch-basics/all) © 2013 by Sparkfun Electronics,  (Contributor "JIMBLOM") is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) 
     - Additionally, this guide uses images and text extracted from tutorial above with  contributor "JIMBLOM" ([Sparkfun-profile](https://www.sparkfun.com/users/69916?_ga=2.172188515.1921033785.1704438252-691382123.1704438252)) embedded in this guide.
 

### License Information
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


