# Home-Assistant-Voice-Assist-ESP32-C6
Build an inexpensive Home Assistant Voice Assist Satellite 

YAML for Home Assistant ESPHome Builder to make an inexpensive Satellite Voice Assist Device (Code file)
 19Apr26 version essentially the same but adds substitutions and there are some different values compared to original.
 Device is working push-to-talk (PTT) - I2S bus shared for mic & spekaer, current (2026.4.x) ESPHome Builder doesn't support states needed for code to properly share,
 so fixed timeouts are used. I've found the autogain for mic settings doesn't seem to have any effect, I haven't tried 0 which is to disable autogain. 
 I've found the mic sensitivity on the wakeword FAR superior to the Waveshare ESP32-S3's I've been using, and the response time is amazing
 IF remove the audio tone acknowledging the wakeword and just rely on the LED, you'll see zero delay between speaking wakeword and sending speech to HA.
 This code doesn't expose a media device - I have tried, it will compile and may work, but I am not and will not be using this for anything but
 speech/tone responses to assist requests/alarms.

COMPONENTS:<br>
Seeed Studio ESP32-C6   (Amazon ASIN B0DJ6N55FX)<br>
INMP441 Omnidirectional I2S Microphone Module MEMS, high precision, low power, supports ESP32   (Amazon ASIN B0FBWQF74T or equivalent)<br><br>
MAX98357 I2S Audio Amplifier Module, Class D  (Amazon ASIN B096ZM9LL5 or equivalent)<br><br>
4 Ohm 3 Watt Mini Speaker   (Amazon ASIN B0BTP67F81 or equivalent;  8 ohm will also work, lower peak volume)<br><br>

Optional: LED and 1K resistor (or for brighter, 330ohm resistor)<br><br>

Connections:<br>
```
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

(pin numbers are relative to locating what I am calling pin 1 and orienting the module to match)

Speaker output from MAX connect the 2 speaker wires

Optional LED and resistor - From ESP32 D10 to LED with 330-1000 ohm resistor in series to ground

```
Power the device either with rechargeable battery connected to 3V3 and GND or USB connector


<img width="871" height="702" alt="image" src="https://github.com/user-attachments/assets/f35430cb-d406-41b3-a023-c7019d593129" />

<img width="415" height="217" alt="image" src="https://github.com/user-attachments/assets/a2dd4364-f8c3-4256-9c51-8def8ade707d" />
Back & Front of MAX98357A <br> <br>

<img width="267" height="271" alt="image" src="https://github.com/user-attachments/assets/5d22788c-cd14-4525-a107-a18b0a856bfa" />
INMP441<br><br>
<img width="399" height="364" alt="image" src="https://github.com/user-attachments/assets/7b6e7c80-62dc-4fd9-bd17-f1ab3984b7b7" />




