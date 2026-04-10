# Home-Assistant-Voice-Assist-ESP32-C6
Build an inexpensive Home Assistant Voice Assist Satellite 

YAML for Home Assistant ESPHome Builder to make an inexpensive Satellite Voice Assist Device

COMPONENTS:

Seeed Studio ESP32-C6   (Amazon ASIN B0DJ6N55FX)
INMP441 Omnidirectional I2S Microphone Module MEMS, high precision, low power, supports ESP32   (Amazon ASIN B0FBWQF74T or equivalent)
MAX98357 I2S Audio Amplifier Module, Class D  (Amazon ASIN B096ZM9LL5 or equivalent)
4 Ohm 3 Watt Mini Speaker   (Amazon ASIN B0BTP67F81 or equivalent;  8 ohm will also work, lower peak volume)

Optional: LED and 1K resistor (or for brighter, 330ohm resistor)

Connections:
ESP32-C6 --------   MAX98357A
D0  -------------  LRC (pin 7)
D1  -------------  BCLK (pin 6)
D9  -------------  DIN  (pin 5)
GND -------------  GND (pin 2)
5V  -------------  5V (pin 1)

ESP32-C6 --------  INMP441
D0  -------------  WS  (left pin 2)
D1  -------------  SCK (left pin 1)
D2  -------------  SD  (right pin 1)
3V3 -------------  3V3 (right pin 2)
GND -------------  GND (right pin 3)

Speaker output from MAX connect the 2 speaker wires

Optional LED and resistor - From ESP32 D10 to LED with 330-1000 ohm resistor in series to ground



