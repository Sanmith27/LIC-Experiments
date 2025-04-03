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

  ![image](https://github.com/user-attachments/assets/447ece28-ac43-4665-80a8-c03dfc3096f5)

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
 
 ![image](https://github.com/user-attachments/assets/315d8e80-e30b-43b3-8125-a9d5f803c825)

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
 
 ![image](https://github.com/user-attachments/assets/a22ed3e0-1f72-48c6-bae5-bf55954379f8)

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

### Design B
Design the differential amplifier using the same design specification as Experiment_3. 

- V<sub>DD</sub>=3.3 V
- p<=3 mW
- V<sub>ICM</sub>=1.65 V
- V<sub>ocm</sub>=1.7 V
- V<sub>P</sub>=0.5 V
### Circuit
 from calculation we have found I<sub>SS</sub> value as 0.909 mA <br>
I<sub>D1</sub> and I<sub>D2</sub> as 0.45 mA <br>
the ratio is 1:2 thus I<sub>REF</sub>=I<sub>SS</sub>/2 = 0.45 mA <br>

![image](https://github.com/user-attachments/assets/9c633fb7-f2ac-4100-9e4e-6ccf9117df9f)

 
 |Parameters | PMOS(M3)| PMOS(M4) | NMOS(M1) | NMOS(M2) | NMOS(M5) | NMOS(M6) | 
|-----|----|----|----|----|----|-----|
| Length| 180 nm |180 nm | 180 nm | 180 nm | 1 um | 1 um | 
| Width | 2.214 um | 2.214 um | 1.82 um | 1.82 um | 220 um |110 um |  

 ###  Simulation.
 ### DC Analysis
 
![image](https://github.com/user-attachments/assets/d18c3841-44cb-4ce6-a557-c2b1e7fec90a)

### Transient Analysis

![image](https://github.com/user-attachments/assets/092173af-e22a-42ed-b386-c3fa881e69f6)

Gain=V<sub>out</sub>/V<sub>in</sub>=-65 mV/2mV= -2.6 V/V
### AC Analysis

![image](https://github.com/user-attachments/assets/3397b664-e436-4bc1-9854-8b8507444979)

- Gain Av = 4.5 dB.
### 5.Inference
When the length is increased and the W/L ratio of the NMOS is kept constant.
-  V<sub>out</sub> decreases, ie **output resistance** increases.
- **Drain current I<sub>D</sub> slightly increases** with increasing channel length, due to reduced channel-length modulation effects.
- Higher **L** results in **better current matching and stability** in the current mirror.
- 

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
