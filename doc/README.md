# Timer_v0
This is the first of many iterations of the engineering design process with the intention of making a timer product from scratch. 
##### Context: 
This idea resulted from the frustration and problem that occurred from not being able to focus on my tasks due to being distracted from my phone. And while perhaps some of you might just propose that I just not use the phone or put it away. 



# Phase 1: 
### Goal: Design a timer from scratch

### Constraints (in order of priority): 
1. Speed
2. Cost

## Build:
### Materials:

Timer Audio Speaker
- link:[continous noise](<https://www.amazon.com/WEICHUANG-Active-Electronic-Buzzer-Continous/dp/B08SL2HH65/ref=pd_rhf_ee_s_rtpb_dse_gccp_d_sccl_1_1/134-5006114-5799961?pd_rd_w=D0Pkn&amp;content-id=amzn1.sym.bd729ef1-498a-4698-af50-62a8451fe601&amp;pf_rd_p=bd729ef1-498a-4698-af50-62a8451fe601&amp;pf_rd_r=2C5HW1ZBKN6NPA01PC1J&amp;pd_rd_wg=yzE9w&amp;pd_rd_r=d8693a1f-f875-4a2c-b554-d4703c50f468&amp;pd_rd_i=B08SL2HH65&amp;th=1&_encoding=UTF8&tag=robjects-20&linkCode=ur2&linkId=5990d4b99e3aa094efbfdd2ef1ece628&camp=1789&creative=9325>) or [intermittent noise](https://www.amazon.com/dp/B07TT8WTVD?pf_rd_p=f734d1a2-0bf9-4a26-ad34-2e1b969a5a75&pf_rd_r=QMAFSB455EY4MSY7AQ89&pd_rd_wg=lADMj&pd_rd_w=ewlel&content-id=amzn1.sym.f734d1a2-0bf9-4a26-ad34-2e1b969a5a75&pd_rd_r=4b9a9a6e-b667-481d-a593-6eff4ede5592&s=hi&sp_csd=d2lkZ2V0TmFtZT1zcF9kZXRhaWw&th=1&linkCode=ll1&tag=robjects-20&linkId=c1d433b61ed1f27875ab7c4ad51de17c&language=en_US&ref_=as_li_ss_tl)
- manual

  Timer circuit
- link:
- manual![B1GVAXm4XqS](https://github.com/Robjects-Timers/Timer_v0/assets/20546156/ea89280b-eca0-4921-95b7-2f90bd583674)

  power supply with switch
  - [link](https://www.amazon.com/dp/B09WF27Q9N?coliid=I2K2YT9T4UHR2G&colid=1ERO15SLA5MAH&th=1&linkCode=ll1&tag=robjects-20&linkId=20dff3bb4d6340ae63bbe2612306943e&language=en_US&ref_=as_li_ss_tl)
  - 


   And here is some supplementary hardware that might be of use
  -batteries 9v: https://www.amazon.com/dp/B07RZ9PMQH?ie=UTF8&s=hpc&sp_csd=d2lkZ2V0TmFtZT1zcF9kZXRhaWxfdGhlbWF0aWM&pd_rd_i=B07RZ9PMQH&pd_rd_w=vp6iG&content-id=amzn1.sym.d81b167d-1f9e-48b6-87d8-8aa5e473ea8c&pf_rd_p=d81b167d-1f9e-48b6-87d8-8aa5e473ea8c&pf_rd_r=FYMGS02B0Z433V6EBPFQ&pd_rd_wg=VUT62&pd_rd_r=27799fe5-2c6a-492e-910a-02871a5f1d2c&th=1&linkCode=ll1&tag=robjects-20&linkId=89d975d5e423e5ddc7f23108ab8d79c5&language=en_US&ref_=as_li_ss_tl
  
  - [power module 5 pack] https://www.amazon.com/dp/B07SC1FSM9?coliid=IYU0HMCZAAKKF&colid=1YRP8QIT5XT4C&psc=1&linkCode=ll1&tag=robjects-20&linkId=491c00a8b245f979cfaa459522417f1f&language=en_US&ref_=as_li_ss_tl
 
  - battery connectors
    1. https://www.amazon.com/dp/B07YBYL7HH?coliid=I17EOFCT0C7RLH&colid=1YRP8QIT5XT4C&psc=1&linkCode=ll1&tag=robjects-20&linkId=e35b831ced6d6c32f630668e08efc097&language=en_US&ref_=as_li_ss_tl
     2. https://www.amazon.com/dp/B08SL9X2YC?coliid=I1Y8GKUAYXOEDZ&colid=1YRP8QIT5XT4C&th=1&linkCode=ll1&tag=robjects-20&linkId=663cc92690b22550993a0a85a28c1837&language=en_US&ref_=as_li_ss_tl

  3. https://www.amazon.com/dp/B06XX25HFX?coliid=I33RCI68G0QX9P&colid=1YRP8QIT5XT4C&psc=1&linkCode=ll1&tag=robjects-20&linkId=23fa6e515e3b7909197d4d5000cb9026&language=en_US&ref_=as_li_ss_tl

 -switches https://www.amazon.com/dp/B08F1D52YS?coliid=I3EZ62SRTM9V64&colid=1YRP8QIT5XT4C&psc=1&linkCode=ll1&tag=robjects-20&linkId=2276a1a3069cad982ad72d120e89af9f&language=en_US&ref_=as_li_ss_tl




#### Step 1: Configure Timer
After gathering of all components, let's go ahead and grab the timer pcb and configure the equipment for a test run. Follow these steps to configure a 10 second timer.

  ##### First, there are two ways to power the timer circuit.
  1. Easiest: Through USB cable 
  2. Easier: DC cable pins (battery-powered or not)

For the sake of just configuring and testing the circuit, we'll go through the easiest way to power the circuit, which is through the usb connectors. Depending on what type of circuit, you bought, you can grab either a usb-c (or micro usb cable) and connect it to the circuit via almost usb connector as this circuit has a WIDE input voltage, 6V - 30V with a low working amperage of 50 mA making the circuit a very versatile tool.





#### Step 2: Configure Timer
- ~~Note: Keep in mind that~~ 
##### Second, We will set the mode and variable inputs.
 For this timer, there are many different configurations possible. Since we just want to set a time prior to the execution of a speaker we will utilize Mode _________
  which enables us to set a time(___) prior to powering on the load and a time,____, which will specify the  duration of which the load will go on. If you would like to learn more about the different possible modes please refer to documentation of which you can access via this link.


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