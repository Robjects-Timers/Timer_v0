[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa] [![Run TODO to Issue](https://github.com/Robjects-Timers/Timer_v0/actions/workflows/todo-to-issue.yml/badge.svg?branch=master)](https://github.com/Robjects-Timers/Timer_v0/actions/workflows/todo-to-issue.yml)

# TIMER_V0


<!--[TODO: add finished product image]-->
This is the first of many iterations of the engineering design process with the intention of making a timer product from scratch.

##### Context: 
This idea resulted from the frustration and problem that occurred from not being able to focus on my tasks due to being distracted from my phone. And while perhaps some of you might just be able to leave your phone with effortless determination, I rather procastinate with and replace a bad habit with a less worse habit. If you find my projects interesting and useful, please consider donating or supporting my [YouTube Channel]() to fund the completely free, open-source projects intended for the community!


# Overview


<!-- [TODO: add product image] -->This is the first of many iterations of the engineering design process with the intention of making a timer product from scratch.

# Table of Contents

- [TIMER\_V0](#timer_v0)
        - [Context:](#context)
- [Overview](#overview)
- [Table of Contents](#table-of-contents)
  - [Context](#context-1)
  - [Specific Problem to Solve](#specific-problem-to-solve)
  - [Solutions](#solutions)
  - [Timer Assembly Guide](#timer-assembly-guide)
    - [Objectives](#objectives)
    - [Supplies](#supplies)
      - [Required Items (Choose one from each numbered item)](#required-items-choose-one-from-each-numbered-item)
      - [Optional \& Supplementary](#optional--supplementary)
    - [Timer Build Assembly Guide](#timer-build-assembly-guide)
      - [Step 1. Powering the circuit](#step-1-powering-the-circuit)
      - [Step 2. Setting Timer Mode Instructions](#step-2-setting-timer-mode-instructions)
      - [Step 3. Trigger Signal](#step-3-trigger-signal)
      - [Step 4. Relay Overview](#step-4-relay-overview)
      - [Step 5: Attach external Speaker as Load](#step-5-attach-external-speaker-as-load)
      - [Step 6: Test Timer](#step-6-test-timer)
      - [Step 7: Attach Supporting Hardware (Optional)](#step-7-attach-supporting-hardware-optional)
    - [Attributions](#attributions)
    - [License Information](#license-information)
      - [License](#license)

## Context

This idea resulted from the frustration and problem that occurred from not being able to focus on my tasks due to being distracted from my phone. And while perhaps some of you may just be able to, very admirably, leave your phone with relentless determination, and move on to your long-term goals as effortless as it was to do the other habit.
That being said, we have to be both wise and smart and reduce the amount of mental friction we intend to have to partake; otherwise, I don’t stand a chance changing my behavior and might end up worse than I started from the depression of failure. Due to this, I will work on replacing the worst habit of checking my phone and ‘less worse’ habit such as working on these engineering projects so that either way, I am procrastinating, but I am still inside the mental (and physical) environment that my day-to-day career tasks which might end up indirectly improving my productivity.

## Specific Problem to Solve

Essentially, I want to eliminate the justification of using my phone for time related apps such as timer, stopwatch, clock, alarm, etc.?

Objectively, this problem is arguably nonexistent if you use only the productive apps for its intended purpose while trying to focus on your long-term goals without distractions.

But really… You do that 100% of time? Really bro...? (props if you honestly do though!)

## Solutions

I will be creating several iterations of full hardware/software prototypes that use different hardware/software every iteration. The hope is to incrementally increase complexity of builds that stick to specified criteria common for creating tech solutions.

```

  "why don't you just buy a cheap clock, you goon? Arrr ya dumb or something...?" - online troll somewhere

  My response: Yes... you can solve this problem simply with a quick purchase of a timer, stopwatch from a 1 minute search on Amazon. However, that won't really solve the problem at hand and create a alternative procrastination habit useful for my career goals. Also, where's the fun in buying a solution that won't impact you at your very core increasing the probability of success in defeating your bad habit...? 
  And, where else can you flex your engineering skills from all different fields of engineering, and have a chance to showcase to my fellow engineering community that can laugh or implement their own projects incrementally improving your life in the best way? 

```

 I'll be constantly working on different projects apart from these iterations. If you find my projects interesting and useful, check out my [YouTube Channel]() where I post videos of completed builds (projected 2025) of which showcase the free, open-source projects intended for the community! Please consider donating to my [Patreon](patreon.com/MrMikeyMarks) and  the financial oblior subscribing to 



## Timer Assembly Guide

-------------------
<!-- [TODO: add overhead project img here] -->


### Objectives

-------------------

- **Goal:** Design a timer from scratch in minimal time
- **Constraint**: Speed
- **Pros & Cons of Build**
| Pros                                                                                                | Cons                                            |
| --------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| No Volume adjustment available                                                                      | No coding in build (+ increased speed)          |
| Power through USB requires additional power source (or hardware hack alternative featured in guide) | No 3D Printed Enclosure (+ increased speed)     |
| Manual Configuration required for changing countdown can be tedious                                 | No Soldering used (+ increased speed)           |
| Limited options provided from timer hardware selected                                               | No Breadboard used (+ increased speed)          |
| ---                                                                                                 | Minimal focus on aesthetics (+ increased speed) |
| ---                                                                                                 | Timer hardware allows powering via micro-usb    |
| ---                                                                                                 | Display for seeing countdown progress.          |
| ---                                                                                                 | Low cost for full build (under $20 dollars)     |

### Supplies

-------------------

<!-- [TODO:image of all supplies with label] -->

If you have Breadboard wires and the ability to solder, then you only need one option from each numbered required from this section.

#### Required Items (Choose one from each numbered item)

1. **Timer Circuit** <!-- [TODO: add side by side comparison] -->
    1. [Seven Segment Display (Type-C)](https://amzn.to/48rKJi9)
    2. [LED Display (Type-C or Micro-Usb)](https://amzn.to/3O03DFd)
2. **External DC Audio Speaker** <!-- [TODO: add side by side comparison] -->
    1. [continous noise](https://amzn.to/3NEzoDs)
    2. [intermittent noise](https://amzn.to/3TthQhk)
3. **Trigger Switch** <!-- [TODO: add side by side comparison] -->
    1. [Micro Limit Switch (Momentary)](https://amzn.to/488LcWz)
    2. [Push Button (Momentary or latching)](https://amzn.to/3RBcuOw)

#### Optional & Supplementary

### Timer Build Assembly Guide

-------------------

Let’s go ahead and overview the timer PCB Hardware by breaking it down into 5 main parts: **Power**, **Trigger**, **Relay**

#### Step 1. Powering the circuit

-------------------

According to the manual for our micro-usb timer hardware,there are 2 main ways that you can power the circuit:

   1. Through the USB Socket Connection Port (**Easy**)
   2. Through pins via DC power source (**Could be Complex**)

For the majority of this tutorial, we will stick to powering the circuit via the USB C socket connector to reduce complexity, cost and unecessary steps to fit with the speed constraint in the YouTube Video.

Depending on what type of timer pcb variation you bought, you can grab either a USB-C or a Micro USB cable and connect it to the socket.

> **Note:**
> For those planning to power the timer externally via external source, I **highly recommend** you to **read the documentation** closely and plan out all wire connections as configuration changes if you plan to use an external battery. Before getting any hardware for my first iteration, I still made costly mistakes that could have been avoided with careful reading.
> Take for instance a **9V DC Battery**: Although being in the input voltage range (**6-30V**) as seen in the [Timer Hardware Manual](/docs/TimerHardwareManual-MicroUSB.pdf), the power source will likely not turn on or worse, run out very quickly even if you manage to power the circuit. This is due to its low-current and sporadic flunctuations in current as the relay is turned on and off while in use.

#### Step 2. Setting Timer Mode Instructions

-------------------

Now that we have power to our pcb, let’s go ahead and configure the timer pcb ([Item #1](https://amzn.to/48rKJi9)) for a test run.

Here are the directions needed for changing timer hardware functionality:

_For those using alternative timer hardware, please see note below for corresponding modes:_
> **Note**: For those using the Seven Segment Display Timer PCB variation, The configuration steps follow the exact ordering that the tutorial pcb variation does. For example, P2 will correspond to P1.2 (P3->P1.2, P4->P2) However, please feel free to fact check for understanding and browse at all possible configurations as well
>
- **Modes P1-P4 Explanation**:
  - **P1-P3**: Upon receiving a triggering signal, modes P1-P3 all turn the relay on for a duration of pre-configured “OP” time until it turns off when the countdown hits zero. However, the sublety lies on what happens if a trigger is registered before the countdown “OP” hits zero.
    - **P1**:Subsequent triggering signals during the OP time have no effect.
    - **P2**:Subsequent triggering signals during the OP time reset the timer.
    - **P3**:Subsequent triggering signals during the OP time reset the timer, causing the relay to turn off and stop the timing process.

  - **P4**: Mode P4 begins exactly as its predecessor with one extra pre-selected variable “CL” added. “CL” determines exactly how long the relay will be on, or “closed time” if you will. Which, if you plan to use in close-proximity with the dc audio speaker, you want to set to quick as the speaker can be an earful during timed breaks if you don’t decide to muffle it.

- **To configure different modes (P1-P7)**
>
> 1. Turn Power on
> 2. Hold Set until P* starts blinking
> 3. Use Up and Down buttons to choose mode P1-P4
> 4. Hold Set button until P* stops blinking
 >

- **Configuring Time Variables (OP, CL, etc…)**
>
> 1. Turn on and ensure mode desired is seen on display (see step above if mode desired is incorrect)
> 2. Hold set until P* starts blinking
> 3. Press set once to configure first variable OP (or CL for those in P4 mode)
> 4. Use Up and Down buttons to set time
>      1. If no period is seen (Time is 0-999)
> 5.  

- **Modes Utilized for timer build**:
We’ll be using the P1-P3 (P1.1,P1.2,P1.3 on USB-C variation) for basic test runs and P4 (P2 on USB-C) after we finish all testing and are ready to finalize the prototype.
  - **Testing the Circuit:**
    - Test Mode: P3 (P1.3 for Seven Segment Variation)
OP Time: 0003 (3 Seconds)
For my test run, we’ll be using P3 with OP time “0003” since we want to test for simple execution of one push on our trigger with options to stop the relay during OP countdown in case there are problems with the output connection to our speaker. This will enable fast prototyping and minimal delay or complexity while adding safety measures.
- **Running the Circuit (For everyday use)**:
  - Mode Used: P4 (P2 for Seven Segment Variation)
  - OP Time: 0900 (15 Minutes)
  - CL Time: 0005 (5 Seconds)
When using the timer in real applications, I wanted to keep my breaks to 15 mins to not allow too long of a gap between work. Thus, the timer was configured for 0900 but feel free to modify based off your goals and needs.

#### Step 3. Trigger Signal

-------------------
 Next, we need to attach a trigger load in which when pressed, it will initiate the delay prior to the output being held for time (CL) on mode P4 and/or send power to the load that we will attach to the output connections. But before we start connecting pins and wires, let’s overview how the trigger works with the micro-usb timer hardware.

With this variation of timer, there are two inputs that the circuit will recognize.

  1. **High-level Trigger (3.0V-24.0V)**:

    _`[show trigger diagram here]`_

    the trigger is acknowledge at the rising edge meaning that both momentary and maintained (in off position) switches will turn on the circuit when you first press the button changing the trigger to the on position. With maintained switches, the circuit will not acknowledge the trigger until the next rising edge meaning you can keep it in the on or off position for as long as you like and the relay will only trigger on the up signal of a voltage spike in the 3.0-24 voltage range. 
    _`[show trigger diagram here]`_

  2. **Low-level Trigger (0V-0.2V)**: Similar to High-level trigger but voltage is high in the off position (or very low voltage). This means, that you can tie a battery to the terminals and have the relay start when you disconnect the pins or turn the source off via switch.

    For our specific timer usage, I do not recommend this method to those expecting to use the circuit in the medium to long run, especially when testing a prototype. This is due to the continuous presence of voltage at one of the terminals of the button. Over time, there will be voltage drops which could eventually fall in the low-level trigger range if circuit is running long-term.. Additionally, the posibility of accidental triggering is also much higher due to the possibility accidental stripping, tears, or breaks in the connections from moving the prototype which would be entirely avoided if a high-level trigger is utilized. 

Ultimately, the high-level trigger is ideal, as we can easily tie an external dc battery source with a toggle switch seperate from main power. This will incredibly increase the life-span of the battery, decrease material cost, and provide efficient modularity in case we want to upgrade, replace, or change the trigger source without reassembling the entire circuit. This is timer VERSION #0, and there is still much more to come so having organized and seperate parts Makes it incredibly easier to make on the spot changes which will increase my productivity and speed, even more in the long run.

> - **Extra Note**:
> _`[show timing diagram here with flip flop included]`_
>
>   [diagram of flip flop vs diagram of imagined timer hardware timing diagram or animation]
>   For educated Electrical Engineers like myself, your brain might be screaming (or cringing :P) “flip-flops! AHHHH!” or some other familiar Digital electronic synchronization circuit.
>
>   There are some differences of course to those pesky edge-triggered flippy flops. however, in real-time, “are they really even there…?” I mean, if flip-flop clocks fall so fast, are they really there?”

#### Step 4. Relay Overview

In the timer hardware, our relay follows a standard configuration that is seen across all types of relays, with or without delay, potentials.

- Relay Pin Definitions:

  When a momentary switch/relay is not actuated, it’s in a “normal” state. Depending on how the button is constructed, its normal state can be either an open circuit or a short circuit. Futhermore, This configuration is typical standard that you might see association with switches, relays, and programmable logic controllers (PLCs). So it makes sense that the relay that our timer hardware follows this approach, characterized with by standard 3 pins naming convention NO, COM/C, and NC explained below:

  1. Normally Open (NO): This means that the circuit itself is broken in a normal state and is only a closed loop when the switch/button is pressed. it is not actuated meaning there is no current
  2. Normally Closed (NC): and the other hand, if the button is closed, unless it is actuated, it is considered a normally closed switch, where a press of the button will break the circuit, creating an open circuit
  3. Common Ground (C/COM): When attaching a button, common ground is the first terminal of the relay where you want to connect the first part of your circuit to. When the relay is off the normally closed (NC) and the Common Ground (C/COM) have continuity. conversely, when the relays turned on the normally open(NO) and the common ground (C/COM) have continuity. based off these principles, buttons are wired to one of the terminals NC or NO depending on use case.

- **Relay Hardware Assembly**:

for the reasons mentioned in the trigger, we will utilize the normally open and common ground  terminals on the PCB. This is due to the fact that we want an output to be created at the end of the countdown. this means that anytime  before the powering of the relay, the loop will be open.

Note: Ideally, we should be able to use the PCB power supplied from microusb cable from the input bottom left 2 pins (shown as 5V on multimeter) to configure relay pins NO and COM and the 2 wires from the audio speaker as seen in image gelow:

 [show image]

  I mean a microcontroller can power this speaker with a 3.3V output pin… it would make sense or so I thought…

But to our dissapointment, the manual shows (in the smallest of prints if I may add) that when powering the timer pcb **with a micro USB cable**, the 2 input pins on the bottom left corner output a 5V voltage with 15 mA which unfortunately doesn’t reach a high enough current. For instance, the speaker, although can work with currents as low as 15mA, requires a voltage of at least 12V for it to work with that current output according to the specifications.

So unfortunately, we were going to have to come up with a differenet alternative. So, going back to brainstorming, we need a solution that effectively adds more power to the speaker to enable it to power on as countdown stops. Or, we need to completely reframe the notification system entirely and redefine what is needed to know when a timer is done based on intended use case/purpose of a prototype. Here are some options that could work, and should be quick to do if planned correctly:

1. adding additional battery to allow the relay to create notification when turned on
2. split 5V input (from cable wire) in parallel to allow one source for both hardware and speaker
3. find a speaker that works with combination of 5V/15mA
4. change notification system from to LED which still has small noise made when relay is turned on.

 > **Note**:
  > Although speed is the essence, we still need to be going through some sort of logical process before resorting to quick, hasty actions that sneakily seem like the easiest path for solving the problem at hand. Part of becoming a efficient and productive engineer is learning when to hesitate, take a break from building, realign yourself with any new problems or information presented, and jump back to arranging the best steps forward.
  > The engineering design process is not always sequential or perfect, even if you ‘perfectly’ planned every step along the way. Sometimes, the most productive action you can make is restraint, although it might not seem in the moment.
  > Realigning yourself with the updated problem at hand ensures you don’t follow ‘rabbit holes’ of a sequential process and turn 5 minute solutions into 5 hour mistakes which will yield better result in the long run.
  > For further information which might help you in learning from my time-wasting mistakes, feel free to see “Mistakes I wish I understood before developing” section in [“Acknowledgements.md”](Acknowledgements.md).

before deciding on, seems like the easiest choice, let’s go ahead and use some sort of logical reasoning  to decide which approach to tackle. reigning ourselves with our speed constraint, we need something to be the quickest so this easily removes option #3 as we would too long (in product search and shipping) for our new package which on top of the additional money of finding another speaker.  before resorting to this option, let’s make sure we cannot solve it with an easier and much more cheaper solution. So, considering option four, we would have to essentially align ourselves with the purpose of the project, or in this case prototype.
  
   The overall purpose is to create a timer in which we can input a delay and allow the timer to countdown which ultimately turns on a relay at the end of the countdown. That being said, we have the first steps of that process covered, which are Starting the timer and triggering the countdown of a specific pre-selected time. so now, all that is missing is turning on the relay, which is currently not working.  so let’s go ahead and reframe the problem and isolate the what/where/when/why/details of fixing this in our prototype.

   1. what:  First, let’s discuss the basic necessities. We need some sort of notification to signify that. The countdown of the timer hardware is finished.
   2. how: currently, the notification system is set to use sound (via powered speaker). realistically for my prototype and use case needs, having other notification systems is possible.
   3. when: I intend to use the prototype when I require breaks. Typically these brakes would be used in the middle of the day, or at the after the last Session of work typically requires full attention.
   4. why: The brakes are solely needed to detach myself from screens and have a chance to relax/meditate as I transition to another session of work or other daily activity. I typically want to stay away from having to use my phone as it’s not a great activity to do as my brain would just consider this another stimulating activity.
   5. where: I imagine most of the brakes that I take will be in my room or area apart from my office so it most likely will require minimal movement of location.

Taking all of these into consideration, I narrow it down to two different options: #4 and #2.
So considering that I will use this notification system mainly during breaks, not meant for screen time, perhaps it would be best to Remove a somewhat loud alarm that might jolt me, and subtract from the benefit from the low stress environment. Additionally, the relay itself when it starts does have a small noise in which can be heard if the device is  in proximity. This, in combination with an LED type, notification would be incredibly valuable as I imagine I could wake up from a qquick nap and realize if the break is over or not without  inducing, negative stress.

 Next we have option number two, which ultimately still uses the speaker, but doesn’t involve utilizing an extra battery which would cost materials, size, and Project clutter (as suggestted in #1). Instead,  we can create a creative solution that splits the USB power source prior to the attachment  into the hardware, which would ultimately split the power source in parallel with one pathway still being the the input of the timer (with microusb male headers) requiring minimum of 50 mA and the other pathway powering the speaker PCB (in Normally Open configuration) only when the relay is turned on. This means after accounting how much current is needed (estimateed from speaker’s 12V/15mA specification), the estimated (650mA current required when relay turns on would allow concurrent power to both the timer and speaker.
  been load to the speaker attached to.

 let’s first attempt option #4  as this keeps intended speaker in the solution without having to configure additional components which require manual hardwiring which reduces intended modularization of hardwareAs we need to manually hardwire some components and ensure notification system will suffice.

> Ideally, you don’t need any soldering to do this project; however, depending on cost, materials, and/or preference, you might want/need to solder or use additional hardware to make sure each seperate electronic in the overall build has the ability to connect to the designated termianal, and that each connection is tightly secure, and there are no loose wires. Last thing you want prior to creating your first prototype is your circuit to start disconnecting pins due to loose and flimsy wires that couldn’t have been avoided with better hardware configuration tools. .I’ll be thinking the hardware as I explained the guide, but feel free to click here to see the full list.

 Using [’Type-E Lever Wire Connectors”](https://amzn.to/3NW4eHX) with a Y splitter that splits one input into 2 options such as a [microusb (Micro micro to dual male micro headers) type](https://amzn.to/3NUKOmL) or a [or a USB (1 Male input, 2 USB Female](https://amzn.to/41XZaIH) to allow split on cheap wire instead of splicing the product, you can allow one end for the hardware and another for the speaker as shown below

 [image of speaker with usb]

For those that don’t want or have much use in the extra components,  you could just as easily manually splice your own wires following the splicing configuration ([seen here](https://amzn.to/3tC23Ct)). Choose one 2 wires you are okay with splicing and configure both methods shown in product: one for connecting the header to the timer and another for connecting pins to the speaker circuit. For joining the nodes, feel free to be creative with the electronic hardware you have as there are many alternatives in connecting 2 junctions to the same node (i.e., breadboard, spade connectors, and/or soldering iron, hot-air gun with covers), please do not feel forced to buy products you will only use once.

After pulling out the cable or turning power off, you can connect the switch to the timer pcb (momentary push button). I utilized the positive and negative pins (left, bottom two pin connections) enabled by our 5V USB connection (seen below):

Then, attached one wire into the positive header from the 2 pins on the bottom left terminal connections on the timer hardware and placed to one terminal connection prong of my button hardware. , I attached the second prong to the High-level trigger input connection (or the positive trigger on seven segment variation) due to the output being ~5V due to powering from a usb connection. Lastly, I connected the ground terminal from our power supply enabled from the 5V connection to the common ground (middle pin of three). Once connection have been made, pressing the switchs enabled triggering of the relay, as confirmed with clickikng sound and LED notification without the need for an external source of power.

See below for configuration after all steps are done.

- **Tools that drastically reduce connecting wires (with links):**
Using these shortcut will definitely save you in time on effort used, **especially** if you constanting like working with electronics.
Wiring two different wires (No Breadboard, No Soldering, No Splicing required):

1. E-type inline connectors
2. 1-to-1 inline connectors

Easy, Pain-free triggering and Speaker load Power supply options:
3. Micro-USB Cable splitters (1 Input, 2 Outputs)
4. Power Supply Module (For Trigger, and Speaker Load powering)
5. 9V Battery switch()

Connecting Prongs (No Breadboard, No Soldering, but Splicing Suggested)

1. Spade Connectors
2. …

#### Step 5: Attach external Speaker as Load

Now, we are ready to attach the speaker to the output of the relay. If you only used a usb connection (as shown in my design) to power the timer pcb, the timer pcb unfortunately does not have the ability to power the 2-pin speaker due to a reduced the amount of current flow from using only the 5V usb connection.

- Note: Because I did not want to include an extra power source as I didn’t want to make the hardware bulky or add too much wiring which could be ripped or cut, I used a two way splitter which ‘hacked’ the need for a battery or external power for our load as explained in the hardware documentation. There are many many variations of this, so please don’t feel limited in having to purchase this item as well. You can use a 9V battery by itself, or attached to power supply and just feed it to the speaker with the wiring described in the following step.

- Note: If you are using a 3-pin type of connectors as seen in common relay switches, you can attach power to the NO (Normally Open) pin, and attach the common Ground circuit to the positive terminal of the triggering pin on the PCB
- Note #2: For those using external power supply, please keep in mind that your connections will be a little different than the directions above but will still utilize the

~~Next, we wi Note(TPDP) I the top input of the 5 of three connections)  After connection are secure and intact, I attached both ground Additionally, splice the  usb cable and utilize a bread board (or painless E-Type connectors) to allow several pins to access the consistent voltage source coming from  To do this, you can can connect a wire to the positive (indicated with ’+' on hardware) terminal via screwdriver and connected the other end of the wire to one end of the momentary push button.~~

#### Step 6: Test Timer

Once everything has been configured, you should hear a satisfying beep of your circuit once the time delay has counted down to zero for a specified amount of time. For those not wanting to hear the speaker for too long, I recommend to lower the time (CL) the load will run as 1-5 seconds should be more than enough to make sure you hear the notification.

#### Step 7: Attach Supporting Hardware (Optional)

Since you need a way to place all components in a secure location, and are going to be testing it in the real world, we need to make sure that the overall build will survive its testing phase. I am big advocate for glue guns, as they do not disrupt any electrical connections and provide a quick and easy solution to essentially stick any component anywhere without having to spend all the extra time and hardware assembling through other methods that might require a 3d printer or solder that additionally require mounting via screws. Here is the [glue gun](https://amzn.to/3ScX5oQ) I use that has saved countless hours as some projects take more time in creating enclosures than the the assembly of the circuit.

### Attributions

-------------------

  **Resource #1:**

- [Button and Switch Basics](https://learn.sparkfun.com/tutorials/button-and-switch-basics/all) © 2013 by Sparkfun Electronics,  (Contributor “JIMBLOM”) is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
  - Additionally, this guide uses images and text extracted from tutorial above with  contributor “JIMBLOM” ([Sparkfun-profile](https://www.sparkfun.com/users/69916?_ga=2.172188515.1921033785.1704438252-691382123.1704438252)) embedded in this guide.

### License Information

-------------------

This product is _**open source**_!

Please use, reuse, and modify these files as you see fit. Please maintain attribution to “Robjects” and release any derivative under the same license.

#### License

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
