# Quiz 25
In the moving spectrum example, if the frameIndex is 5 and the frameOffset is 120, pick the correct value for each of these..
g (green variable) 10
b (blue variable) 224
y coordinate of the horizontal line that is drawn in that round 125

How many horizontal lines are drawn during the execution of this code?
![[wlox13xf.bmp]]
16,384 $128*128$

To modify the code in the question above to produce nonblocking code, how can the variables frameIndex and frameOffset be declared? Choose A for Acceptable and N for Not acceptable.
- leave them as is N
- make them static variables A
- make them global variables N
- add them to the application struct so they can be passed by reference A
In the blocking code example, why was the green LED not toggling at the correct time interval?
SWTimer_expired is not executed until after the for loop is complete
# Quiz 26
Consider an A/D with n = 4 and Vref- = 0V and Vref+  = 4V. Assume the A/D uses the floor (rounded down)  of the conversion formula when turning non-integers to integers. Select all correct statements.
1. There are 16 possible digital outputs. True $2^n$
2. If the input is 0 V, the output is 0000. True
3. The voltage value of LSB is 0.25 V.  True $\frac{V_+-V_-}{2^n}$ 
4. If the input voltage is 0.95, the output is 0011. True
5. The A/D analog span is 4 V.  True
6. If the input voltage is 1.95, the output is 1000. False
Consider an A/D with n =1, Vref - = 0V, Vref+ = 1V. Assume the A/D uses the floor of the conversion formula when turning non-integers to integers. Select all that is correct.
1. If the input is 0.4 V, The output is 0. True
2. If the input is 0.7 V, The output is 0. False
3. 1LSB is 0.5 V. True
Consider two A/Ds
1. n= 4, Vref-=0, Vref+=2V
2. n = 8, Vref-=-1V, Vref+ = 1V
Choose all that is correct.
1. The digital resolution of the second A/D is higher than the first one. True
2. The voltage resolution (1LSB or analog resolution) of the second A/D is larger than the first one. False
3. Both A/D have the same full-scale range or analog range. True
Consider a D/A with n = 2, Vref- = -1V and Vref+ = +1V. Choose all that is correct.  
1. The LSB is worth 0.5V (in other words 1LSB is equal to 0.5V).True
2. If the input is 00, the output is -1V. True
3. If the input is 11, the output is +1V. False
4. If the input is 10, the output is 0V.  True
5. The digital resolution is 2 bits. True
6. The analog resolution is 2/3 of a volt. False
For each item, decide whether it is a transducer or not:
light sensor is
solar cell is
oven temperature controller (a circuit that connects or disconnects the power to the heating element based on the temperature sensor reading using a transistor switch is not
# Quiz 27
What port the microphone is connected to? P4
What pin is the microphone connected to? 3
What driverlib function configures the i/o pin for microphone to act as an analog input?
`GPIO_setAsPeripheralModuleFunctionInputPin` with last argument as `GPIO_TERTIARY_MODULE_FUNCTION`
What is the name of the gate in the i/o pin schematics for pin 6.0  that passes an analog input without changing it? transmission gate
Which of the following is not part of the ADC block diagram? The error flag generator in case something goes wrong with the conversion
If we wish to record the result of the conversion of the microphone input in 15th storage location in the ADC, and we like to use VSS and VCC as the Vref- and Vref+, what line of code we should use? (Keep in mind the microphone provides one single analog signal)
```c
ADC14_configureConversionMemory(ADC_MEM14,
								ADC_VREFPOS_AVCC_VREFNEG_VSS, 
								ADC_INPUT_A10, 
								ADC_NONDIFFERENTIAL_INPUTS);
```
Assume we have recorded the conversion result of the microphone input in 15th storage location of the ADC. Which instruction correctly reads the result?
`int result = ADC14_getResult(ADC_MEM14);`
# Quiz 28
In a binary-weighted ladder D/A with n = 8, if the resistor attached to   
MSB is 256 kilo-ohm, what is the resistance of the resistor connected to LSB? ~33 Mega-ohm
In an R-2R ladder, the switch that is connected to the left-most resistor (the resistor that is connected directly to the voltage source) is controlled by which bit? MSB
How many resistors exist in an n-bit binary-weighted D/A converter? $n+1$
How many resistors exist in an n-bit R-2R ladder? $2n+1$
What is the ratio between the smallest resistor and the largest resistor in an n-bit binary-weighted ladder D/A? $2^{n-1}$
What is the ratio between the smallest resistor and the largest resistor in an n-bit R-2R ladder D/A? 2
Choose True/False regarding the below image.
1. IC is 1/3 of IA. F
2. Bz represents LSB. T
3. ID is twice IA. F
4. If Bx is 0, the switch is positioned on the right dotted line. T
5. If we wish to convert 110, the current going through the feedback resistor is 1.5* Iref. F
![[attachments/r2r.png]]
# Quiz 29
Which one of the below statements is true about S/H circuit?
1. At least two switches are needed to build the S/H circuit. True
2. The capacitor is needed to avoid a short in the S/H circuit. False
3. The resistor is not necessary for building the S/H circuit and it is only used to improve the quality of the design. False
4. The delay of the S/H circuit is increased exponentially when the size of the capacitor is increased linearly. False
5. The speed of the S/H circuit is increased when the size of the resistor is decreased. True
Consider a signal with a dynamic range of 50 mV. This means the difference between the minimum and maximum amount of this signal is 50 mV. If we like to feed this signal to an A/D where the Vref- is 0V and Vref+ is 3V, and n = 14. We need to amplify this signal before feeding it to the A/D. Among the below options, which one is the most suitable value for the gain of this amplifier? times 50
For a signal with the bandwidth of 1KHz, what is the minimum sampling rate that guarantees the sampled data is free of distortion, i.e. it is close enough to the original signal? 2000 samples per second
Assume you have used Equation 11 of chapter 22 in MSP432 user manual and based on the values at hand in your A/D setup, you have figured that the right side of the inequality is 1ms. What can you say about the sampling speed? It is less than or equal to 1000 samples per second.
Assume in an A/D the maximum possible sampling rate is 4000 samples per second. What is the maximum possible bandwidth of a signal we can sample without distortion? 2 KHz.
# Quiz 30
Between an A/D and D/A with the same number of bits, building an A/D is always more costly than D/A. True
What is the number of amplifiers needed in an n-bit A/D flash converter? $2^n - 1$
Which statements are true about SAR and flash converter?
1. They are both Analog to Digital converters. True
2. SAR is smaller but slower compared to the flash converter. True
3. SAR is both smaller and faster than the flash converter. False
For a SAR A/D  with n = 10, what is the first digital guess? 512
Mechanism of SAR implementation is based on binary search
For a 10-bit SAR resolving one bit takes 1us. In other words, one round of making a digital guess, D/A conversion, comparison with the analog input and finally making a decision about the bit at hand takes 1us. How long does it take to do a complete conversion of an analog input? always 10us.

Consider a 4-bit SAR converter with Vref+ = 2V  (Vref- = 0) similar to what is shown in the below figure.
![[attachments/SAR-1.jpg]]
If Vin, the input voltage, is 1.6 V, compute the values of the analog guess, VDAC for the 4 passes of the conversion, and provide the digital output by completing the following table. There is one row for each round of SAR, which is given in the first column. You need to enter the VDAC in the second column. You have to enter the index of the bit that is being calculated (resolved in this round) in the third column. This is going to be 0 for LSB and 3 for MSB and something in between for the other two bits. Finally, the last column is for the value of the resolved bit. So, if you decide the bit is 1, you put 1 for that column and 0, otherwise.

| Round | VDAC (Analog guess in Volts - a number with three decimal points rounded up) | Bit index (the bit that is resolved in this round) | Resolved bit value (0 or 1) |
| ----- | ---------------------------------------------------------------------------- | -------------------------------------------------- | --------------------------- |
| 1     | 1                                                                            | 3                                                  | 1                           |
| 2     | 1.5                                                                          | 2                                                  | 1                           |
| 3     | 1.75                                                                         | 1                                                  | 0                           |
| 4     | 1.625                                                                        | 0                                                  | 0                           |
# Quiz 31
Consider a processor that uses a Timer32 to generate PWM. Imagine a situation when the PWM is in the "on" cycle and the processor gets busy with another task, and therefore, is not able to change the "on" state to "off" state at the right moment. Nevertheless, the processor is not busy during the "off" cycle and switches back to the "on" cycle at the proper time. What happens to the PWM? The duty cycle of the PWM goes higher than the desired value.
1. We can use Timer32 to generate a square wave with a varying duty cycle (PWM). True
2. Using PWM is an expensive, but highly effective control solution for applications such as motor speed control, oven temperature control, etc. False
3. In order to know our exact location on earth, we use an accurate measurement of time (as in GPS). True
The PWM is NOT suitable for which of the below applications? steering a self-driving car
1. The best way to generate a PWM is to use the processor and a general timer such as Timer32 because the processor is very fast and accurate. False
2. The most accurate way to generate a PWM on our chip is using Timer_A, but using Timer_A is very expensive in terms of power and energy. False
- In the output-compare operation, when the pin reading matches a certain condition, the value of the counter is copied to the CCR register. False
- In the output-compare operation, when the counter value matches the CCR register value, the Timer_A drives the pin with a certain predefined value. True
- In the input-capture operation, when the pin reading matches a certain condition, the value of the counter is copied to the CCR register. True
- In the input-capture operation, when the counter value matches the CCR register value, the Timer_A drives the pin with a certain predefined value. False
- In MSP432, Timer-A has a dedicated register for output-compare and another dedicated for input-capture. False
# Quiz 32
Which one is true about TA0.4? It is connected to Pin 7 of Port 2.
Which one is NOT true about Red LED on the booster board?  It is driven by channel 0.3 of Timer_A
There are multiple timer_A modules on MSP432 SoC and each timer_A has several OC/IC channels.

Consider a Timer_A in the count-up mode with CCR0 = 4000 and CCR1 = 1000. Referring to Figure 19-12 of MCU user guide, fill the below table. The first row is given as an example.

| Output mode | Pulse starting state | Period (in cycles) | Duty cycle (0-100) |
| ----------- | -------------------- | ------------------ | ------------------ |
| Toggle/set  | High                 | 4000               | 25                 |
| Toggle      | Low                  | 8000               | 50                 |
| Set/Reset   | Low                  | 4000               | 75                 |
```c
typedef struct _Timer_A_PWMConfig  {  
	uint_fast16_t clockSource;  
	uint_fast16_t clockSourceDivider;  
	uint_fast16_t timerPeriod;  
	uint_fast16_t compareRegister;  
	uint_fast16_t compareOutputMode;  
	uint_fast16_t dutyCycle;  
} Timer_A_PWMConfig;
```
If the clockSource's frequency is 48MHz and we are interested to create a PWM to play a musical note B1 with the frequency of 61.74 Hz, what is the minimum acceptable prescaler value to be used for clockSourceDivider? Note: In our board, we use a PWM with the duty cycle of 50% that matches the frequency of the note to play it. (**Give your answer as a numerical value such as 1 as opposed to TIMER_A_CLOCKSOURCE_DIVIDER_1 for this problem.**)
12

If the clockSource's frequency is 48MHz and we are interested to create a PWM to play a musical note B1 with the frequency of 61.74 Hz, what is the minimum acceptable prescaler value to be used for clockSourceDivider? Note: In our board, we use a PWM with the duty cycle of 50% that matches the frequency of the note to play it. (**Give your answer as a numerical value such as 1 as opposed to TIMER_A_CLOCKSOURCE_DIVIDER_1 for this problem.**)
2250