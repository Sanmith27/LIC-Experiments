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
  |  MOSFET name  |	Channel length in nm	 |     Channel width in µm    |
  |      M1	      |        180	           |            80              |  
  |      M2       |     	 180	           |            80              |        
  |      M3       |   	   180             |            20              |   
  |      M4       |   	   180             |           	20              | 
  |      M5	      |        180             |           	37.5            | 
  |      M6	      |        180             |           	30              |   
  |      M7       |        180	           |            30              |
  |      M8	      |        180	           |            10              |
  |_______________|________________________|____________________________|
