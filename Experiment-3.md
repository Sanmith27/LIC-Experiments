# THE MOS DIFFERENTIAL PAIR AMPLIFIER <br>
1. A differential amplifier amplifies the differential-mode voltage while rejecting common-mode signals,characterized by a high common-mode rejection ratio (CMRR) and differential gain.
2. It is built using matched BJTs or MOSFETs, often incorporating a current mirror for biasing and an active load for improved gain and linearity.
## Applications
Used in operational amplifiers, instrumentation amplifiers, and analog front-end circuits, it enhances noise immunity and precision in signal processing systems.
### Q) Design a differential amplifier for the following specifications 
| Parameter |  value | 
|-----------|--------|
|VDD        | 2.5V   |
|Vp         | 0.5V   | 
|VinCM      | 1.3V   |
|VOcm       |1.4V    |


Perform DC analysis , Transient analysis , frequency response and extract the parameters.

### *circuit diagram and design
![Alt image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/circuit%20design.jpg?raw=true)

### *Working of MOSFET-Based Differential Amplifier
A FET-based differential amplifier operates by amplifying the voltage difference between two input signals while rejecting common-mode signals. It is commonly implemented using MOSFETs or JFETs, providing high input impedance, low power consumption, and excellent noise immunity.

### *key equations 
1. Vgs>Vthn
2. Vds=>Vov   --> (Vgs-Vt)
3. Id=1/2Kn Vov^2
4. gm=Id/Vgs
5. Av=gm*Rd = 2Id *Rd/Vov (for differential amp)

### *Role of Each Component in a FET-Based Differential Amplifier
A FET-based differential amplifier consists of several key components, each playing a critical role in its operation. Below is a breakdown of their functions:

1.Matched MOSFETs (M1 & M2)
Function: Act as the active amplifying devices.
Working:
The gate terminals receive differential input signals.

The drain currents vary based on the difference in gate-source voltages.

The transistor with a higher gate voltage conducts more current, lowering its drain voltage, and vice versa.


2.Common Source Connection
Function: Both MOSFET sources are connected together to a current source.

Working:
Ensures that the current splits between the two transistors dynamically.
Helps maintain differential operation.


3.Common Source Connection
Function: Both MOSFET sources are connected together to a current source.
Working:
Ensures that the current splits between the two transistors dynamically.
Helps maintain differential operation.


4.Drain Resistors(Rd)
Function: Convert drain current variations into voltage output.

Working:
The voltage drop across Rd determines the output voltage.
The differential output voltage is given by:
Vout =(I1-I2)Rd
Larger Rd increases voltage gain.

###Summary of Component Roles

| Component           | Function                                         |
|---------------------|--------------------------------------------------|
|MOSFETs (M1 & M2)    | Act as the main amplifiers.                      | 
|Common Source        | Provides a shared reference for both transistors |
|Current Source(Ibias)| Sets the operating point and stabilizes current. |
|Drain Resistors(Rd)  | Convert current variations into voltage signals. |


### *Advantages of FET-Based Differential Amplifier
 High input impedance (good for sensor applications).
 Low noise and power consumption.
 Good linearity and stability.
 Ideal for operational amplifiers, instrumentation amplifiers, and signal processing.

 
 ## Circuit Diagram
 ![Alt image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c1.png?raw=true)
 
 
 ## DC Analysis
 Procedure 
<br> 1.Make the circuit connections as per diagram.<br>
<br>2.set w/L = 180nm/ 7.59995um such that Id becoes 5.9mA.<br>
<br>3. Even though the given parameter is 6mA ,it is bettter keep the value ratherthan exceeding , because in large scale millions and billions of transistors are used there power consumption of each fet will addup and make device less relaiable.<br>

 Oparating point
 ![Alt image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c1dc.png?raw=true)
 

| Parameter    | Theoretical value  | Practical value |
|--------------|--------------------|-----------------|
|Voutcm        | 1.40 V             | 1.40037 V       |
|Vp            | 0.5 V              | 0.498 V         |
|Id1,Id2       | 0.6 mA             | 0.598mA         |
|Id(R3)        | 1.2 mA             | 1.1965 mA       |
|Rd            | 1.83 kohm          | 1.838 kohm      |
|Rss           | 416.67 ohm         | 416ohm          |
|Vgs           | 0.8 V              | 0.801V          |
### Finding input and output swing
<br>therefore Q point = (Vds,Id) = (0.9V,0.598mA).<br>
 Vincm(min)= Vth + Vp = 0.37 + 0.5 = 0.87V <br>
 Vincm(max) = Vdd - (Id*Rd) + Vth = 1.77V <br>
 0.87V < Vin <1.77V(input swing)<br>
 Vout(min) = Vov1 + Vov3 = (0.8-0.37)+0.5 = 0.93V <br>
 Vout(max) = Vdd-(Id*Rd) = 1.4007V <br>
 0.93V<Vo<1.4007V
<br>
## Transient Analysis
procedure
* Replace DC input with an AC signal.
* Use SINE(dc_offset, Amplitude, Frequency).
* Go to "Simulate" > "Edit Simulation Cmd" > "Transient".
* Set Stop Time: 10ms.
* Run the simulation.
* Our dc_offset = 1.3V and assume amplitude as 50mV and frequency as 1Khz<BR>
  ### Case 1: Vin <0.5V (50mV amp)<br>
  ![Alt image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c1_bll.png?raw=true)
  <br> As we apply Vin as 0.4V sinewave(f=1kHz) with 50mV amolitude.
  As Vin is near to Vt(0.36V) operation of Fet is not linear infact Mi and M2 eneters to off state so output is not stable and linear.<br>
  vinp-p = 1mV<br>
  Vo is almost looks like DC voltage , Vo=2.5V<br>
  ### Case2 :vin>0.5V(50mV)<br>
  ![Alt image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c1_ll.png?raw=true)
  In this case Vgs >Vt , Vds>Vov.
  Vinp-p =1V.<br>
  Vop-p = 4.08v<br>
  Hence the Vop-p is large we can consider 0.5V as Vin minimum value. But the theoretical Vop-p=2.8V But here it is exceeding it by large margin. This implies Vin musst be above 0.6V<br>
   ### Case3 :vin=1.3V(50mV) Designed value.<br>
  ![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c1_Q.png?raw=true)
  <br>Vinp-p = 2.6V<br>
  <br>Vop-p=2.83V<br>
  The theoretical max Vo is 2.8V .So this output is meeting required design conditions.<br>
  ### Case4 :vin>1.7V(50mV) <br>
  ![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c1_ul.png?raw=true)
  <br>Here the output is distorted so we can consider above the 1.6V Fet enters to triode region and output dies out.<br>
  ## AC Analysis
  #### Steps to get Ac analysis Waveform:
- In simulation tab select AC Analysis.<br>
- In the AC Analysis tab, select **Type of Sweep as Decade**.<br>
- Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).<br>
  ![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c1_ac.png?raw=true)
<br>theoretical Gain . <br>
gain = Av= -gm*Rd 
where gm= (2Id)/Vov = 2.72mS <br>
Av= -2.72m * 1.83k = -5 V/V <br>
as we know Av= 20Log(vout/Vin)<br>
in dB scale theoretical gain is 13.97dB <br>
from this , practically we are getting 13.01dB gain <br>
Bandwidth = 13GHz <br>
3db Bandwidth = 19GHz <br>

 |Parameter      |Theory value  | Practical value |
 |---------------|--------------|-----------------|
 |Av(in dB)      | 13.97dB      | 13.1dB          |
 |Av(in V/V)     | 5v/v         | 4.5             |
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Circuit -2<br>
## Current Source-Loaded Differential Pair
### Circuit Diagram
![Alt image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c2_.png?raw=true)
### DC Analysis 
![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c2_dc.png?raw=true)
the transistor to operate in saturation region ,<br>
Vgs>Vth, <br>
Vds> Vov <br>
##### 0.801 > 0.495 Vgs > Vth <br>
##### 0.904 > (0.801-0.495) i.e Vds > Vov <br>
saturation region conditions are meet. .<br>
Therefore Q point = (Vds,Id) = (0.9V,0.598mA).<br>
### Swing of input amd output V 

Vincm(min)= Vth + Vp = 0.37 + 0.5 = 0.87V <br>
 Vincm(max) = Vdd - (Id*Rd) + Vth = 1.77V <br>
 0.87V < Vin <1.77V(input swing)<br>
 Vout(min) = Vov1 + Vov3 = (0.8-0.37)+0.5 = 0.93V <br>
 Vout(max) = Vdd-(Id*Rd) = 1.4007V <br>
 0.93V<Vo<1.4007V<br>
 
## Transient Analysis
procedure
* Replace DC input with an AC signal.
* Use SINE(dc_offset, Amplitude, Frequency).
* Go to "Simulate" > "Edit Simulation Cmd" > "Transient".
* Set Stop Time: 10ms.
* Run the simulation.
* Our dc_offset = 1.3V and assume amplitude as 50mV and frequency as 1Khz<BR>
### case 1: Vin =1.3V(50m amp)

![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c2_Q.png?raw=true)
Vincmp-p = 2.6V <br>
Vout p-p = 1.21 + 1.62 = 2.83V<br>
From theoretical value wkt Vout(max)p-p = 2.80V <br>
So in this input volatge we are getting the maximum output swing.<br>
### case 2: Vin =1.9(50m amp)
![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c2_ul.png?raw=true)
The transistor enters the triode region as Vds<Vov <br>
<br>Output will become DC as we keep moving above 1.9V. So input max can be fixed as 1.9V.
 
 ## AC Analysis
  #### Steps to get Ac analysis Waveform:
- In simulation tab select AC Analysis.<br>
- In the AC Analysis tab, select **Type of Sweep as Decade**.<br>
- Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).<br>
![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c2_ac.png?raw=true)
theoretical gain is 13.97dB <br>
  |Parameter      |Theory value  | Practical value |
  |---------------|--------------|-----------------|
  |Av(in dB)      | 13.97dB      | 13.1dB          |
  |Av(in V/V)     | 5v/v         | 4.5             |
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Circuit 3

### Circuit Diagram:Simple Current Source Differential Pair

![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c3.png?raw=true)
### DC Analysis

Vds = Vgs - Vt ( Vds = Vp = 0.4V )
0.5 + 0.3 = Vg ( since source is grounded )

Vbias = Vg = 0.8v(approx) ( Bias voltage at the gate for 3rd n type mosfet)

The width and length of the differential pair MOSFETs remain unchanged, while the third MOSFET has a width of 16.9662um and a length of 180nm.<br>
## DC analysis
![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c3_dc.png?raw=true)
**- Condition for transistor to operate in saturation region,**

Vgs>Vth, 

Vds> Vov 

From the Output Log we can observe that Vgs= 0.55V , Vth= 0.36V and Vds = 0.9V . <br>
It is satisfying the required condition therefore, the transistors lies in saturation region .
<br>Q point = (Vds,Id) = (0.9V,0.598mA).<br>
## Transeint Analysis
### Case 1: Vin =1.3V(50m amp)
![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c3_Q.png?raw=true)
Vincmp-p = 2.6V <br>
Vout p-p = 1.21 + 1.62 = 2.83V<br>
From theoretical value wkt Vout(max)p-p = 2.80V <br>
So in this input volatge we are getting the maximum output swing.<br>
### case 2: Vin =2V(50m amp)
![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c3_ul.png?raw=true)
The transistor enters the triode region as Vds<Vov <br>
<br>Output will become DC as we keep moving above 1.9V. So input max can be fixed as 1.9V.
 ## AC Analysis
  #### Steps to get Ac analysis Waveform:
- In simulation tab select AC Analysis.<br>
- In the AC Analysis tab, select **Type of Sweep as Decade**.<br>
- Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).<br>
![image](https://github.com/Harsha-B-1/LIC_4thsem/blob/main/c3_ac.png?raw=true)
theoretical gain is 13.97dB <br>
   |Parameter      |Theory value  | Practical value |
   |---------------|--------------|-----------------|
   |Av(in dB)      | 13.97dB      | 13.1dB          |
   |Av(in V/V)     | 5v/v         | 4.5             |
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# **Final Result**

 | **Parameter** |Theoretical      | **Circuit 1** | **Circuit 2** | **Circuit 3**     |
 |---------------|-----------------|---------------|---------------|-------------------|
 | **V(out1)**   |     1.4V        |1.40037V       | 1.4002V       | 1.4V              |
 | **V(out2)**   |     1.4V        |1.40037V       | 1.4002V       | 1.4V              |
 | **V(vp)**     |      0.5V       |0.498V         | 0.4989V       | 0.4988V           |
 | **Id(M1)**    |     0.6mA       |0.5982 mA      | 0.598 mA      | 0.598 mA          |
 | **Id(M2)**    |  0.6A           |-0.5982 mA     | -0.598mA      | -0.598 mA         |
 | **Iss**       |  1.2mA          |1.1965 mA      | 1.198 mA      | 1.196 mA          |
 | **W/L**       | 180nm/180nm(min)|7.59995um/180nm|7.59995um/180nm|16.9662um/180nm{m3}|
 | **Vimin**     |     0.87V       |  0.5V         |   0.4V        |       0.37V       |
 |**Vimax**      |       1.77V     |        1.7V   | 1.9V          |       2V          |
 ## comparision table
 
| Parameter          |	Circuit 1: Resistor Load |Circuit 2: Current Source Load   |	Circuit 3: Active Load                 |
 |-------------------|-----------------------|---------------|---------------|
|DC Operating Point  |	Higher power dissipation due to resistor drop	|Moderate power efficiency	       |Best power efficiency                   |
|Bandwidth (BW)     	|Highest                                        |     lower gain                  |               	Moderate                |
| CMRR              	|Low                                            |	Moderate                        |	High                                   |
|Distortion          |	Distorts early (~1.5V)	                       |Better than Resistor Load (~1.7V)|	Best linearity (~1.9V before distortion|
|Power Consumption	  |High                                           |	Moderate                        |	Low (best efficiency)                  |
|Suitability	Simple  |low-cost designs	                              |Balanced performance             |	High-precision applications            |
<br>
## Inference  
1.Integration of Additional Transistor:<br>

In one design, an extra MOSFET is introduced as a current source to enhance tail current stability.<br>
This modification ensures a more balanced current distribution in the differential configuration.  
2.Enhanced Current Stability:  

In the simpler version, the current through the main transistors depends on passive components and supply conditions.  
With the extra MOSFET, a steady tail current is maintained, minimizing fluctuations caused by external factors.  
3.Voltage Level Differences:

The output voltage comparison shows a slight variation, indicating improved regulation in the modified circuit.  
4.Alteration in Current Distribution:  

In the basic setup, the current through each transistor follows an unregulated path.   
In the improved version, the extra MOSFET ensures a regulated tail current, maintaining better balance.  
### Overall Conclusion:
The inclusion of a current source enhances stability, common-mode rejection, and tail current regulation, making the modified circuit more effective for differential applications.

 
