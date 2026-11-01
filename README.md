# Custom-STM32-H7B0VB

A custom development board built around the STM32H7B0VB (LQFP100) as part of the Formula Student Team Formula Manipal. The goal is building a test board to later be embedded into multiple other PCBs such as the Vehicle Control Unit, Accumulator Management System and other important PCBs that go onto the car.

The board contains one instance each of UART, I2C, SPI and CAN, plus analog, PWM-capable digital pins and two LEDs. Special care has been taken to assign each pin/LED a different PWM timer for each to be capable enough to run at it's own frequency.
