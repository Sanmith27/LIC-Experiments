# Design and Analysis of Current Mirror Circuit
### 1. AIM   :

### Design question A
Design and analyse the current mirror circuit for the following specifications.
- Av > -10 V/V
- V<sub>DD</sub> = 1.8 V
- P <= 1 mW

Perform the DC analysis, Transient analysis and AC analysis while maintaining (W/L) same for different values of Length(L). ALso find the maximum output swing and bandwidth.
### 2.Theory:
A current mirror is a circuit used to copy (mirror) a reference current from one branch to another while maintaining a constant current. It is widely used in analog circuit design, such as biasing circuits and active loads in amplifiers.

## Principle of Operation
A current mirror operates based on the concept that two identical transistors, when subjected to the same V_BE (base-emitter voltage), will conduct the same current, assuming they have identical characteristics
 
 A reference current I<sub>REF</sub> is forced through M1, setting its gate-source voltage  V<sub>GS</sub>.
-  The gate of M1 is connected to M2, ensuring that both transistors have the same V<sub>GS</sub>.
-  Since both transistors are identical, M2 will conduct a current equally.
-  Current Copying Ensures that the output current remains identical to the reference current.
-  Output current remains constant despite changes in the load.
### for 1:1 Ratio
### 3.1 Ciruit Design


1. Determine the Total current (I<sub>TOTAL</sub>)

   I<sub>TOTAL</sub> = P/V<sub>DD</sub>= 1.8 V = 1 m/1.8 = 0.555 mA

2. Determine the reference current ( I<sub>REF</sub>)

  I<sub>TOTAL</sub>=  I<sub>REF</sub>+ I<sub>D</sub>
  
  I<sub>REF</sub> = I<sub>TOTAL</sub>/2 = 0.555m/2 = 0.277 mA

 ![Screenshot 2025-04-06 000334](https://github.com/user-attachments/assets/794cb30c-03a8-4cd0-bace-5ccb617ce7c0)

|Parameters | PMOS(M1)| PMOS(M2) | NMOS(M3) |
|-----|----|----|----|
| Length| 180nm |180nm | 180nm | 
| Width | 2.5um | 2.5um | 2.9um | 

 ### 4.1 Simulation.
 ### DC Sweep.
 By doing a DC Sweep we can determine the Q-point.
 
 ![image](https://github.com/user-attachments/assets/e7c92f57-6916-46c1-afba-56c41fc11b9f)

from the above graph we can set the biasing voltage as 0.85 V. 
 ### DC Analysis
 
 ![Screenshot 2025-04-06 000352](https://github.com/user-attachments/assets/19d64411-edeb-401d-9cc1-05c9c5dddfb0)


By changing the length of the NMOSFET to 500 nm and 1 um but keeping the W/L ratio the same we observe some changes in the V<sub>out</sub> and I<sub>D</sub>.

| Length (L) | Width (W1) | Width (W2) | Width (W3) | I<sub>REF</sub> | I<sub>D</sub> | V<sub>out</sub> |
|-----|----|----|----|----|----|-----|
| 180nm | 2.5 um  | 2.5 um | 2.9 um | 0.277 mA | 0.27711 mA | 0.552485 V |
| 500nm | 2.5 um | 2.5 um | 8.055 um | 0.277 mA | 0.284046 mA | 0.289677 V |
| 1um | 2.5 um | 2.5 um | 16.11 um | 0.277 mA | 0.285765 mA | 0.213333 V |



### Transient Analysis

 ![image](https://github.com/user-attachments/assets/fcc70ef8-2075-4cff-aa74-b1ba47f56c87)

Gain=V<sub>out</sub>/V<sub>in</sub>=-300mV/25mV= -12 V/V

### AC Analysis

![image](https://github.com/user-attachments/assets/4e1452b3-031f-4338-85c7-b4603bbd7f43)

- Gain Av = 21.1 dB.
- -3dB bandwidth frequency = 754.698 MHz.

 | Gain | Theoretical Value | Practical Value |
|---|----|---|
| Av (V/V) | 10 | 12 |
| Av (dB) | 20 | 21.1 |    

### for 1:2 Ratio
### 3.2 Ciruit Design


1. Determine the Total current (I<sub>TOTAL</sub>)

   I<sub>TOTAL</sub> = P/V<sub>DD</sub>= 1.8 V = 1 m/1.8 = 0.555 mA

2. Determine the reference current ( I<sub>REF</sub>)

  I<sub>TOTAL</sub>=  I<sub>REF</sub>+ 2*I<sub>D</sub>
  
  I<sub>REF</sub> = I<sub>TOTAL</sub>/3 = 0.555m/3 = 0.185 mA

  I<sub>D</sub>=  I<sub>REF</sub>*2= 0.37 mA
  
  ![image](https://github.com/user-attachments/assets/447ece28-ac43-4665-80a8-c03dfc3096f5)

|Parameters | PMOS(M1)| PMOS(M2) | NMOS(M3) |
|-----|----|----|----|
| Length| 180nm |180nm | 180nm | 
| Width | 2.5um | 5 um | 3.897 um | 

 ### 4.2 Simulation.
 ### DC Analysis

 ![Screenshot 2025-04-06 000639](https://github.com/user-attachments/assets/7debf9e2-f885-408b-821b-455ae604c434)

By changing the length of the NMOSFET to 500 nm and 1 um but keeping the W/L ratio the same we observe some changes in the V<sub>out</sub> and I<sub>D</sub>.

| Length (L) | Width (W1) | Width (W2) | Width (W3) | I<sub>REF</sub> | I<sub>D</sub> | V<sub>out</sub> |
|-----|----|----|----|----|----|-----|
| 180nm | 2.5 um  | 5 um | 3.897 um | 0.185 mA | 0.370105 mA | 0.552485 V |
| 500nm | 2.5 um | 5 um | 10.825 um | 0.185 mA | 0.380347 mA | 0.287608 V |
| 1um | 2.5 um | 5 um | 21.65 um | 0.185 mA | 0.382464 mA | 0.211787 V |



### Transient Analysis

![image](https://github.com/user-attachments/assets/7df0d17e-0b1e-428c-b1bc-d5a3a0696375)

Gain=V<sub>out</sub>/V<sub>in</sub>=-280mV/25mV= -11.2 V/V

### AC Analysis

![image](https://github.com/user-attachments/assets/67b911ac-3a1f-4b99-882d-b92d6c6ad52d)

- Gain Av = 20.9 dB.
- -3dB bandwidth frequency = 804.698 MHz.

 | Gain | Theoretical Value | Practical Value |
|---|----|---|
| Av (V/V) | 10 | 11.2 |
| Av (dB) | 20 | 20.9 |    

## PART - B <br>
## SIMULATION : Differential Amplifier with Current Mirror Load <br>

### Design differential amplifie for following specifications Vdd=2.5V, P≤3mW, Vicm = 1.3V, Vocm = 1.4V, Vp = 0.5V. Perform DC analysis, transient analysis & frequency response and extract the required parameters.

![image](https://github.com/user-attachments/assets/d3d28dfb-8522-43b2-a0b6-ed6ff853c3c9)

This circuit is a CMOS Differential Amplifier with a Current Mirror Load, commonly used as the input stage of an Operational Amplifier (Op-Amp) or as a Comparator. It amplifies the difference between two input voltages (Vin1, Vin2) while rejecting common-mode signals<br>

### DC ANALYSIS :<br>

![image](https://github.com/user-attachments/assets/a786d58d-91ad-43ec-9211-ab123f925352)

| Parameter    | Theoretical value  | Practical value |
|--------------|--------------------|-----------------|
|Voutcm        | 1.40V              | 1.40V           |
|Vp            | 0.5V               | 0.62V           |
|Id1,Id2       | 0.5mA              | 0.48mA          |
|Iss           | 1mA                | 0.96mA          |
|Id3,Id4       |0.5mA               | 0.48mA          |
|Iref          |0.5mA               | 0.5mA           |

### TRANSIENT ANALYSIS : <BR>

#### For Vin < 1.3V <br>
i.e Vin(min) = 0V<br>

![0V](https://github.com/user-attachments/assets/82261936-55e7-462b-a3c2-827fed7602a0)

For Vin=0V also the amplification takes place with high output peak to peak.<br>

#### For Vin > 1.3V <br>

i.e Vin = 1.3V<br>

![image](https://github.com/user-attachments/assets/515200f5-8d67-4ac9-bbf2-6f2af429d284)

Voutpp = 1.39+1.40 = 2.79V 

i.e Vin = 3V<br>
![image](https://github.com/user-attachments/assets/7554c19d-2c68-4bdd-85f1-6657fd18782a)

there is a distortion in output wavwform <br>

Therefore <br>
|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Vincm(min)     | 0.86V        | 0V              |
|Vincm(max)     | 1.76V        | 2.79V           |

### AC ANALYSIS :<br>

![ac ](https://github.com/user-attachments/assets/132c0fff-c2c5-486c-8498-45c254ff8361)

Av (dB) = 32.2 dB<br>
Av (in V/V) = 10^(32.2/20) = 40.7V/V
Now,<br>
3dB gain = 32.2 - 3 = 29.2V/V <br>
Bandwith = 7GMHz <br>

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Inference:<br>
* Differential Pair (M3 & M4) : Vin1 and Vin2 and generates a differential current.Operates in saturation for linear amplification.
* Current Mirror Load (M1 & M2) :Converts the differential current into a single-ended output.Provides high gain by increasing output resistance.
* Biasing Current Source (M6) : Ensures a constant bias current for stable operation.Determines the gain and bandwidth of the amplifier.
* Active Load (M5):Helps improve the circuit's linearity and output swing.
* Output Distortion for Vin <0.5V : If Vin is too low, M3 or M4 enter triode, causing distortion.Proper biasing is required to maintain transistors in saturation.
* Channel Length Modulation Effect: Causes a slight increase in drain current as Vds increases.
* Affects output voltage but is minimized by using longer channel lengths.

- When the length is increased and the W/L ratio of the NMOS is kept constant.
-  V<sub>out</sub> decreases, ie **output resistance** increases.
- **Drain current I<sub>D</sub> slightly increases** with increasing channel length, due to reduced channel-length modulation effects.
- Higher **L** results in **better current matching and stability** in the current mirror.


| **Feature**                  | **1:1 Ratio Current Mirror** | **1:2 Ratio Current Mirror** | **Inference** |
|------------------------------|-----------------------------|-----------------------------|--------------|
| **Current Accuracy**         | Higher accuracy due to identical transistor sizes. | Slight difference due to different transistor widths. | 1:1 ratio provides better current matching. |
| **Transistor Sizing**        | Smaller transistors, requiring less area. | Larger transistor widths needed, increasing area consumption. | 1:1 ratio is more efficient in terms of chip area. |
| **Output Resistance** | **Higher**, as longer **L** reduces $lambda$ , increasing r<sub>out</sub> . | **Slightly lower**, as larger transistor widths may introduce mismatch, slightly increasing $lambda$. | 1:1 ratio provides better stability due to **higher output resistance**. |
| **Power Consumption**        | Lower due to smaller transistors. | Slightly higher due to increased transistor sizes. | 1:2 ratio consumes more power due to larger devices. |
| **Design Complexity**        | Easier to implement and match. | Requires careful selection of width . | 1:1 ratio is simpler to design and optimize. |



- A differential amplifier performs better when a **current mirror** is used instead of a **resistor load**.  
- use of additional MOSFETs increases **complexity of the circuit**.
- using current mirror **enhances gain and stability** of the differential amplifier.
- current mirror **Reduces offset variations**.
