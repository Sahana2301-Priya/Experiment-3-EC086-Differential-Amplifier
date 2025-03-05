## Experiment-3-EC086-Differential-Amplifier
A differential amplifier is an electronic amplifier that **amplifies the difference between two input signals**. It is a key component in many analog circuits and plays a crucial role in reducing common-mode noise (signals that are the same on both inputs) while amplifying the difference between the two input voltages.

**Key aspects**:

1. **Two Inputs (V₁ and V₂):** A differential amplifier has two input signal V<sub>1</sub>(non-inverting input) and V<sub>2</sub>(inverting input).The amplifier amplies the difference of **V<sub>1</sub>-V<sub>2</sub>**

2. **Output (V_out):** The output of the differential amplifier is a signal proportional to the difference between the two inputs. The general form of the output is:
                          **V<sub>out</sub>= A<sub>d</sub> * (V<sub>1</sub>-V<sub>2</sub>**) where **A<sub>d</sub>** is the differential gain of the amplifier.
   
3. **Common-Mode Rejection Ratio (CMRR):** This parameter indicates how well the amplifier rejects common-mode signals (signals that are the same on both inputs). A high CMRR means that the amplifier is good at rejecting noise that affects both inputs equally.

4. **Single-Ended Output:** In many cases, the differential amplifier produces a single-ended output (referenced to ground) rather than a differential output (where both the positive and negative outputs are referenced to each other).

## MOSFET (Metal-Oxide-Semiconductor Field-Effect Transistor)

For an **N-channel MOSFET**, the transistor has three regions of operation: **cutoff**, **linear (or triode)**, and **saturation**. In the saturation region, the transistor allows current to flow with minimal resistance.

### Conditions for Saturation in a MOSFET:

1. **Gate-Source Voltage <V<sub>GS</sub>**:  
   The gate-source voltage must be greater than the threshold voltage:
   -**V<sub>GS</sub> > V<sub>t</sub>**

2. **Drain-Source Voltage:**  
   The drain-source voltage must be large enough for the MOSFET to enter saturation:
   -  **V<sub>DS</sub> >= V<sub>GS</sub> > V<sub>t</sub>** is the threshold voltage of the MOSFET.
  
![WhatsApp Image 2025-03-05 at 16 22 57_0e560a2d](https://github.com/user-attachments/assets/00b77b5d-b317-4a1b-8c2a-df2aa5c2ad33)


 
## Differential Amplifier:

![image](https://github.com/user-attachments/assets/771790ee-1ce1-4124-be14-bb970567c8ed)


## Design Specifications: 

Given 
- P <= 2.2mW
- V<sub>DD</sub> = 2.2 V
- V<sub>icm</sub> = 1.2 V
- V<sub>ocm</sub> = 1.25 V
- V<sub>p</sub> = 0.4 V

**Answer:**             we know that **P <= V<sub>DD</sub> * I**

                        2.2mW <= 2.2 * ID
                        
                        ID= 2.2mW / 2.2

                         ID >= 1mA
  then, 
      **I<sub>D</sub> = 1mA**                       **I<sub>d1</sub> = I<sub>d2</sub>** = 1mA/2 =    **0.5 mA**

  then, **R<sub>D</sub> = V<sub>DD</sub> - V<sub>ocm</sub> / I<sub>d1</sub>**

                       = 2.2 - 1.25 / 0.5mA

**R<sub>D</sub> = 1.9k&Omega;**

**R<sub>ss</sub> =  V<sub>p</sub> / I<sub>D</sub>** 

                 = 0.4 / 1mA 

  **R<sub>ss</sub> = 400 &Omega;**    

  


  ### SIMULATION:

This report presents the DC analysis, AC analysis, Transient analysis of a differential NMOS amplifier. The objective of this analysis is to determine the DC biasing conditions, gain and output impedence using Transient analysis, and to find frequency response using AC analysis.



  ## **Component Details:**
The circuit consists of a TSMC 180nm NMOS transistor (CMOSN), a drain resistor and two voltage sources. The drain resistor limits the current through the transistor and affects the small-signal gain. The NMOS transistor operates in saturation region, making it suitable for amplification.


**Model:** **CMOSN**

**Channel Length:** 180nm

**Channel Width:** 5  &micro;m

**Threshold Voltage:** 0.366V

**Resistor:** 1.9 k&Omega;

**Supply Voltage:** 2.2 V

**DC Voltage:** 1.25 V

**Frequency:** 0.1kHz


  ## Procedure:

1.Create a new folder and name it as project file.Save the LT spice file in this folder.

2.Name the mosfet as CMOSN and the length as 180nm and width as 5um initially.

3.**DC Analysis**: Set up the circuit as per the circuit diagram with proper connections ensuring valid circuit for further analysis. Apply the DC voltage of Vdd=2.2V and Vicm = 1.2 V . Go to simulate option in the tab and edit simulation command, click on DC analysis and press ok.(.op) Click on Run in the tab menu to get the DC operating point ,Vout and Id.

4.**Transient Analysis:** Apply a sine wave input of Vicm = 1.2 V with an amplitude of 50mV and frequency of 0.1kHz by going to advanced menu in the voltage setting option.go to simulate option in tab ,edit simulation command , click on transient analysis and give the stop time as 5m and click ok. Now Run to visualise the response of the circuit to a time varying signal.

5.**AC Analysis:** Go to spice directive and give the library file path for the simulator to access the data through the path . Go to simulate option in the tab , edit simulation command , click on AC analysis and mention the time of sweep as decade , no of points as 20 and frequency as 1kHz to 100THz and click on ok. Now Run to analyze the gain and frequency response of the circuit


  

   ## Circuit 1. : with source resistance R<sub>ss</sub>
   
![Screenshot (283)](https://github.com/user-attachments/assets/4dd0db7e-d843-474c-a387-b58b6173e97d)

   
 
  ## DC ANALYSIS:

Start varying the width to get the required  **V<sub>ocm</sub> = 1.25 V**  value from the simulation.

![image](https://github.com/user-attachments/assets/b8f101dd-9d80-432d-83e2-b288159b8ebe)




when **width is 5.82774 &micro;m**    **V<sub>ocm</sub> = 1.25 V**

The output voltage **V<sub>ocm</sub>** from given design specification is matching with simulation output that is **1.25 V**. **(V(vout 1)) = (V(vout2))**


 ## TRANSIENT ANALYSIS:

 Transient analysis in a differential amplifier examines how the amplifier reacts to time-varying inputs, such as step or sinusoidal signals. It helps to assess the time-domain response, including key parameters like rise time, settling time, and distortion from capacitive effects. The analysis shows how quickly the output responds and whether there are any delays, overshoot, or instability.

For this experiment, we will find the gain of the circuit.
For the same circuit, we will perform the transient analysis keeping the sinusoidal voltage signal  **input voltage as 1.2 V**, and **amplitude 50mV**, and **frequency = 0.1kHz**
And the **AC amplitude as 1V**.
In the configure analysis select  **stop time as 5ms**. There is **180 degree phase shift** between input and output and a DC level phase shift observed.


![image](https://github.com/user-attachments/assets/32a90670-a770-4cfc-91ba-909a9fd19331)


From graph, **V<sub>out(peak)</sub> = 71.948 mV**



![image](https://github.com/user-attachments/assets/e747433b-4595-4938-82f2-786b23a672f3)


From graph, **V<sub>in(peak)</sub> = -49.579 mV**


Therefore, **Gain = V<sub>out(peak)</sub>  /  V<sub>in(peak)</sub>**

                  = 71.948 mV / -49.579 mV

                  = -1.45


**Gain = -1.45**


**Gain in dB = 20 * log<sub>10</sub> (Gain)**

             = 20 * log10 (1.45)

             = 3.227 dB

 **Gain in (dB) = 3.227 dB**    


 ## AC ANALYSIS:

 
![image](https://github.com/user-attachments/assets/0de85862-696a-4f1b-b938-a6cb8b16ffb3)




## Circuit-2: Replace source resistance R<sub>ss</sub> by current source(I) (1mA)


![image](https://github.com/user-attachments/assets/716b16d1-86e5-47cd-9f1d-8337e8d9a82c)




   same procedure ; just replacing R<sub>ss</sub> by current source(I) (1mA)

   

## DC ANALYSIS:



![image](https://github.com/user-attachments/assets/d8c639ef-402a-49c4-bac5-315416710432)



when **width is 5.82774 &micro;m**    **V<sub>ocm</sub> = 1.25 V**

The output voltage **V<sub>ocm</sub>** from given design specification is matching with simulation output that is **1.25 V**. **(V(vout 1)) = (V(vout2))**


## TRANSIENT ANALYSIS:

 Transient analysis in a differential amplifier examines how the amplifier reacts to time-varying inputs, such as step or sinusoidal signals. It helps to assess the time-domain response, including key parameters like rise time, settling time, and distortion from capacitive effects. The analysis shows how quickly the output responds and whether there are any delays, overshoot, or instability.

For this experiment, we will find the gain of the circuit.
For the same circuit, we will perform the transient analysis keeping the sinusoidal voltage signal  **input voltage as 1.2 V**, and **amplitude 50mV**, and **frequency = 0.1kHz**
And the **AC amplitude as 1V**.
In the configure analysis select  **stop time as 5ms**. There is **180 degree phase shift** between input and output and a DC level phase shift observed.



![image](https://github.com/user-attachments/assets/010dd368-05e7-4d7a-b83d-dbba72e9f57d)


 From graph, **V<sub>out(peak)</sub> = 196.29907 mV** 


 ![image](https://github.com/user-attachments/assets/7b74e9da-0c01-4693-a18e-d1f3068e73f5)


 From graph, **V<sub>in(peak)</sub> = -49.79327 mV** 


 Therefore, **Gain = V<sub>out(peak)</sub>  /  V<sub>in(peak)</sub>**

                  = 196.29907 mV /  -49.79327 mv

                  = -3.942


**Gain = -3.942**


**Gain in dB = 20 * log<sub>10</sub> (Gain)**

             =  20 * log10 (3.942)

             =   11.914

  
 **Gain in (dB) = 11.914 dB** 

 
 ## AC ANALYSIS:


![image](https://github.com/user-attachments/assets/e5875548-c1bf-4a15-9090-e2a440b1b26c)



## Circuit-3: Replace source resistance R<sub>ss</sub> by Mosfet(NMOS4)



![image](https://github.com/user-attachments/assets/dbdd8265-f7a3-4177-9c9d-f7098b95305b)



 same procedure ; just replacing R<sub>ss</sub> by **Mosfet(Nmos4)**


## DC ANALYSIS:



when **width is 5.82774 &micro;m**    **V<sub>ocm</sub> = 1.25 V**

The output voltage **V<sub>ocm</sub>** from given design specification is matching with simulation output that is **1.25 V**. **(V(vout 1)) = (V(vout2))**

;and Nmos4 mosfet width is given as **15.96841 &micro;m** to get the output voltage as **1.25 V** and input voltage given is 



![image](https://github.com/user-attachments/assets/e4fba07a-1827-487a-be32-10f20501e1e3)


## TRANSIENT ANALYSIS:


Transient analysis in a differential amplifier examines how the amplifier reacts to time-varying inputs, such as step or sinusoidal signals. It helps to assess the time-domain response, including key parameters like rise time, settling time, and distortion from capacitive effects. The analysis shows how quickly the output responds and whether there are any delays, overshoot, or instability.

For this experiment, we will find the gain of the circuit.
For the same circuit, we will perform the transient analysis keeping the sinusoidal voltage signal  **input voltage as 1.2 V**, and **amplitude 50mV**, and **frequency = 0.1kHz**
And the **AC amplitude as 1V**.
In the configure analysis select  **stop time as 5ms**. There is **180 degree phase shift** between input and output and a DC level phase shift observed.



![image](https://github.com/user-attachments/assets/53712468-ad4a-4bd5-ac2d-04c236eae142)

  
From graph, **V<sub>out(peak)</sub> = 197.21196 mV** 


  
![image](https://github.com/user-attachments/assets/4949c55f-c211-4a77-8407-d09a875063c9)

  
From graph, **V<sub>out(peak)</sub> = -49.791593 mV**                         

      
 Therefore, **Gain = V<sub>out(peak)</sub>  /  V<sub>in(peak)</sub>**

                  = 197.21196 mV /  -49.791593 mv

                  = -3.960


**Gain = -3.960**
   

**Gain in dB = 20 * log<sub>10</sub> (Gain)**

             =  20 * log10 (3.960)

             =   11.914 dB


 **Gain in (dB) = 11.914 dB** 
 


 ## AC ANALYSIS:
 

 ![image](https://github.com/user-attachments/assets/844423a0-e7ce-4f23-a1b7-0c6257a5687e)



 ## Inference for Differential Amplifier Experiment

The **Differential Amplifier** is a key component in many analog circuits, known for amplifying the difference between two input signals while rejecting common-mode signals. This experiment explores the analysis and performance of a differential amplifier using an **NMOS transistor**.

### Key Design Specifications and Calculations:
- The **power** for the differential amplifier is constrained to **2.2 mW**, and the supply voltage is **2.2 V**.
- Using the power equation, the **drain current I<sub>D</sub>** is calculated to be **1 mA**.
- With the calculated current, the **drain resistance R<sub>D</sub>** is determined to be **1.9 kΩ**, and the **source resistance R<sub>ss</sub>** is calculated to be **400 Ω**.

### MOSFET Saturation Region:
- For an **N-channel MOSFET** to operate in the **saturation region**, the **gate-source voltage V<sub>GS</sub>** must exceed the threshold voltage **V<sub>t</sub>**, and the **drain-source voltage V<sub>DS</sub>** must be greater than or equal to the difference between **V<sub>GS</sub>** and **V<sub>t</sub>**. This ensures minimal resistance in the MOSFET, allowing for effective amplification.

### Simulation Results:
The experiment involves **DC analysis**, **Transient analysis**, and **AC analysis** to evaluate the performance of the differential amplifier. The simulations are conducted using the **TSMC 180nm NMOS transistor** model.

#### DC Analysis:
- The **DC operating point** is established by adjusting the transistor's width until the **common-mode output voltage (V_ocm)** reaches **1.25 V**, as per the design specifications.
- The results show that when the MOSFET width is **5.82774 µm**, the output voltage **V<sub>ocm</sub>** aligns with the expected value, confirming the correctness of the design.

#### Transient Analysis:
- In the transient analysis, the circuit’s response to a sinusoidal input signal is examined. A **180° phase shift** is observed between the input and output signals, indicative of inverted amplification.
- The **gain** is calculated by measuring the peak values of the output and input voltages. The **gain** for the first circuit is **-1.45** (or **3.227 dB**), which demonstrates the amplifier's ability to amplify the signal in the expected range.

#### AC Analysis:
- The **AC analysis** provides insights into the frequency response of the amplifier. The gain remains stable over a wide range of frequencies, confirming the amplifier is functioning as expected. The **gain in dB** is **3.227 dB** in the first case.

### Component Changes and Performance Variations:
- **Circuit 2** involves replacing the **source resistance R<sub>ss</sub>** with a **current source (1 mA)**. This modification results in a higher gain of **-3.942** (or **11.914 dB**), indicating that using a current source improves the performance of the differential amplifier by providing more controlled and stable biasing conditions.
- **Circuit 3** replaces the source resistance with an additional **NMOS transistor (NMOS4)**. This further improves the gain to **-3.960** (or **11.914 dB**), demonstrating that replacing passive components with active ones (like additional MOSFETs) can significantly enhance the performance of the differential amplifier.

### Frequency Response and Stability:
- Across all simulations, the circuit maintains stability in terms of gain, confirming that the differential amplifier is working efficiently across various frequency ranges. The **-3 dB points** in the frequency response analysis help confirm the amplifier's bandwidth limits.

### Conclusion:
The differential amplifier experiment highlights several important aspects of its operation:
- The importance of precise **biasing** to achieve the correct operating point.
- The ability to reject **common-mode signals** and amplify the difference between the two inputs.
- The impact of different circuit configurations on the **gain** and **frequency response** of the amplifier.

By replacing **source resistance** with different configurations (current source or NMOS transistor), the amplifier's performance is significantly improved, offering higher gain and better stability. The combination of **DC**, **Transient**, and **AC analyses** provides a comprehensive understanding of the amplifier's characteristics and its suitability for amplification tasks in real-world applications.



