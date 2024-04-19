# Quiz 12
When writing the main function (or a high-level function) for a processor to work with its a peripheral, we are considering three different approaches:
1. Using memory-mapped registers: Directly reading from or writing to memory-mapped registers of that peripheral. (similar to noHAL_noDriverlib example)
2. Using the driver library: Calling the library of functions written by the vendor or others for that peripheral. For our case, this would be DriverLib from TI. (similar to noHAL_Driverlib example)
3. Using HAL: Calling HAL functions that we have developed without the use of the Driver library. (similar to HAL_noDriverlib example)
For each of the above programming methods, choose whether the high-level code can be easily ported from one processor, such as MSP432, to another processor, such as PIC32.
1. noHAL_noDriverlib: not portable
2. noHAL_Driverlib: not portable
3. HAL_noDriverlib portable
Choose T/F from the drop-down menu:
1. API is a special form of HAL. False
2. HAL is a special form of API. True
3. HAL functions can be found in the driverlib manual. False
4. We can use driverlib functions to develop (implement or write the code for) HAL. True
5. HAL stands for Hardware Abstraction Level. False
6. Driverlib is a form of API. True
7. Driverlib is a form of HAL. False
What is the reason to use HAL? Choose "yes" for all that applies.
1. It makes the code more readable. yes
2. It makes the code easier to port from one processor to another. yes
3. It reduces the size of the machine code binary after compilation. no
4. It improves the efficiency of the program (e.g. it becomes faster or uses fewer resources.) no
# Quiz 13
The graphics context is only used once during initialization and then, you do not need to refer to it. FALSE
(x,y) = (0,0) is located at the top left of the LCD screen
(x,y) = (0,127) is located at the bottom left of the LCD screen
(x,y) = (127,0) is located at the top right
(x,y) = (127,127) is located at the bottom right of the LCD screen
Find the \#define for the color PAPAYA_WHIP in the grlib.h file.
What are the 8 bit values for the blue, green and red components of this color?
blue: 0xD5
green: 0xEF
red: 0xFF
The expression to produce a color mask as mentioned in lecture can be written as:
(color1 << shift1) | (color2 << shift2) | color3
Select the correct values from the drop-down menu in the below expression to produce the color TOMATO, as defined in grlib.h to match the above formula.
(0xFF << 16 ) | (0x63 << 8 ) | 0x47
# Quiz 14
What can you say about FSM? Choose between T/F.
1. FSM stands for Finite State Machine. T
2. FSM is a mathematical model of computation. T
3. FSM is an abstract machine. T
4. FSM is the C code that implements a certain algorithm. F
5. FSM is a mechanical machine that is capable of doing calculations.F
6. FSM is a machine that can go into an infinite number of states. F
7. FSM is defined by a list of states, an initial state, and conditions for transitions between the states. T
8. An FSM is weaker than the combinational logic model. F
9. Some examples of the behavior of an FSM are traffic lights, vending machines, and elevators. T
10. An FSM is more powerful than the Turing machine.F
Consider the below figures. Answer this and a few following questions: What is the number of inputs of this FSM? 2 inputs
![[FSM-1.png]]

For the same FSM as above, what is the number of outputs? 2
For the same FSM as above, what is the number of states? 5
For the same FSM as above, what is the number of transitions? 7
In the same FSM, if the current state is S4 and the key = 5 and S = true, then what is the next state? S1
In the same FSM, starting from the initial state, assume the following series of inputs are given to the FSM. 

key = 5 and S = true
key = 5 and S = false
key = 2 and S = false

What is the final output at this point? Green Square
![[LED FSM v1.jpg]]
![[Code FSM v2.png]]
# Quiz 15
1. A static in C is a variable that is constant and does not change. F
2. A static variable is stored on the stack. F
3. A static variable defined within function Func1 can be accessed from outside Func1 by other functions. F
4. A static variable defined within function Func1 holds its value after Func1 finishes. The next time Func1 starts the old value of the static variable is still available. T
- Static variables are similar to pointers except that they point to a static part of the memory. F
- Static variables are similar to global variables in the sense that they stay in the same location in the memory throughout the program execution regardless of which functions are called. T
In the lock FSM we covered in class, how many rounds of calling the FSM function does it take to go from Sx state back to Sx state? (count like this: it takes one round to go to either S1R or S1W, ...) 5
In the FSM we covered in class, what causes the "unlock" variable to become true?
When you are transitioning from state S3R to S4R, the unlock variable becomes true.
# Quiz 16
- Switch debouncing is some form of signal filtering. T
- When we press a button, the two metals of the button do not create instant contact, instead, they connect and disconnect several times until they settle in the pressed state and remain connected. T
- There is only one method to debounce a button. F
- Switch debouncing is some form of signal amplification. F
- Switch debouncing creates the illusion of a perfect switch to the user.
- In an FSM, it is possible that some inputs are Don't Care for some of the transition arcs. T
- It is possible to use analog components such as resistors and capacitances to debounce a switch. T
- The debouncing method described in class requires a timer. T
Which of the following are benefits of modular programming?
- produces more reusable code
- easier to maintain and modify
- easier to test
- facilitates collaboration
All macros, structs, and enums should be in a .h file. False
Function definitions are contained in .c files. True
# Quiz 17
SPI is **full-duplex** , I2C is **half-duplex** , and UART is **full-duplex** .
SPI is **serial** , I2C is **serial** , and UART is **serial** .
SPI is **synchronous** , I2C is **synchronous** , and UART is **asynchronous** .
Consider a communication scheme where each symbol (baud) represents two bits. If the bitrate in this communication is 10 Kbit/sec, what is the baudrate? 5K
Consider a communication scheme where the bitrate is 1 Mbit/sec. The bits are packaged as packets of 20 bits, where 4 bits are used to specify the start and stop of the package and other protocol-related information. The rest of the bits are data bit. What is the data rate (in bits per second)? 0.8 M
What is the odd parity for this 8-bit piece of data 10101111? 1
What is the even parity for this 8-bit piece of data 11101111? 1
We know a communication scheme is using odd parity for error checking and each package of data is one byte (8 bits). For each of the below packages that the receiver gets, please confirm if corruption has occurred **based on parity analysis** or not.
- 001011011 no corruption
- 110101101 corruption
# Quiz 18
What are the number of bits in a UART packet of data with the default number of start bits, 8 data bits, 2 stop bits, and no parity bits? 11
- In UART, sender, and transmitter share a clock signal. F
- In UART, baud rate is equal to bit rate. T
- In UART, bit rate is equal to data rate. F
- UART is asynchronous. T
- UART is always half-duplex. F
- UART has two data lines between the two sides of the communication. T
Assume we are transmitting single bytes with a parity bit. Choose T/F.
1. When sending ASCII of 'L', the odd parity is 0. True
2. When sending 0x23, the even parity is 0. False
3. When sending the decimal 0, the odd parity is 1. True
In a UART where the BRCLK's frequency (BRCLK is the input clock of the UART counter) is 500KHz and Baudrate is 115200, what are the integer part and the fractional part of the division factor (the potential load value of the counter)? 4 and 0.34
When is the ideal time for sampling the data of a bit?  In the middle of the data bit.
A UART module shares a clock with the processor core that is 4MHz. The Baudrate is set at 10,000 baud/sec. What is the length of time the UART has to wait between sampling two consecutive bits? 1ms
A UART uses Baudrate of 100 K Baud/sec. The counter inside the UART uses a 1MHz clock as its input, how long after the beginning of the start bit (the falling edge moment), we should sample the first data bit? 15us
For a UART module with (8N1) format (which means 8 data bits, No parity and 1 stop bit), and Baudrate of 1000 Baud-per-second. Assume the channel is used at its full capacity. choose all the true statements:
1. The bitrate is 1000 bit/sec. True
2. The data rate is 1000 bit/sec. False
3. The data rate is 800 bit/sec. True
4. The bitrate is 2000 bit/sec. False
# Quiz 19
1. Launchpad has a dedicated serial port for UART communication. F
2. Most modern laptops have a dedicated serial port for UART communication. F
3. The UART frame arriving at Launchpad port is routed directly to MSP432. F
4. MobaXterm is an application that provides a variety of communication terminals including serial (UART). T
5. XDS11 receives a USB package from the Launchpad USB port and converts it to a UART frame before passing it to MSP432. T
According to the Launchpad schematics, XDSET_RXD is directly across P1.3_BCLUART_TXD and is connected to it when a jumper is present.
According to MCU datasheet, P2.2 is connected to what eUSCI module? UCA1 (also called eUSCI_A1)
According to MSP432 datasheet, is it possible for P2.3 to have the below roles? Choose Y/N
1) RXD (Rx of UART) N
2) TXD( Tx of UART) Y
3) SIMO (SIMO of SPI) Y
4) SOMI (SOMI of SPI) N
According to MSP432 (MCU) datasheet, if we would like to configure P5.1 to function as A4 (an analog signal) what function we should use?
`GPIO_setAsPeripheralModuleFunctionInputPin( GPIO_PORT_P5, GPIO_PIN1, GPIO_TERTIARY_MODULE_FUNCTION);`
Which one of the below components is part of a UART module on MSP432? Choose between  "Yes" and "No"
1. Transmit State Machine Yes
2. Transmit shift register Yes
3. Receive shift register  Yes
4. Baud rate generator Yes
5. The error flag generator Yes
6. Transmit and Receive buffers Yes
# Quiz 20
not found
# Quiz 21
proj1 related stuff
# Quiz 22
What is the clock frequency of a processor whose clock period is 1ms? 1 KHz
In terms of seconds, how long is 2 million cycles of a processor with a clock frequency of 1MHz? 2s
For a processor with a clock frequency of 1 GHz, how many cycles exist in 3 seconds? 3,000,000,000
1) GPS depends on timers for accurate determination of one's location on earth. T
2) Controlling the dimness of an LED light can be done using a timer. T
3) Controlling the temperature of an oven can be done using a timer. T
4) Controlling the speed of a servo motor can be done using a timer.T
Consider the below code, part of the example we covered in class. Which portion of the main function code is compiled and turned into an executable when we compile the code? Assume the macro Timer32 is defined earlier in the code.
![[Screenshot 2021-03-08 163029.png]]
The entire main function except for line 81 to 86.
Choose if any of the below computer systems is working under real-time constraints or not?
A small microcontroller implementing the anti-lock brake system of a car. yes
A massive supercomputer which is performing modeling the three-dimensional structure of the Earth for earthquake simulation. no
The MCU inside a joystick that handles the joystick operations. yes
A microcontroller inside an electric toothbrush that signals the user to move to another area of the mouth for brushing. yes
If the system clock frequency feeding a timer is 4MHz and the Prescaler value is 16, what is the counter clock period? 4 us
A 16-bit periodic count-down timer uses a clock source of 2KHz and a clock divider of 2, choose the proper options for 
1. How much is the frequency of the clock that feeds the counter inside this timer? 1 KHz
2. What is the largest Load value for this timer? 2^16 - 1
	2^n - 1
3. Based on the answer to part 2, how long is this periodic timer's longest period? 65.536 s
$\frac{P(2^n-1)}{f} = \frac{2 * (2^{16}-1)}{2000}$
# Quiz 23
Timer32 is a new peripheral such as digital i/o that we have studied so far. Select Y (Yes) if any of the following resources can be used for learning about Timer32:
1) Dirverlib guide Y
2) MSP432 user guide Y
3) Launchpad user guide N
4) timer32.h Y
**Assume the system clock is clocked at** 3000000 Hz.  
**Assume the following lines are used to initialize a Timer32.**  
`Timer32_initModule(TIMER32_0_BASE,  **UNKOWN**,  TIMER32_32BIT,  TIMER32_PERIODIC_MODE);'
**Assume the following lines are used to start the timer in the one-shot mode.**   
`Timer32_setCount(TIMER32_0_BASE, 12000);`  
`Timer32_startTimer(TIMER32_0_BASE, true);`
**If we wish for the timer to expire after _about_ 1s, what should be used for the UNKOWN value in the init function?** 
TIMER32_PRESCALER_256
Assume the source clock of a Timer32 module is 16MHz. Assume the following lines of codes are used to initialize the Timer32:
`Timer32_initModule(TIMER32_0_BASE,   
 ``                  TIMER32_PRESCALER_1,   
 ``                  TIMER32_32BIT,   
 ``                  TIMER32_PERIODIC_MODE); `
Assume the following lines are used to start the timer.
`Timer32_setCount(TIMER32_0_BASE, 32000);   
`Timer32_startTimer(TIMER32_0_BASE, true); `
How long does it take for the timer to expire from the time it is started **in microseconds**? (no partial credit will be given) 2000
For Timer32, the largest possible Prescaler value is 256 and the smallest Prescaler value is 1. What is the longest interval **(in seconds)** Timer32 can measure if the system clock frequency (the one that feeds the timer) is 48MHz? Give your answer as a rounded integer +/1 error is acceptable. 22,906
# Quiz 24
Software timers can be used to measure much longer time periods than hardware timers. T
You can have an unlimited number of software timers. T
In the Guess-the-Color project, Timer.h can be found in the HAL folder. T
How do we initialize a SW timer to wait for 8 seconds? `SWTimer_construct(8000)`
Using the diagram below, determine the values of the following variables at the moment of Event 2 within the function SWTimer_elapsedCycles(SWTimer* timer_p).
hwTimerRollover = 3
timer_p->startRollovers = 1
currentCounter = 900
timer_p->startCounter = 300
SWTimer_elapsedCycles = 1400
$(C_1-C_2) + (R_2-R_1)(N+1) = (300-900)+(3-1)(999+1)$
![[L22-1.png]]
Which of the following is the correct way to start the SW timer defined earlier in the code as blinkingTimer? `SWTimer_start(&blinkingTimer);`
A 16-bit periodic count-down timer uses a clock source of 2KHz, the clock divider of 2, and the load value is 9999. Once an event, e1, happens, the light should turn on and stay on for 3 seconds. If the counter value when e1 happens is 2000 and we immediately turn on the light, what should be the counter value when we have to turn off the light (after 3 seconds)? 9000
Consider a periodic counter in the count-down mode. The counter value at the time of events, e1 and e2 were c1, and c2 respectively. What can we say about e1, e2, c1, and c2? C1 is can be either more than or less than C2 if e1 happens before e2.
Consider a periodic timer in count-down mode where the Load value is 11,999. The counter value at the time of e1 (first event) and e2 (second event) is 5000 and 2000 respectively and three rollovers have happened between the two events. How many counter **_cycles_** has it elapsed between the two events? 39000
A 16-bit periodic count-down timer uses a clock source of 2KHz and clock divider of 2, choose proper options for 
1. How much is the frequency of the clock that feeds the counter inside this timer? 1 KHz
2. What is the largest Load value for this timer? 2^16 - 1
3. Based on the answer to part 2, approximately, how long is the longest period for this periodic timer? 65.536 s
4. Assume the Load value is set at 999 and no rollover has happened between events, e1 and e2. If the counter reading (the value inside the counter) for the two events, c1 and c2, are 550 and 200, how long has elapsed between the two events? 350 ms
5. Assume the load value is 9999. Once an event, e1, happens, the light should turn on and stay on for 3 seconds. If the counter value when e1 happens is 9000 and we immediately turn on the light, what should be the counter value when we have to turn off the light (after 3 seconds)? 6000
rollover counts for one cycle