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

- ~~Note: Keep in mind that~~ 
##### Second, We will set the mode and variable inputs.
 For this timer, there are many different configurations possible. Since we just want to set a time prior to the execution of a speaker we will utilize Mode _________
  which enables us to set a time(___) prior to powering on the load and a time,____, which will specify the  duration of which the load will go on. If you would like to learn more about the different possible modes please refer to documentation of which you can access via this link.



## Notes & Considerations:
- Understand while this version is completely free and adaptable for whomever may want it, keep in mind I do not recommend this be the first process for professionals (also why it is "version 0") 
- Do not recommend for those with educational experience or intention in the field of creating products or those or professionals that want a well-rounded researched time without such extreme time-constraints.
- Even though I accomplished the feat of my goal; In hindsight, I missed out on better researched, analyzed decisions that could come arise from either having an additional member to check my on the spot, critical-thinking ideas. Which, ultimately, resulted in me having made some rather unwise, unintelligent design decisions in the financial, hardware selection of which I had to stubbornly stick through for the purpose of finishing quick and fast. 

- This is why I have labeled this project as "Timer-V0" and made it public as although flawed, it authentically shows that imperfections and mistakes can be made, even from me with more experience. Additionally, it still might be very beneficial and encouraging for those with little to no design experience, or those frustrated from option paralysis of all the stacks of data. Sometimes, in the grand scheme of the entire design process, more advantage and learnings could be gleaned from just making a decision and finding it was a mistake. Mistakes are inevitable, and the quicker you get to them, the faster you learn and make improvements rather than be stuck reviewing and overthinking things needing action. There is something incredibly that seems to occur in your brain from feeling shame and anxiety gained, although incredibly unwarranted, from failure. It is always what you do afterword in the end that determines your result and improvements over the long run.

- This could have very easily been avoided had I spent more time in research or even having someone else check my train of thought where I can review more than a few options to make better on the spot decisions.

Because Rendition Version 0 is so incredibly f While I 

Keep in mind that in order to optimize speed in the attempt of creating the project in a day, there were some very flagrant considerations that I had to temporarily ignore and mentally restrain (with agonizing difficulty) myself from the good engineering habits in order to meet the requirements.
- The need for portability
- Optimization of energy
- 

- Although for some people the solution can apply with no problem, there are still some very real applications and/or tools needed for your work-related activities such as utilization of alarms, using calculator apps, two-factor authentication, and in case of emergency calls, you just aren't quite able to remove the need for a phone in the viciinity that requires your attention. that might truly be more productive or necessaryt to get work-related tasks