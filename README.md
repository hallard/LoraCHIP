C.H.I.P. Computer Lora Gateway/Node for RFM95 or RN2483 Modules
===============================================================

This shield is used to hold HopeRF [Lora module][4] or Microchip [RN2483 LoraWan modules][3] Software with $9 [C.H.I.P. Computer][5]. it has just few minimal features. 

This shield can also act as a LoraWAN Node/gateway using this custom dedicated software    
- C.H.I.P. version of [LMIC][9] stack. This LMIC is in progress to works with this shield.


Features
========
- Footprint for RFM92/95/96/98 Lora module or Microchip RN2483 module
- Placement for choosing single Wire, SMA or u-FL Antenna type
- 2 x LED LED for visual indication
- 1 x Switch button (for example to power clean power off CHIP)
- I2C connector to connect 128x64 Oled or I2C sensors
- FTDI connector connected to Uart2 or Uart1 (selectable with a switch)

I'm waiting now for V1.0 boards PCBs.io, so I didn't fully tested them, I will update ASAP.

Detailed Description
====================

Look at the schematics for more informations.

For RFM95 SPI connexion is classic (MOSI/MISO/CLK/CS) is for SPI2 of CHIP Computer.

Only One GPIO needed for DIO0/DIO1/DIO2 (OR made with 3 diodes and one resistor R3) that will make this board fully compatible with current LIMC implementation, even if I've done a software fix which works with no interrupt. Only Needed for Lora modules, if you're using RFM69HCW and and to use IRQ just place D0 and R3.


Detailed Description
====================

On board switch select which Uart goes to FTDI connector (Uart1 or Uart2), RN2483 use CHIP UART2 and leave you UART1 to connect with serial console to CHIP with FTDI cable.

You can also use shield as a standalone RN2483, just plug FTDI connector with decent 3V3 supply, best us to use FTDI cable with 3V3/5V selectable power (select 3V3 of course)


```
CHIP Computer        RN2483
   LCD-D7        <---->  Reset
   LCD-D2 (TXD2) <---->  RXD
   LCD-D3 (RXD2) <---->  TXD

CHIP Computer    RFM95 Module
   CSIPCK   <---->  CS
   CSICK    <---->  CLK
   CSIHSYNC <---->  MOSI
   CSIVSYNC <---->  MISO
   CSID3    <---->  Reset
   DIO0     <---->  CSID0
   DIO1     <---->  CSID1
   DIO2     <---->  CSID2

CHIP Computer   On Board Leds
   LCD-D4  <---->  RED LED
   PWM     <---->  GREEN LED
```

### Schematic  
![schematic](https://raw.githubusercontent.com/hallard/LoraCHIP/master/pictures/LoraCHIP-sch.png)  

### Boards  
<img src="https://raw.githubusercontent.com/hallard/LoraCHIP/master/pictures/LoraCHIP-top.jpg" alt="Top">    

<img src="https://raw.githubusercontent.com/hallard/LoraCHIP/master/pictures/LoraCHIP-bot.jpg" alt="Bottom"> 

You can order the PCB of this board at [PCBs.io][8]. PCBs.io give me some reward when you order my designed boards from their site. This is pretty good, because I can use these rewards to create and design new boards and order boards for a discounted price and share new boards. So if you don't care about PCB manufacturer please use PCBs.io.

### Assembled boards (V1.0)

TBD

### V1.0 connected to C.H.I.P.

TBD

##License

<img alt="Creative Commons Attribution-NonCommercial 4.0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png">   

This work is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License](http://creativecommons.org/licenses/by-nc/4.0/)    
If you want to do commercial stuff with this project, please contact [CH2i company](https://www.ch2i.eu/en#support) so we can organize an simple agreement.

##Misc

See news and other projects on my [blog][2] 

[1]: https://staging.thethingsnetwork.org/wiki/Hardware/Gateways/DIY 
[2]: https://hallard.me
[3]: http://www.microchip.com/wwwproducts/en/RN2483
[4]: http://www.hoperf.com/rf_transceiver/lora/
[5]: https://getchip.com/pages/chip
[8]: https://PCBs.io/share/46N5m
[9]: https://github.com/hallard/arduino-lmic/tree/rpi
[13]: https://github.com/hallard/arduino-lmic/blob/rpi/README.md
