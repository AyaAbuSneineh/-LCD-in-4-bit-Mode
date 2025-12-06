# LCD 16x2 Driver in 4-Bit Mode (No Libraries)

This project implements a custom low-level driver for a 16×2 LCD using **4-bit communication mode** on Arduino.  
All LCD operations (initialization, commands, data write, and text scrolling) are implemented manually without using any external libraries.

## Features
- Manual 4-bit initialization sequence
- Send commands and data to LCD
- Custom `lcd_print()` function
- Smooth scrolling text animation
- Pure low-level control of RS, E, and data lines

## Pin Connections

| LCD Pin | Function | Arduino Pin |
|--------|----------|-------------|
| RS     | Register Select | 12 |
| E      | Enable          | 11 |
| D4     | Data bit        | 5 |
| D3     | Data bit        | 4 |
| D2     | Data bit        | 3 |
| D1     | Data bit        | 2 |

## How It Works
The project manually:
1. Sends data in **two 4-bit nibbles**
2. Toggles the Enable pin to latch each nibble
3. Handles the official LCD initialization sequence
4. Implements `lcd_command`, `lcd_data`, and `lcd_print`
5. Scrolls the text “HELLO AYOOSH” using command `0x18`
##  Simulation (TinkerCad)

You can view and test the full circuit and code on TinkerCad:  

 *TinkerCad Project Link:*  
*https://www.tinkercad.com/things/aw8ezS5sCxe-q4ass/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits*
