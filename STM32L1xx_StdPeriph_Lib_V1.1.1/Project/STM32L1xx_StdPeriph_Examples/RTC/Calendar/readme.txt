/**
  @page RTC_Calendar RTC Hardware Calendar example
  
  @verbatim
  ******************** (C) COPYRIGHT 2012 STMicroelectronics *******************
  * @file    RTC/Calendar/readme.txt 
  * @author  MCD Application Team
  * @version V1.1.1
  * @date    13-April-2012
  * @brief   Description of the RTC Hardware Calendar example.
  ******************************************************************************
  *
  * Licensed under MCD-ST Liberty SW License Agreement V2, (the "License");
  * You may not use this file except in compliance with the License.
  * You may obtain a copy of the License at:
  *
  *        http://www.st.com/software_license_agreement_liberty_v2
  *
  * Unless required by applicable law or agreed to in writing, software 
  * distributed under the License is distributed on an "AS IS" BASIS, 
  * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  * See the License for the specific language governing permissions and
  * limitations under the License.
  *
  ******************************************************************************
   @endverbatim

@par Example Description 

This example demonstrates and explains how to use the RTC peripheral.
As an application example, it demonstrates how to setup the RTC peripheral, in 
terms of prescaler and interrupts, to be used to keep time and to generate 
alarm interrupt. 

One from the following clock can be used as RTC clock source (uncomment the
corresponding define in main.c): 
  - LSE oscillator clock usually delivered by a 32.768 kHz quartz.
  - LSI oscillator clock

A key value is written in backup data register 0 to indicate if the RTC is already
configured.

The program behaves as follows:

1. After startup the user is asked to set the time and alarm (entered on 
      HyperTerminal).


2. When an External Reset occurs the BKP domain is not reset and the RTC configuration
   is not lost.

3. When power on reset occurs:
    - the BKP domain is reset and the RTC configuration is lost.

4. When an RTC Alarm A event occurs the RTC Alarm interrupt is generated and the
   LED1 is toggled.
   
The example uses HyperTerminal to configure the RTC clock and display the current time:
 - When SEL button is pressed, a menu is displayed to configure the RTC Time 
   and Alarm A registers.
 - When Key button is pressed, the current time is displayed.
 - When UP button is pressed, the current alarm A is displayed. 

LED2 is truned ON when the RTC configuration is done correctly.

 
@par Directory contents 

  - RTC/HW_Calendar/system_stm32f2xx.c   STM32F2xx system clock configuration file
  - RTC/HW_Calendar/stm32f2xx_conf.h     Library Configuration file
  - RTC/HW_Calendar/stm32f2xx_it.c       Interrupt handlers
  - RTC/HW_Calendar/stm32f2xx_it.h       Header for stm32f2xx_it.c
  - RTC/HW_Calendar/main.c               Main program
  - RTC/HW_Calendar/main.h               Main header file


@note The "system_stm32l1xx.c" is generated by an automatic clock configuration 
      system and can be easily customized to your own configuration. 
      To select different clock setup, use the "STM32L1xx_Clock_Configuration_V1.1.0.xls" 
      provided with the AN3309 package available on <a href="http://www.st.com/internet/mcu/family/141.jsp">  ST Microcontrollers </a>

      
@par Hardware and Software environment 

  - This example runs on STM32L1xx Ultra Low Power High-, Medium-Density and Medium-Density Plus Devices.

  - This example has been tested with STMicroelectronics STM32L152D-EVAL (STM32L1xx 
    Ultra Low Power High-Density) and STM32L152-EVAL (STM32L1xx Ultra Low 
    Power Medium-Density) evaluation board and can be easily tailored to any 
    other supported device and development board.

  - STM32L152-EVAL Set-up
    - Use LED1 led connected to PD.00 pin.
    - Use the SEL Joystick button connected to PE.08 pin (EXTI Line8).
    - Use the KEY push button connected to PA.00 pin (EXTI Line0).
    - Use the UP  Joystick button connected to PE.09 pin (EXTI Line10).
    - Connect a null-modem female/female RS232 cable between the DB9 connector 
      CN2 (USART2) and PC serial port to display data on the HyperTerminal.

    - Make sure that jumper JP5 is in position 2-3
    - Make sure that jumper JP9 is in position 1-2
      
    - Hyperterminal configuration:
      - Word Length = 8 Bits
      - One Stop Bit
      - No parity
      - BaudRate = 115200 baud
      - flow control: None


  - STM32L152D-EVAL Set-up
    - Use LED1 led connected to PD.03 pin.
    - Use the SEL Joystick button connected to PG.13 pin (EXTI Line13).
    - Use the KEY push button connected to PA.00 pin (EXTI Line0).
    - Use the UP  Joystick button connected to PG.11 pin (EXTI Line11).
    - Connect a null-modem female/female RS232 cable between the DB9 connector 
      CN1 (USART1) and PC serial port to display data on the HyperTerminal.

    - Make sure that jumper JP4 is in position 2-3

    @note Make sure that the LCD glass module is mounted on �IO� position.  

    - Hyperterminal configuration:
      - Word Length = 8 Bits
      - One Stop Bit
      - No parity
      - BaudRate = 115200 baud
      - flow control: None

       
@par How to use it ? 


In order to make the program work, you must do the following :
 - Copy all source files from this example folder to the template folder under
   Project\STM32L1xx_StdPeriph_Templates
 - Open your preferred toolchain 
 - Rebuild all files and load your image into target memory
 - Run the example

@note
- Ultra Low Power Medium-density devices are STM32L151xx and STM32L152xx 
  microcontrollers where the Flash memory density ranges between 64 and 128 Kbytes.
- Ultra Low Power Medium-density Plus devices are STM32L151xx, STM32L152xx and 
  STM32L162xx microcontrollers where the Flash memory density is 256 Kbytes.
- Ultra Low Power High-density devices are STM32L151xx, STM32L152xx and STM32L162xx 
  microcontrollers where the Flash memory density is 384 Kbytes.
    
 * <h3><center>&copy; COPYRIGHT STMicroelectronics</center></h3>
 */



