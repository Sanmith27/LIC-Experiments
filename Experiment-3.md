# Experiment-3

### **Differential Amplifier**

A differential amplifier is a key circuit in analog electronics that amplifies the difference between two input signals while rejecting common-mode signals (noise). It is widely used in operational amplifiers (op-amps), instrumentation amplifiers, and analog circuits.
A basic MOSFET differential amplifier consists of:

Two matched MOSFETs (M1 and M2) forming a differential pair

A current source I<sub>SS</sub> as a tail current

Two drain resistors R<sub>D</sub>

When the inputs V<sub>in1</sub> and V<sub>in2</sub> are equal, the circuit is balanced, and the current splits equally.

When V<sub>in1</sub> increases while V<sub>in2</sub> decreases, M1 conducts more current, and M2 conducts less, creating a voltage difference at the outputs.

The circuit rejects common-mode signals (same voltage at both inputs) and only amplifies the differential component

### **question:**

**V<sub>DD</sub>=2.5 V , p<=3 mW , V<sub>ICM</sub>=1.3 V, V<sub>ocm</sub>=1.4 V , V<sub>P</sub>=0.6 V**

**Circuit 1** <br>

![Screenshot 2025-03-03 135629](https://github.com/user-attachments/assets/37d26f32-c010-455b-9c3f-8ee978c185d1)

**Step 1:Dc analysis design Rd and Rss**
![WhatsApp Image 2025-03-03 at 20 10 16_27d09197](https://github.com/user-attachments/assets/93b0b360-e9fb-404f-b825-e6c8f278152d)

from the calculation we have finded I<sub>SS</sub>value as 0.909 mA <br>
I<sub>D1</sub> and I<sub>D2</sub> as 0.6 mA <br>
R<sub>D</sub> as 1.83 kohm <br>
R<sub>SS</sub> as 500 ohm <br>
V<sub>GS</sub>=V<sub>G</sub> - V<sub>p</sub> = 1.3 V - 0.6 V = 0.7 v <br>
V<sub>OV</sub> = V<sub>GS</sub> - V<sub>th</sub> = 0.7 V - 0.366 V = 0.334 V <br>

### **DC Analysis**

To set the operating point go to Configure Analysis and select Dc operating Point <br>

![Screenshot 2025-03-03 135527](https://github.com/user-attachments/assets/52aa62a0-97b6-4cbe-ad4f-ba758b588475)

to set correct operating point vary width and length values 
width = 180n <br>
length = 0.015m <br>


### **Analysis**

### Effect of VICM on Vout and VP

| **Common-Mode Input Voltage (V_ICM)** | **Output Voltage (V_out)** | **Voltage at Point P (V_P)** |
|---------------------------------------|----------------------------|------------------------------|
| **1.65V**                             | **0.9793V**                | **0.829V**                   |
| **1.1V**                              | **1.3836V**                | **0.445V**                   |



As the common-mode input voltage \( VICM \) increases, the source voltage \( VP \) also increases, causing a shift in the operating point. This leads to a higher drain current, resulting in a greater voltage drop across \( RD \), which reduces \( Vout \).

### **Calculate Gain**

![WhatsApp Image 2025-03-03 at 19 41 21_e5a9cd19](https://github.com/user-attachments/assets/9c7e173b-61f5-48c0-a325-4a8f99d94a04)


### **Calculate maximum input and output Swing**

![1000087836](https://github.com/user-attachments/assets/a7147bde-a96f-4703-9a03-c7482373dc9d)


### **TRANSIENT ANALYSIS**
go to configure Analysis and select transient analysis then <br>
stop time as 1m ,time to start saving data as 0 <br>

• Waveform Type: Sine Wave
• DC Offset: 1.3 V
• Amplitude: 50 mV
• Frequency: 1 kHz

put the same values for V2 but change the phase angle.

And in V2 phi(deg) as 180

![image](https://github.com/user-attachments/assets/e2582f63-12ab-4547-bb69-5d3355ce5e6c)


### **AC Analysis**
• Type of sweep: Decade
• Number of points per decade: 20
• Start frequency: 0.1 Hz
• Stop frequency: 1 THz
AC Amplitude as 1 and AC Phase as 0 in V1 <br>
AC Amplitude as 1 and AC Phase as 180 in V2 <br>

![image](https://github.com/user-attachments/assets/23f00bad-f11d-49fe-b218-6548ea8d2db6)


### **Circuit 2** <br>

Replace the resistor with a current source=0.909mA. 

![image](https://github.com/user-attachments/assets/6c7a1dda-0905-400f-860e-80775a53d92d)

### **DC Analysis**
![image](https://github.com/user-attachments/assets/128cfffe-93e1-4c37-9893-9cd733d29981)

### **TRANSEINT ANALYSIS**

![image](https://github.com/user-attachments/assets/548b555e-e252-4c3c-8d79-329f345360fa)

if Vin is more then the allowable swing.

![image](https://github.com/user-attachments/assets/b0851280-53c3-4fbe-9ae7-ea836453a7ed)

### **AC ANALYSIS**

![image](https://github.com/user-attachments/assets/65cc8608-0b87-4ba3-8c7e-68bfa642261d)

### **Circuit 3** <br>

Replace current Source with N-Channel MOSFET .

![image](https://github.com/user-attachments/assets/a0450fd3-c7e7-4f16-9d61-adf282e415d6)

V<sub>b</sub> should be less than V<sub>p</sub> as the drain voltage of MOSFET M3 is V<sub>p</sub>

and the V<sub>b</sub> should be greater than the V<sub>th</sub> , therefore the value of V<sub>b</sub> should be between 0.367 V and 0.967V.

### **DC Analysis**

set the operating point of M3 such that It is in saturation state.
V<sub>b</sub>=0.96 V

![Screenshot 2025-03-03 200053](https://github.com/user-attachments/assets/a803a4da-3ab0-459a-b1dc-3dd29762fbe3)

### **TRANSIENT ANALYSIS**

![image](https://github.com/user-attachments/assets/97da5a68-7b90-4c25-8954-4cbf61b8b9d9)

if vin is more then

![image](https://github.com/user-attachments/assets/85369af5-8b0c-487b-8729-efccbc9bc5de)


### **AC Analysis**


![image](https://github.com/user-attachments/assets/2b380d5e-255e-4b70-abbc-92d81539ff79)


### ""Result and Inference""

V<sub>DD</sub>=2.5 V

V<sub>p</sub>=0.6 V

V<sub>ICM</sub>=1.3 V 

V<sub>OCM</sub>=1.4 V

R<sub>D</sub>=1.8338 kohm

R<sub>SS</sub>=500 ohm

I<sub>SS</sub>=1.2 mA

I<sub>D</sub>=0.6 mA

1. When V<sub>ICM</sub> changes there is a change in the output voltage and Drain current.

2. If the input voltage is more then the minimum swing or outside the allowable swing the output wave form deforms, ie it is in triode or cutoff region.

3. If R<sub>D</sub> value changes there will be a change in the output voltage,by selecting the resistance wecan control the output voltage.
