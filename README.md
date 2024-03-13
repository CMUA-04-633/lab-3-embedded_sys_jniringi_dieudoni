Description

This project incorporates light intensity and temperature sensing, with an LED responding to light changes. Temperature is measured using an LM34 sensor, and the LCD displays real-time values of Celsius and Fahrenheit. Communication occurs via UART, continuously updating and transmitting data in an infinite loop.


Components and Boards Used:

- STM32 Nucleo board.
- Photoresistor with 10K Ohm resistor.
- LM34 temperature sensor.
- External LED.
- LCD with HD44780 controller.

Main code functionality

1. System Initialization:
   - Function: SystemClock_Config
   - Purpose: Configures the system clock.
   - Working Principle: Establishes the system clock settings, determining the overall timing of the microcontroller.

2. Peripheral Initializations:
   a. GPIO Initialization:
      - Function: MX_GPIO_Init
      - Purpose: Initializes GPIO peripherals.
      - Working Principle: Configures the microcontroller's GPIO pins for various operations.

   b. UART Initialization:
      - Function: MX_USART2_UART_Init
      - Purpose: Initializes UART communication.
      - Working Principle: Configures the UART module for serial communication.

   c. ADC1 Initialization:
      - Function: MX_ADC1_Init
      - Purpose: Initializes ADC1 for analog-to-digital conversion.
      - Working Principle: Sets up ADC1 for converting analog signals to digital values.

   d. ADC2 Initialization:
      - Function: MX_ADC2_Init
      - Purpose: Initializes ADC2 for analog-to-digital conversion.
      - Working Principle: Sets up ADC2 for converting analog signals to digital values.

   e. I2C1 Initialization:
      - Function: MX_I2C1_Init
      - Purpose: Initializes I2C1 for I2C communication.
      - Working Principle: Configures I2C1 for communication with other devices.

3. Main Program Loop:
   - Function: main
   - Purpose: Main entry point of the program.
   - Working Principle: Enters an infinite loop where the primary functionality of the program is executed repeatedly.

4. Temperature Conversion Functions:
   a. Celsius Conversion:
      - Function: temp_value_to_Celsius
      - Purpose: Convert ADC temperature values to Celsius.
      - Working Principle: Takes an ADC temperature value, converts it to Celsius, and stores the result in a character buffer.

   b. Fahrenheit Conversion:
      - Function: temp_value_to_Fahrenheit
      - Purpose: Convert ADC temperature values to Fahrenheit.
      - Working Principle: Takes an ADC temperature value, converts it to Fahrenheit, and stores the result in a character buffer.

5. LED Control Function:
   - Function: LED_on_Flash
   - Purpose: Controls an LED based on light intensity.
   - Working Principle: Toggles an LED when the light intensity exceeds a certain threshold. The LED is controlled based on a counter (i) to avoid immediate toggling.

6. Error Handling:
   - Function: Error_Handler
   - Purpose: Handles errors by entering an infinite loop.
   - Working Principle: In case of an error, this function disables interrupts and enters a perpetual loop, effectively halting the program.

7. Main Loop Execution:
   - Working Principle: Inside the main loop, the program continuously performs various actions, including ADC conversions, LED control, and displaying information on an LCD while transmitting data over UART.


Challenges:

- Debugging is quite tough as there are no enough guidance in case of errors.
- Integrating various peripherals like ADCs, UART, and LCDs needs careful consideration of data formats, communication protocols etc.
- Ensuring accurate readings from sensors may require calibration or different type of sensors to account for variations and environmental factors.





Done by Dieudonne and Damour
