# Walkie_Talkie_Breakout_Software
<img src="https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/images/walkie-talkie%20banner.png">

Say goodbye to communication challenges in areas with poor mobile signals like hilly forests, mountains, or deserts with the DIY Walkie-Talkie. This compact, robust device ensures reliable long-distance audio transmission up to 1 km, with customizable frequencies between 400-470MHz and adjustable power settings for license-free usage. Perfect for makers, outdoor enthusiasts, and anyone needing dependable communication in remote areas, the DIY Walkie-Talkie enhances outdoor experiences and is ideal for adventures, emergencies, and fun activities like hide and seek or scavenger hunts. Stay connected no matter where your adventures take you.

This github provides getting started instructions with Walkie-Talkie Breakout.

### Features:
- Walkie-Talkies can transmit **audio up to 1km** in open air.
- Walkie-Talkie frequencies can be tuned between **400-470MHz** with wattage settings **(0.5W and 1W)** to meet regulations for license-free usage in different regions.
- Easily communicate with individuals at a distance via walkie-talkie utilizing the **onboard microphone**.
- **Push to Talk button** for easy switch between Audio transmission and receive mode
- Multiple audio output choices are provided, including a **2mm JST connector** and a **2.54" 2 pin header** for connecting 3W speakers.
- There is also a **3.5mm Aux OUT** to attach headphones for private listening
- **Type C interface** for Power and AT command access for custom configuration.
- **UART breakout** Walkie-talkie module is offered for interfacing with various microcontrollers which is an add-on for your existing projects.


### Specification:
- **Supply Voltage:** 5V Type C
- **Operating pin voltage:** 3.3V
- **Battery Connector:** 3.7V Lithium Ion
- **Audio Outputs:**
	- 3W Speaker Output at 2.54” standard Header and 2mm JST 
	- Standard 3.5mm TRS Headphone Jack
- **Walkie-Talkie Module :**
	- **Frequency Range** => 400 ~ 470MHz
	- **Communication Distance** => around 1 km in Open area
	- **Current Consumption** => Rx around 60 mA and for Tx around 750 mA
	- **Operating Temperature Range** => -20°C ~ +70 °C

## Getting Started Walkie Talkie Breakout
### Pinout
<img src="https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/images/walkie-talkie%20pinout.png">


- **<ins>Walkie-Talkie Module</ins>**: SA818S-CE walkie-talkie module for audio communications over long distance.
- **<ins>Control Switch/Buttons<ins>** : Onboard there are three control switch,
   - **(2) PD Slide Switch** : Use to switch ON/OFF module power. On **+ve** side module is **ON** and **-ve** side module is **OFF**.
   - **(14) PWR Slide Switch** : Use to set **Wattage** of walkie-talkie transmission between 0.5W and 1W power. Slide switch on **H side** for **1W** and on **L side** for **0.5W**. 
   - **(4) Push-To-Talk** : Push switch when pressed walkie-talkie is in audio transmission mode, so talk to send audio. When release it is in reception mode to listen incoming audio from other walkie-talkie.

- **<ins>Type C Interface</ins>**: Type C interface for power and USB to UART access of walkie-talkie for configuration. 
- **<ins>External Power</ins>**: Additional power source option as 2mm JST to connect 3.7V lithium ion battery for portable use. Onboard charging facility available.
- **<ins>Audio Output</ins>**: Three options to listen incoming audio,
  - Use 2mm JST connector or 2.54" standard header to connect 2W or 3W speaker. Checkout below for compatible speaker options.
  - For private listening use 3.5mm Audio Jack. Required 3 Pole TRS Aux pin connector for Compatibility.

#### Compatible speakers available Here:
* [2W 6 Ohm Mono Enclosed Speaker](https://shop.sb-components.co.uk/products/2-watt-6-ohm-mini-portable-speaker-for-small-electronic-projects-2pcs)
* [3 Watt 8 Ohm Mini Speaker](https://shop.sb-components.co.uk/products/3-watt-8-ohm-mini-speaker-full-range-portable-for-small-electronic-projects)
  
## Configuration and Setting with UART via XCTU/Terminal Software
- Connect Walkie-Talkie breakout to PC/laptop using Type C interface and make sure Jumper selection is placed as shown to access walkie-talkie module for configuration.

  <img src="https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/images/jumper_selection.jpg" width="113" height="105">

- Now you will see device listed with COM port you can checkout in device manager, If not listed meaning CH340 driver missing. To install driver check out [CH340 Driver Installation Manual Guide](https://github.com/sbcshop/NFC_Module/blob/main/documents/CH340%20Driver%20installation%20steps.pdf).
  
  <img src="https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/images/device_manager_com.jpg" width="583" height="426">

- To monitor or configuration of device you can use any serial console terminal. For demo we have used XCTU which you can download from [official site here](https://hub.digi.com/support/products/xctu/).

  Select Tools > Serial console > configure

  <img src="https://github.com/sbcshop/L76_GPS_Breakout_Software/blob/main/images/xctu_1.jpg" width="600" height="451">

  <img src="https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/images/COMPORT_settings.jpg" width="600" height="451">

- Maintain defualt setting as shown in above fig. related to baudrate, data bits, parity, stop bits and flow control. Click OK and then close connection.
- We will create packet of AT commands to send. While creating packets make sure to add 0D and 0A after every command in HEX. Below simple demo,

  <img src="https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/images/AT_cmd_ascii.jpg" width="612" height="442">
  <img src="https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/images/AT_cmd_hex.jpg" width="283" height="259">

- Now select packet and click on send selected packet to view response,

  <img src="https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/images/at_cmd_response.jpg" width="612" height="442">

- Similarly you can add more AT Commands for easy configuration and save as XML for future reference. Sample XML available [here](https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/documents/walkie_talkie_testing_setup.xml),

  <img src="https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/images/at_cmd_response2.jpg" width="612" height="442">

  <img src="https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/images/at_cmd_response_frequency.jpg" width="612" height="442">
  
- By default you may receive Walkie-Talkie with UK 446.0812MHz frequency configured, but you can change this as per your region. To change default operating frequency you can use DMOSETGROUP command,
  - Format: AT+DMOSETGROUP=GBW, TFV, RFV, Tx_CXCSS, SQ, Rx_CXCSS
    ```
    Example 1: AT+DMOSETGROUP=0,446.0812,446.0812,0000,1,0000
    Example 2: AT+DMOSETGROUP=0,415.1250,415.1250,0012,4,0013
    Example 3: AT+DMOSETGROUP=0,415.1250,415.1250,754N,4,445I
    ```
    
  - Parameter Description:
    ```
    GBW: bandwidth setting (0: 12.5K 1: 25K)
    TFV: Transmit frequency value (400.0000MHz～470.0000MHz)
    RFV: Receiving frequency value (400.0000MHz～470.0000MHz)
    Tx_CXCSS: Transmit CXCSS value
    SQ: Squelch level (0～8) (0: monitor mode, scan mode cannot be used 0)
    Rx_CXCSS: Receive CXCSS value
    ```
    Note:
    - The transmitting frequency and receiving frequency can be the same or different, but the set frequency must be 12.5K and 25K, Integer multiples.
    - different CXCSS values can be used for transmitting and receiving, 0000: no coding, 0001-0038: CTCSS
    
- For Details Checkout [Walkie-Talkie Manual](https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/documents/SA818S-U_Datasheet.pdf)
  
## Resources
  * [Schematic](https://github.com/sbcshop/Walkie_Talkie_Breakout_Hardware/blob/main/Design%20Data/Walkie%20Talkie%20Breakout%20SCH.%20PDF.pdf)
  * [Hardware Files](https://github.com/sbcshop/Walkie_Talkie_Breakout_Hardware)
  * [Step File](https://github.com/sbcshop/Walkie_Talkie_Breakout_Hardware/blob/main/Mechanical%20Data/Walkie%20talkie%20Breakout%20.STEP)
  * [Walkie-Talkie Datasheet](https://github.com/sbcshop/Walkie_Talkie_Breakout_Software/blob/main/documents/SA818S-U_Datasheet.pdf)

## Related Products

  * [GatePi - Pico and LoRa based 4Channel Relay](https://shop.sb-components.co.uk/products/gatepi?_pos=3&_sid=276907aab&_ss=r)
  
    ![GatePi](https://shop.sb-components.co.uk/cdn/shop/products/gate-pi-photoi.png?v=1647335212&width=300)
  
  * [USB-to-LoRa dongle](https://shop.sb-components.co.uk/products/usb-to-lora-dongle?_pos=1&_sid=276907aab&_ss=r)
  
    ![USB-to-LoRa dongle](https://shop.sb-components.co.uk/cdn/shop/products/05_2.png?v=1678712489&width=300)
  
  * [Pico LoRa Expansion](https://shop.sb-components.co.uk/products/pico-lora-expansion?_pos=6&_sid=276907aab&_ss=r) 
  
    ![Pico LoRa Expansion](https://shop.sb-components.co.uk/cdn/shop/products/loar-2_1.jpg?v=1670922482&width=300)

  * [Lo-Fi : ESP based LoRa for Long Range communication](https://shop.sb-components.co.uk/products/lo-fi?_pos=22&_sid=276907aab&_ss=r) 
  
    ![Lo-Fi](https://shop.sb-components.co.uk/cdn/shop/files/SHOPSIZE3.jpg?v=1700211751&width=300)
    

 
## Product License

This is ***open source*** product. Kindly check LICENSE.md file for more information.

Please contact support@sb-components.co.uk for technical support.
<p align="center">
  <img width="360" height="100" src="https://cdn.shopify.com/s/files/1/1217/2104/files/Logo_sb_component_3.png?v=1666086771&width=300">
</p>
