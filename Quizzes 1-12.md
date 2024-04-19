# Quiz 1
What percentage of computer systems are embedded systems as opposed to general-purpose computers? 99-1
A computer is a device that has a keyboard and a monitor and can run arithmetic and logical operations. FALSE
All computer systems are embedded systems. FALSE
All embedded systems are computer systems. TRUE
Embedded systems always use low-end microcontrollers rather than high-end microprocessors. FALSE
# Quiz 2
Order the below abstraction levels from low to high:
atoms
transistors
gates
digital circuits
architectural units such as cash, register file, FIFO, ALU
system components such as cpu, UART, RAM

Which file types are mostly or entirely in machine language binary and unintelligible to humans?  Choose U for unintelligible and I for intelligible. 
1. C file I
2. Assembly file I
3. Object file U
4. Executable file U
The tool that translates high-level language to assembly is called **compiler**.
The tool that combines object files to create one executable is called  **linker**.
The tool that translates assembly to machine code is called **assembler**.
The compiler that is used inside CCS (Code Composer Studio) for compiling C code to be executed on the MPS432 chip is a native compiler. FALSE
If you write a Python script and use your computer to interpret and run the script, you are using a native compiler. TRUE
When you develop code for a drone on your tablet and send the executable to the drone, you are using a cross compiler. TRUE
# Quiz 3
MCU (Microcontroller unit) consists of a CPU (Central Processing Unit), memory and some other peripherals. TRUE
Is any of the following components part of MSP432 MCU?
1. simple peripherals such as buttons and LEDs NO
2. Blocks that are in charge of reset, clock, and power YES
3. Several timers YES
4. Different types of memory YES
5. Analog interface including ADC (Analog to Digital Converter) YES
6. Digital interface including UART SPI, I2C, I/O ports YES
7. CPU YES
XDS110 is the is the emulator on the launchpad board that helps program/debug the main microcontroller whereas MSP432 is the main microcontroller on the Launchpad board .

For each of the below components, choose if they are located on the BoosterPack (B), the Launchpad (L), or the MSP432 chip (M).
(Note: We know MSP432 is on the Launchpad and anything on the MSP432 chip is on the Launchpad as well. We also know that BoosterPack is connected to and sits on top of Launchpad and therefore, in a way anything on BoosterPack, is on the Launchpad as well. For the purpose of this question, if a component is on MSP432 or the BoosterPack, choose these two rather than the Launchpad. Choose Launchpad only if the component is sitting directly on Launchpad.)
1. Joystick B
2. ADC (Analog-to-Digital Converter) M
3.  Large round S1 and S2 push buttons B
4. Timer_A M
5. Timer32 M
6. UART M
7. micro-USB port L
8. Debugger chip L
Are the below types of memory included on MSP432? 
1) ROM Yes
2) SRAM Yes
3) Flash memory Yes
# Quiz 4
Which ones are acceptable ways to declare a pointer?
- int *a; acceptable
- int &a; not acceptable
- int a*; not acceptable
- int a&; not acceptable
# Quiz 5
```c
void WorkwithBunch(bunch_t *inputBunch_p);

bunch_t myBunch = {1,12,1};
bunch_t *bunchPtr = &myBunch;

WorkwithBunch(bunchPtr);
```

```c
void WorkwithBunch(bunch_t inputBunch_p);

bunch_t myBunch = {1,12,1};
bunch_t *bunchPtr = &myBunch;

WorkwithBunch(*bunchPtr);
```

```c
void WorkwithBunch(bunch_t *inputBunch_p)
;
bunch_t myBunch = {1,12,1};
WorkwithBunch(&myBunch);
```
# Quiz 6
Which one of the following numbers can fit in a 2's complement 16-bit register? -2^15
How many bits in a signed character? 8
How many bits in an integer (MSP432)? 32
Does adding 0x0fffefee and 0x0efffffff result in an overflow? insufficient information
What is the lowest number that can be stored in a signed short? (Hint: A C short is two bytes.) -2^15
What is the highest number that can be stored in an unsigned long? (Hint: A C long is four bytes.) 2^32-1
Consider the below code:
```c
 #include <stdio.h>  
    int main()  
    {  
        int i = 39;  
        char c = 'd';  
        printf("%d, %d, %d\n", sizeof(i), sizeof(c), sizeof(c + i));  
        return 0;  
    }
```
What is the expected output? 4, 1, 4
# Quiz 7
Which one is bit 23 mask (BIT23)? (1<<23)
Assume oldStatus and updatedStatus are two integers. Which code segment sets bit 4 to **one**, **toggles** bit 5 and resets bit 6 to **zero**? (Bit 0 is the Least Significant Bit) 
```c
#define bit4_mask (1<<4)  
#define bit5_mask (1<<5)  
#define bit6_mask (1<<6)  
  
updatedStatus = oldStatus | bit4_mask;  
updatedStatus = updatedStatus & ~(bit6_mask);  
updatedStatus = updatedStatus ^ bit5_mask;
```
A single-bit bitmask is a bitstring where all the bits are 0 except for a single bit, which is 1. If that single bit is located at index i, we call the bitmask BITi. For example, BIT0 is equal to 1 and BIT1 is equal to 2 and BIT2 is equal to 4, and so on. If we intend to reset bits 10 and 20 of an integer, and we like to create a macro mask, what should go in the blank space below?. If we intend to reset bits 10 and 20 of an integer, and we like to create a macro mask, what should go in the blank space below?
```c
#define NEW_MASK ....  
x = x & ~NEW_MASK;
```
(BIT10 | BIT20)
Which one is the bit 4 mask? 2 to the power of 4 (2^4 in mathematical form)
Which expression could be untrue if the nth bit of the integer a is 0? ((a>>n) == 0)
A C expression to compute a * 19 (a times 19) is: (Recall that one time shift to left doubles an integer. ) (a << 4) + (a << 1) + a;
For each of the below lines of C code decide whether test is true or false after that line is executed. **For all these examples assume x is 3 before this line of code.**
1. test = (x <= 5) ; True
2. test = (x = 5) ; True
3. test = (x - 5) ; True
4. test = (x - 3) ; False
5. test = 0x10 & 0x1; False
6. test = x & BIT1; // test is true if x's bit at index 1 is 1. TRUE
7. test = (x & BIT0) || (x & BIT2); // test is true if x's bit at index 0 or 2 is 1. TRUE
8. test = !(x &BIT2); //test is true if the bit at index 2 is 0. True
# Quiz 8
Two gates cannot share a certain wire as their output as it may cause a short in the circuit.
Select True/False:
- T A port is a combination of pins. TRUE
- F MSP432 has 1 port, but many pins. FALSE
- F A port is used as output and a pin as input. FALSE
- F Port and pin are two names of the same thing. FALSE
Choose T/F.
1. In MSP432, a digital I/O cannot be used for any other purpose such as an analog input. FALSE
2. In MSP432, any digital I/O pin can be configured to be a digital input. TRUE
3. In MSP432, any digital I/O pin can be configured to be a digital output. TRUE
![[Pasted image 20240219001322.png]]
This creates a short and the voltage changes rapidly while creating a large spike in the current.
# Quiz 9
**multiplexer** selects a certain input among multiple inputs, **tri-state buffer** is able to cut off a path in the circuit and **schmitt trigger** can act as a basic analog to digital converter.
In MSP432, a digital input can use any of these three options: 1) attached pull-up resistor, 2) attached pull-down resistor, 3) no attached resistor. TRUE
Consider a Schmitt trigger with two thresholds at 1.4V and 1.6V. Also, assume the logic 0 is 0V, and logic 1 is 3V. 
1. What is the output of the Schmitt trigger when the input is 0.2V? 0V
2. What is the output of the Schmitt trigger when the input is 1.55V? We cannot tell. It depends.
3. What is the output of the Schmitt trigger when the input is 2.33V? 3V
Consider the two below setups for a pushbutton. In order for them to work properly which statement should be correct?
![[Pasted image 20240219001502.png]]
1. Configuration A needs a pull-up resistor. .
2. Configuration B needs a pull-down resistor. .
In an MSP432 digital I/O module, there are one Schmitt triggers, two 2-input logic gates, three multiplexers, and three  components that act as switches (tri-state buffers, latch with enables, etc.)
1. In MSP432, the configuration of a single digital I/O pin depends on the values of several registers. T
2. In MSP432, one register can affect the configuration of multiple digital I/O pins. T
3. In MSP432, each digital I/O pin has a dedicated register that controls its configuration. F
In MSP432,
- if we wish to configure a pin as an input with a pull-down resistor, DIR register should be 0 , REN register should be 1 , and OUT register should be 0 .
- if we wish to configure a pin as an output, DIR register should be 1 , REN register does not matter , and OUT register does not matter 
Pick T/F.
1. In MSP432, the configuration of a single digital I/O pin depends on the values of several 8-bit registers. T
2. In MSP432, one 8-bit register can affect the configuration of multiple digital I/O pins. T
3. In MSP432, each digital I/O pin has a dedicated register that controls its configuration. F
# Quiz 10
1. One single port has multiple memory addresses that are associated with different pins. F
2. One single port has multiple memory addresses that are associated with different functionalities. T
3. One single port has one single memory address. F
4. One single pin has one single memory address. F
Consider [typical 32-bit and 16-bit microcontrollers](https://sites.google.com/vt.edu/introduction-to-embeddedsystem/digital-io/memory-mapped-io) and choose which of the below statements are true or false.
1. The datapath of a 32-bit microcontroller is twice as wide as a 16-bit microcontroller. true
2. The address bus of a 32-bit microcontroller is twice as wide as a 16-bit microcontroller. true
3. The Registers of a 32-bit microcontroller have twice as many bits as a 16-bit microcontroller. true
4. The ALU of a 32-bit microcontroller is capable of handling operands that are twice as wide as a 16-bit microcontroller. true
5. The address space of a 32-bit microcontroller is twice as big of a 16-bit microcontroller. false
Choose T/F:
1. In memory-mapped i/o, peripherals and memory certainly share a physical address bus. F
2. In memory-mapped i/o, peripherals and memory certainly share the same address space. TRUE
3. In memory-mapped i/o, the processor uses the same instruction for reading from memory and reading from an i/o. (In other words, the processor "thinks" it is dealing with memory when it deals with i/o.) TRUE
# Quiz 11
1. In MSP432, the configuration of a single digital I/O pin depends on the values of several registers. T
2. In MSP432, one register can affect the configuration of multiple digital I/O pins. T
3. In MSP432, each digital I/O pin has a dedicated register that controls its configuration. F
The red LED on the booster is connected to which BoosterPack pin? J4.39
When programming the buttons on the boosterPack, the buttons do not need pull-up or pull-down resistors from within MSP432's GPIO. In other words, PxREN should be equal 0.
Imagine we are programming a new switch to work with MSP432. This switch is connected to P2.6. When this switch is pressed, it reads a logic 1 (VCC) but when it is released, it is high impedance. What is a suitable line to define the appropriate bitmask for this switch?
`#define S3_MASK (1<<6)`
For the same switch as the above question, which block of code initializes it to properly work as a switch (button)?
```c
*P2DIR_address &= ~S3_MASK;   
*P2REN_address |= S3_MASK;   
*P2OUT_address &= ~S3_MASK;
```
For the same switch problem as the above two questions, assume we have declared a variable as below:
`char pressed;`
Our goal is that the above variable is 1 when the switch is pressed and 0 when it is not pressed. Which one of the below snippets are acceptable to achieve this goal. 
- option 1 not acceptable
`pressed = !(*P2IN_address & S3_MASK);`

- option 2 not acceptable
`pressed = !(*P6IN_address & S3_MASK);`

- option3 acceptable
```c
if (*P2IN_address & S3_MASK)  
     pressed = 1;  
else   
     pressed = 0;
```

- option4 not acceptable
```c
if (*P6IN_address & S3_MASK)  
     pressed = 1;  
else   
     pressed = 0;
```

- option5 acceptable
`pressed = ((*P2IN_address & S3_MASK) == S3_MASK);`

- option6 not acceptable
`pressed = ((*P6IN_address & S3_MASK) == S3_MASK);`
1. A programmer is not able to change the functionality of a digital I/O after the chip is manufactured with a certain configuration. F
2. A programmer is not able to change the functionality of a digital I/O after the chip is placed on a PCB board with certain peripherals and a specific configuration. F
3. A programmer is able to change the configuration of a digital I/O at any time. T
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
