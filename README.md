# Custom-STM32-H7B0VB

A custom development board built around the STM32H7B0VB (LQFP100) as part of the Formula Student Team Formula Manipal. The goal is building a bare-bones test board to later be embedded into multiple other PCBs such as the Vehicle Control Unit, Accumulator Management System and other important PCBs that go onto the car.

The board contains one instance each of UART, I2C, SPI and CAN, plus analog, PWM-capable digital pins and two LEDs. Special care has been taken to assign each pin/LED a different PWM timer for each to be capable enough to run at it's own frequency.

## Complete Pinout:
### 1. Communication protocols

| Interface     | GPIO Pin | Function | Physical Pin |
| ------------- | -------- | -------- | ------------ |
| UART (USART1) | PA9      | TX       | 68           |
|               | PA10     | RX       | 69           |
| I2C (I2C1)    | PB8      | SCL      | 95           |
|               | PB9      | SDA      | 96           |
| SPI (SPI2)    | PB13     | SCK      | 52           |
|               | PB14     | MISO     | 53           |
|               | PB15     | MOSI     | 54           |
|               | PB12     | CS       | 51           |
| CAN (FDCAN1)  | PD0      | RX       | 81           |
|               | PD1      | TX       | 82           |
| USB           | PA11     | D−       | 70           |
|               | PA12     | D+       | 71           |

### 2. Digital I/O and PWM

All seven pins have independent timer assignments.

| GPIO Pin | Physical Pin | Function    | Timer / Channel |
| -------- | ------------ | ----------- | --------------- |
| PE5      | 4            | LED1 / PWM  | TIM15_CH1       |
| PB0      | 34           | LED2 / PWM  | TIM3_CH3        |
| PA8      | 67           | Digital PWM | TIM1_CH1        |
| PC9      | 66           | Digital PWM | TIM8_CH4 (AF3)  |
| PA6      | 30           | Digital PWM | TIM13_CH1       |
| PA7      | 31           | Digital PWM | TIM14_CH1       |
| PD12     | 59           | Digital PWM | TIM4_CH1        |

PC9 uses TIM8_CH4 (AF3), instead of the previously considered TIM3_CH4 assignment.

### 3. Analog I/O

| GPIO Pin | Physical Pin | Function / Notes    |
| -------- | ------------ | ------------------- |
| PA0      | 22           | ADC, Wake-up pin    |
| PA4      | 28           | ADC, DAC1_OUT1      |
| PA5      | 29           | ADC, DAC1_OUT2      |
| PC2_C    | 17           | Direct ADC3 channel |
| PC3_C    | 18           | Direct ADC3 channel |

Note: The pins assigned to communication protocols can also be used as additional GPIO pins if necessary.
