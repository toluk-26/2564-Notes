# C
## printf data types
| printf ref | data type     |        |
| ---------- | ------------- | ------ |
| %d or %i   | int           | 32     |
|            | short         | +-2^15 |
| %f         | float, double |        |
| %p         | address       |        |
| %u         | unsigned int  |        |
| %lu        | unsigned long |        |
| %l         | long          |        |
| %c         | char          |        |
these are stackable, from \[type] \[type] \[unsigned]
## pointers
`var* varname` will hold an address to something a variable
`&varname` will report the `varname` address

think of \* as "point to" and & as "address of"
```c
int* ptr = &x;
```
> ptr points to the address of x

```c
*ptr = 200;
```
> point to ptr 200
```c
printf("%d\n", *ptr)
```
> prints 200 "go to ptr"
> 
```c
printf("%p\n", ptr)
```
> prints x address

## string length
`strlen( char );`
# CCS
## pull down vs pull up
With a **pull-up resistor** and with the button unpressed you make a logic state ON and with the button pressed you make a logic OFF.

With a **pull - down resistor** and a pressed button you make an ON logic state and OFF logic state when its unpressed.
from [instructables](https://www.instructables.com/Understanding-the-Pull-up-Resistor-With-Arduino/)
## Snippets
### Read (lec 6)
`x = *PIDIR_addr & LED1_mask; `
`y = *PIDIR_addr & S1_mask`

### Write
`x = *PIDIR_addr |= LED1_mask; `
`y = *PIDIR_addr &= ~SI_mask`
### Mask
LED1 port1 pin0

LED_red port2 pin0
LED_green port2 pin1
LED_blue port2 pin2

button1 port2 pin1
button2 port2 pin4
# Timer
[SW Timer Calculations](https://sites.google.com/vt.edu/introduction-to-embeddedsystem/timers/periodic-timer-calculations?authuser=0)
$T_{2}-T_{1} = C_{1}-C_{2}$ No Rollovers
$T_{2}-T_{1} = (N+1)+(C_{1}-C_{2})$ 1 Rollover
$T_{2}-T_{1} = (R_2-R_1)(N+1)+(C_{1}-C_{2})$    2$^T$ Rollover
t is the system clock, C is the counter
N is the Load value
R is the number of rollovers at T$_2$ 
# baud Rates
pg 915 of MCU reference manual
pg 12 mod15
f$_{clock}$ =48\*10$^{6}$
baudrate = 57600
$N= \frac{f_{clk}}{baudrate}=833.333$
UCBRx = INT$(\frac{N} {16})$
UCBRFx =INT\[ ($\frac{N}{16}-$ INT$(\frac{N} {16})*16$) \]  = 1

[baudrate calculator](https://software-dl.ti.com/msp430/msp430_public_sw/mcu/msp430/MSP430BaudRateConverter/index.html)
use EUSCI
custom -> 48000000

isc vs spi vs uart
== vs =
fsm
debouncing
baudrate, parity, etc

# timer32
largest number is $2^{32}-1$ , where 32 is the option 32 bit or 16bit
for larger values use a rescaler 
$T = \frac{N*f}{P}$ T is the period, N is the clock cycles, f is the clock frequency and P is the prescaler
## init
```c
  Timer32_initModule( TIMER32_0_BASE,  // There are two timers, we are using the one with the index 0
					  IMER32_PRESCALER_1,  // The prescaler value is 1; The clock is not divided before feeding the counter
					  TIMER32_32BIT,  // The counter is used in 32-bit mode; the alternative is 16-bit mode
					  TIMER32_PERIODIC_MODE);  // This options is irrelevant for a one-shot timer

Timer32_setCount(TIMER32_0_BASE, ON_CYCLES);
Timer32_startTimer(TIMER32_0_BASE, true);
```
not always accurate
# Timer A
![img](https://github.com/toluk-26/2564-Notes/blob/main/attachments/Pasted%20image%2020240418230433.png) pg791 of mcu tech
pg792-794 has **make sure output example title matches question** 

CCR0 is period
CCR1 is when to toggle or whatever
# ADC
$D=\frac{V_{in}-V_L}{V_H-V_L}*2^n$
D is the digital output
Vin is the analog input
n is the number of bits
VH is the highest value
VL is the lowest value
round down
## binary search

# DAC
$V_{out}=\frac{D}{2^n}*(V_H-V_L)+V_L$
D is the decimal equivalent
span $V_H-V_L$
resolution $\frac{V_H-V_L}{2^n}$
## binary weighted ladder
![](https://github.com/toluk-26/2564-Notes/blob/main/attachments/Pasted%20image%2020240418225525.png)
only useful in 8 bits are fewer
## R-2R ladder
![[attachments/Pasted image 20240418225750.png]]
![[attachments/Pasted image 20240418225649.png]]