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
  
  

   ## Circuit 1. : with source resistance R<sub>ss</sub>
   
![Screenshot (283)](https://github.com/user-attachments/assets/4dd0db7e-d843-474c-a387-b58b6173e97d)

   
 
  ## DC ANALYSIS:

![image](https://github.com/user-attachments/assets/b8f101dd-9d80-432d-83e2-b288159b8ebe)



The output voltage **V<sub>ocm</sub>** from given design specification is matching with simulation output that is **1.25**. **(V(vout 1)) = (V(vout2))**


## TRANSIENT ANALYSIS:





  
  


  
                        

      


   



