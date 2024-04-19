| Launchpad Pin | RGB LED Pinout BoosterPack Module Header Connection | Pin Function  |
| ------------- | --------------------------------------------------- | ------------- |
| P2.6          | J4.39(1)                                            | Red channel   |
| P5.6          | J4.37                                               | Blue channel  |
| P2.4          | J4.38                                               | Green channel |

pg 7 boosterpack user guide

| Launchpad Pin | BoosterPack Plug-in Module Header Connection | Pin Function |
| ------------- | -------------------------------------------- | ------------ |
| P5.1          | J4.33                                        | S1 button    |
| P3.5          | J4.32                                        | S2 button    |
pg 8

---

| Launchpad Pin | Pin Function |
| ---- | ---- |
| P1.1 | Button 1 |
| P1.4 | Button 2 |
| P1.0 | LED 1 |
| P2.0 | RED LED |
| P2.1 | GREEN LED |
| P2.2 | BLUE |
pg 37 MSP user quick guide
# adresses
| type | port 1 | port 2 | port 3 | port 5 |
| ---- | ---- | ---- | ---- | ---- |
| PxIN | 000_4C00 | 000_4C01 | 000_4C20 | 000_4C40 |
| PxOUT | 000_4C02 | 000_4C03 | 000_4C22 | 000_4C42 |
| PxDIR | 000_4C04 | 000_4C05 | 000_4C24 | 000_4C44 |
| PxREN | 000_4C06 | 000_4C07 | 000_4C26 | 000_4C46 |
more starting from pg 100 of MCU datasheet
pg 684 of MCU reference manual for detailed register addresses

# Joystick
## x
ADC_INPUT_A15
PORT_P6
PIN0
## y
ADC_INPUT_A9
PORT_P4
PIN4