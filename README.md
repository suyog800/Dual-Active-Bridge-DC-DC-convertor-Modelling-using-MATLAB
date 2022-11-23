# Dual Active Bridge DC/DC convertor Modelling using MATLAB 
 DAB Topology

 
Abstract
In order to reduce the size of today’s power converters, wide bandgap semiconductor technologies are being explored. These devices, such as silicon carbide (SiC), have been shown to outperform their silicon counterparts when used in high frequency switching, high temperature, and high voltage applications. These properties make them highly desirable in the dual active bridge power converter. Being an isolated converter topology, the dual active bridge employs a transformer to provide step-up/step-down functionality and galvanic isolation for the converter. Transformers, as well as other passive components such as inductors and capacitors may be reduced in size when higher switching frequencies are employed. SiC devices used in this application can in turn provide a means to shrink overall system size and increase the power density of the converter, proving further the viability of power electronic systems in applications that require compactness and high efficiency. The aim of this project is to demonstrate the performance benefits of  the dual active bridge topology
Keywords: transformers, SiC, Galvanic isolation


INTRODUCTION


Electric vehicle charging is constantly changing and is pushing for faster battery charging rates requiring typically less than 30 minutes spent at a charging station for one full charge of an electric vehicle. The DC charging station is typically a Level 3 charger which can cater to a very high-power level between 120–240 kW. These DC charging stations are standalone units that house AC/DC and DC/DC power conversion stages. A number of power conversion modules are stacked together inside a charging station to increase the power levels and enable fast charging. DC fast-charging stations provide a high-power DC current to an electric vehicle’s battery without passing through any onboard AC/DC converter, which means the current is connected directly to the battery.

 Most cars on the road today can handle only up to 50 kW. Newer cars will have the ability to charge at greater rates of power. As EVs come with a higher range and batteries get bigger, DC charging solutions are being developed to support long-range EV batteries through fast charging stations up to 250 kW or more. The DC/DC converter in a charging station must be capable of interfacing with the rectified bus voltage (700-800 V) from a three-phase rectifier at its input and connect with the battery of an electric vehicle at its output, delivering rated power. The DC/DC converter finds important applications in a number of end equipment.



Traditional switching devices have a limit on how quickly they can switch high voltages, or more appropriately, the dV/dt ability of the device. This slow ramping process increases switching loss because the device spends more time in the switching transition. This increased switch time also increases the amount of dead time required in the control system to prevent shoot-through and shorts. The solution to this can be the usage of a Dual Active Bridge DC/DC converter. A topology that very well combines the two properties of bidirectional energy flow and galvanic isolation is the dual-active bridge topology (DAB for short). The Dual Active Bridge is a topology with two active semiconductor bridges.

This design provides an overview of the implementation of a single-phase Dual Active Bridge (DAB) DC/DC converter. DAB topology offers advantages like soft-switching commutations, a decreased number of devices, and high efficiency. The design is beneficial where power density, cost, weight, galvanic isolation, high-voltage conversion ratio, and reliability are critical factors, making it ideal for EV charging stations and energy storage applications. Modularity and symmetrical structure in the DAB allow for stacking converters to achieve high power throughput and facilitate a bidirectional mode of operation to support battery charging and discharging applications

Power density and system efficiency are two important requirements of a converter in a DC charging station. Operating at high switching frequencies enables the reduced size of magnetics. By moving to higher bus voltage to facilitate fast charging, more power can be transferred at the same current level. This helps to reduce the amount of copper, thereby improving the power density of the converter. The converter must also be highly efficient as it results in significant cost savings and reduced thermal solution.





MATERIALS AND METHODS

We are using Simulink to simulate and demonstrate this project. 

We have a DC source and we are converting it into AC using an inverter. This AC voltage is increased or decreased using a transformer and it is given to the rectifier section. Consequently, AC is converted to DC and a capacitor is used to filter out the DC.
 2.1 Transformer:

The transformer provides isolation between the input and output sides if there is any damage concerning the load consequently it does not affect the source terminals. Also based on the transformer's turn ratio we can step up or down the voltage.


2.2 Mosfets and Thyristors:

Due to the total of eight switching elements in this topology, the number of different control methods is very high and there are several degrees of freedom that can be used for optimization. The two bridge branches of a full bridge have a phase shift of 180°. Only the phase shift φ between the primary and secondary full bridge is used to control the power flow. 


Each switch is on for 50% of its respective switching period. The switch pairs in the two bridges all have the same switching period but are operated such that between each bridge a phase shift is introduced that varies based on the modulation derived from feedback measurements.
The efficiency achievable with the DAB topology lies between 96% and 99% and is primarily determined by the nominal input and output voltage as well as by the switching frequency. A further influencing factor is the desired range of the input and output voltage. This is due to the fact that at low voltages and high powers the ohmic losses represent the dominant loss component and scale these quadratically with the RMS current. In addition, when phase shift control is used in combination with a wide voltage range, there are inevitably working ranges in which an increased reactive current component is created in the transformer resulting in higher losses in the transformer winding. The other loss components in the DAB are given by the switching losses in the semiconductor switches, and the core losses in the transformer. The switching losses of the power semiconductors represent a not negligible proportion of the total losses. In order to select suitable semiconductor switches, the operating conditions in the circuit must first be analyzed. These include the maximum RMS current through the respective switches, the maximum reverse voltage, and the switching currents when the semiconductors are switched on and off. The operating frequency of the converter is also an important criterion.
In order to achieve a high-power density, it is necessary to increase the switching frequency. As a result, the usable switches are limited to MOSFETs. IGBTs are no longer suitable for frequencies above 100 kHz due to their high switching losses. If the MOSFET is now switched on, its drain-source voltage is nearly 0 V. This means that there are no significant switch-on losses, which reduces the overall loss balance.


If one considers the switching behavior of the components when operating the DAB with a high power, it quickly becomes apparent that all MOSFETs can be switched here with Zero Voltage Switching (ZVS). In the ZVS, the energy stored in the inductive components is used to recharge the switching nodes of the MOSFETs with virtually no loss. To achieve this, a positive drain-source current must be switched off. The current driven by the inductance then recharges the switching node of the MOSFETs and commutates into the body diode of the second MOSFET of the half-bridge. If the MOSFET is now switched on, its drain-source voltage is nearly 0 V. This means that there are no significant switch-on losses, which reduces the overall loss balance.

If, however, the DAB is operated at very low power using the standard phase shift control, it is no longer possible to switch with ZVS). Then, when the MOSFET is switched off, the current commutates into its own body diode and the voltage of the switching MOSFET corresponds to the input or output voltage. This means that all the energy stored in the output capacitors of the MOSFETs must be converted into heat. In addition, the current flowing in the body diode to be disabled at the time of switching must commutate into the transistor to be switched on within the switching time. During this so-called reverse recovery of the body diode, a cross current flows over the half-bridge, which is completely converted into heat. In order to avoid extreme losses and dynamic over voltages, the body diodes of the MOSFETs must, therefore, have a very short reverse recovery time (trr).
 
Placing Mosfets and switching them accordingly can convert the DC voltage source to AC voltage source and it will act as an inverter. 




2.3 Rectifier :

Rectification converts an oscillating sinusoidal AC voltage source into a constant current DC voltage supply by means of diodes, thyristors, transistors, or converters. This rectifying process can take on many forms with half-wave, full-wave, uncontrolled and fully-controlled rectifiers transforming a single-phase or three-phase supply into a constant DC level.
We can use SCRs or other thyristors and convert the modified output from the transformer to DC voltage. The thyristors act as full wave rectifier and provide controlled DC output voltage.  It is popularly used in grid-to-grid vehicle applications where it is used as a battery charging section and in case an AC supply is required, we can directly take the tapping from the inverter section. It can provide multiple opportunities to use the nature of supply (Both DC and AC)
 
2.2  full bridge rectifier


2.4 Inverter :

The inverter is an electrical device that converts DC input supply to symmetric AC voltage of standard magnitude and frequency at the output side. It is also named as DC to AC converter. An ideal inverter input and output can be represented either in a sinusoidal and non-sinusoidal waveforms. If the input source to the inverter is a voltage source, then the inverter is said to be called a voltage source inverter (VSI) and if the input source to the inverter is a current source then it is called as current source inverter (CSI).

A full bridge single phase inverter is a switching device that generates a square wave AC output voltage on the application of DC input by adjusting the switch turning ON and OFF based on the appropriate switching sequence, where the output voltage generated is of the form +Vdc, -Vdc, Or 0.
 
2.3  Full bridge inverter
 
2.4 Waveform of full bridge inverter





2.5 Capacitor:

The capacitor acts as a filter in this circuit. The capacitor increases the DC voltage and decreases the ripple voltage components of the output. Thus providing the output to be the smoothened DC







 



RESULTS AND DISCUSSION

Present results; evaluate the proposed approaches and discuss the findings. Make sure you explain how results were obtained and what they mean. About 3-4 pages with ap- propriate subdivisions
•	Relevant figures/ block diagrams/ plots

•	Justification on the parameter selection of each block

•	Inferences made


3.4	Phase modulation : 
Phase-shift modulation is probably the simplest modulation technique for dual active bridge converters. It uses D1=D2=0.5 (i.e. 2-level switched voltages), reducing the degrees of freedom to ϕ only.
The switched voltage and inductor current waveforms are depicted below:
 
3.4 phase modulation waveforms
Dual Active Bridge switched voltage and inductor current waveforms
With this method, the power transfer between the primary and secondary has the following simple expression and has a maximum for ϕ=0.25.
P=(nV1V2/(fsw*L))* ϕ (1−2ϕ)
Some of the benefits and drawbacks of this method are summarized in the following table:
Benefits	Drawbacks
Simplicity (1-D of freedom)	Higher RMS transformer current
Highest achievable power flow	Limited operating range with low switching losses
Due to a high RMS current (hence conduction losses), and high switching losses, phase-shift modulation cannot be used for high-efficiency applications. Nevertheless, the best ratio between transferred power and inductor RMS current is optimal when V1=nV2, making phase-shift modulation attractive when operated close to that operating point.



CONCLUSION


With Dual Active Bridge converters, one can be interested in controlling the secondary voltage to a fixed value. A simple way of achieving that is by acting on the angle  to control the power transfer to charge/discharge the secondary DC bus to the desired voltage. In this work, a dual active bridge is identified as a preferred power converter for interfacing the low voltage and high voltage dc busses of the Smart Green Power Node system due to its potential high power capacity and bidirectional power flow capabilities. An overview of the dual active bridge converter principle of operation, bidirectional power flow capability, and dynamic characteristics were discussed . Converter modeling and control methods are develope. In conjunction with the feed forward control path, this control scheme facilitates optimal converter operation and performance, even accounting for load disturbances. Matlab/Simulink simulations verify this control scheme’s quality
The resulting converter from this work will require further work in order to meet all desired specification of  this system. This future work will include further investigation of losses in the converter and testing of the digital controller under load disturbance scenarios. Tuning of the dead time could lead to increased efficiency, but will certainly lead to a better voltage conversion ratio as the dead time reduces the effective pulse width of each gate signal and reduces the average voltage delivered to the primary of the transformer. 







REFERENCES

1.	https://core.ac.uk/download/pdf/72841017.pdf
2.	https://eepower.com/news/10kw-bi-directional-dual-active-bridge-reference-design-with-sic-mosfets/
3.	https://imperix.com/doc/implementation/dual-active-bridge-control#Modulation-techniques-for-Dual-Active-Bridge-converters




