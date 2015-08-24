W5x00 ethernet library for STM32F103 micro-controllers
----

That library has been ported from the **WIZnet WIZ_Ethernet_Library**, to STM32F103 microcontrollers.
The library supports **W5100** and **W5500** Ethernet controllers. The source code has been modified to support the **W5200** too, but has not been tested (yet) on a real W5200 controller.

Ported to STM32F103 on 23 Aug 2015 by **Vassilis Serasidis**

Library installation
----
### *Install the library globally* ###


* Unzip the file **Ethernet_STM-master.zip** into your Arduino IDE directory 

> arduino\libraries

and rename the folder **Ethernet_STM-master** to **Ethernet_STM**

In this case the library can be used from the 8-bit and 32-bit Arduino boards (UNO, Nano, DUE etc) and from STM32F1 microcontroller series (for example STM32F103).

#### *Install the library for using it only with STM32F1 series* ###
 
* Unzip the file **Ethernet_STM-master.zip** into your Arduino IDE directory

> ...arduino\hardware\Arduino_STM32\STM32F1\libraries

and rename the folder **Ethernet_STM-master** to **Ethernet_STM**


Selecting the Ethernet type controller (W5100, W5200 or W5500)
----
For selecting among those tree chips edit the file:
`Ethernet_STM\src\utility\w5100.h`
and comment-out only the line with the chip you want to use.

By default the **W5500** ethernet chip is selected.

```
//#define W5100_ETHERNET_SHIELD // Arduino Ethenret Shield and Compatibles ...
//#define W5200_ETHERNET_SHIELD // WIZ820io, W5200 Ethernet Shield 
#define W5500_ETHERNET_SHIELD   // WIZ550io, ioShield series of WIZnet
```
If you edit the **w5100.h** file, save it and re-compile your sketch. 

Using the Ethernet_STM library
----
1. Choose the desired ethernet chip you want to use (W5100, W5200 or W5500) from the w5100.h file
2. include this library in your sketch  

`#include <Ethernet_STM.h>`

All functions / commands have the same syntax with the stock Arduino Ethernet library. 


PIN Connections
----
|W5x00|STM32F103|
|:------:|:-----:|
|SS|PA4|
|SCK|PA5|
|MISO|PA6|
|MOSI|PA7|



**DO NOT FORGET TO ADD A RESISTOR 4k7 BETWEEN RESET AND 3.3V (OR RESET AND 5V) PINS ON ETHERNET SHIELD**

![alt tag](http://www.serasidis.gr/images/w5100_shield_1.jpg)
![alt tag](http://www.serasidis.gr/images/w5100_module_2.jpg)
![alt tag](http://www.serasidis.gr/images/w5100_module_1.jpg)

