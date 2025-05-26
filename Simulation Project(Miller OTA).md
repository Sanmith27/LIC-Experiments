# Two-Stage Miller OTA
# Design and Analysis of Two-Stage Miller Operational Transconductance Amplifier
## Abstract 
This project presents the design and analysis of a Two-Stage Miller Operational Transconductance Amplifier (OTA), a fundamental building block in analog integrated circuits. The Two-Stage OTA architecture is widely used due to its high gain, wide output swing, and improved frequency response. The first stage is a differential amplifier that provides high input impedance and initial gain, while the second stage boosts the overall gain and drives the output load. Miller compensation is employed between the two stages to enhance the phase margin and ensure stability.
The design process involves choosing optimal bias currents, aspect ratios of MOSFETs, and compensation capacitance to meet desired specifications such as high gain, sufficient phase margin, low power consumption, and wide bandwidth. The amplifier is implemented using CMOS technology and simulated using industry-standard tools like Cadence or LTspice. Key performance metrics such as DC gain, unity gain bandwidth, slew rate, power dissipation, and common-mode rejection ratio (CMRR) are analyzed

## Introduction
Operational Transconductance Amplifiers (OTAs) are essential components in analog circuit design, widely used in applications such as filters, oscillators, and analog-to-digital converters. Among various OTA topologies, the Two-Stage Miller OTA stands out for its ability to achieve high gain and wide output swing, making it ideal for high-performance analog systems. The two-stage architecture, combined with Miller compensation, offers improved frequency response and stability. This project focuses on the design and simulation of a Two-Stage Miller OTA using CMOS technology, with an emphasis on achieving an optimal balance between gain, bandwidth, power consumption, and phase margin.

## Circuit Design
The OTA consists of a differential input stage followed by a gain stage. A Miller compensation capacitor is used between the two stages to ensure stability. The transistors are sized to operate in the saturation region, with ideal current sources used for biasing. The supply voltage is set to ±1.8V.

![image](https://github.com/user-attachments/assets/c23b6140-96ce-4b9e-91e9-0320e1cedd2b)

![image](https://github.com/user-attachments/assets/8da130f4-a171-4c03-96fb-1a7d4c401df7)

The designed Two-Stage Miller OTA was simulated using LTspice. The following sections describe the sizing of transistors and key performance metrics obtained from the simulation.

## Circuit Diagram
![image](https://github.com/user-attachments/assets/a882874d-9f72-48f0-876d-9dab3737fbff)

## MOSFET Dimensions
The table below summarizes the channel length and width of each MOSFET used in the circuit:
  _______________________________________________________________________
  |**MOSFET name**|**Channel length in nm**|   **Channel width in µm**  |
  |---------------|------------------------|----------------------------|
  |      M1	      |        180	           |            80              |  
  |      M2       |     	 180	           |            80              |        
  |      M3       |   	   180             |            20              |   
  |      M4       |   	   180             |           	20              | 
  |      M5	      |        180             |           	37.5            | 
  |      M6	      |        180             |           	30              |   
  |      M7       |        180	           |            30              |
  |      M8	      |        180	           |            10              |

 ## DC ANALYSIS:
The DC analysis determines the static power consumption of the OTA. The power consumption is calculated as:
Power = VDD × (I_M6 + I_M7 + I_M8)= 0.613 mW
Where VDD = 1.8V, and the currents are measured from the DC operating point simulation.
![image](https://github.com/user-attachments/assets/9c75995b-764d-4ba0-ad71-2648228b6aac) ![image](https://github.com/user-attachments/assets/8f945727-ac32-459f-b473-979a23e178da)

## TRANSIENT ANALYSIS:
Transient analysis was carried out under differential and common-mode inputs:
- Differential Mode: A step input was applied differentially to Vin+ and Vin-.
![image](https://github.com/user-attachments/assets/9a9859aa-e58e-4392-9627-09cb4f1594e1)

- Common Mode: Identical inputs were applied to both Vin+ and Vin-.
The output response was used to analyze slew rate.
![image](https://github.com/user-attachments/assets/e4efb06f-7306-447c-a833-b9e287752c03)

- Differential mode gain = 1400 V/V or 62.9 dB
- Common mode gain = 0.562 V/V or -5dB
- Common mode rejection ratio = 67.94 dB

## FREQUENCY RESPONSE:

The frequency response was evaluated by applying an AC sweep in two scenarios:

- Differential Mode: Vin+ = 0V, Vin- swept.
![image](https://github.com/user-attachments/assets/d99063ae-ae9d-4a86-9b25-da682b2e948e)
- Bandwidth = 310 kHz

- Common Mode: Vin+ = Vin-, both signals identical.


 ![image](https://github.com/user-attachments/assets/5e643900-054f-4aa2-ae3a-372a1d028105)

The results include gain-bandwidth product, phase margin, and unity-gain frequency.

## INPUT OFFSET VOLTAGE:
The input offset voltage was extracted by applying a zero differential input and measuring the deviation from 0V at the output. This helps evaluate the mismatch between the input differential pair.
 ![image](https://github.com/user-attachments/assets/8e5bf42b-8114-48f6-8c9a-e6eff4c8d27a)

## CONCLUSION
The designed Two-Stage Miller OTA exhibits characteristics suitable for low-power and high-gain analog signal processing. The use of Miller compensation ensures stable frequency behavior and a satisfactory phase margin. Simulation results confirm the performance across DC, transient, and frequency domains.









