This is the file containing details on the electronics of the Bipedal Model.

The components are listed under [Components](components.md).

## Overview of Key Components:  
1. **11.1 V Battery**: provide 11.1 V ouput Voltage via Amass Nylon T charge port, then we connect it using the male connector, use 14 AWG wire to connect it with Step-Down Power Supply Module  
2. **LM317**: adjust and check with multimeter to provie stable 5V supply, might debate to purchase a heatsink  
3. **Rasberry Pi Pico**: 5V supply(from XL4016E1) with 5V pin and GND, and connect servo motors signal line using jumper wires  
4. **MG995**: connect with 6-6.5V supply from XL4016E1 to connect power to servos. Signal line connected to GPIO PWM pin (6 separate pins)
5. **MPU6050**: Pico 3V3 output to connect power. SDA and SCL to GP 6 and 7.
6. **ADS1115**: Pico 3V3 output to connect power. SDA and SCL to GP 6 and 7 (NOTE: use different I2C addresses for gyro and adc)
7. **PDB181**: Pico 3V3 output to connect power. Wiper to ADS analog input pins (A0-A3)
    
