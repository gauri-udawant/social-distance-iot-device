# social-distance-iot-device
1.Social distance alerting device

2. INTRODUCTION
The aim of the project is to help people maintain social distance to avoid spreading COVID-19. In some settings and surroundings, it's easy for people to forget to keep а safe distance, and so this device could help remind them.
In our project, we are basically concentrating on following applications such as:
*To provide guidance at public events where strangers need to maintain social distancing.
*This could be useful in schools, museums, recreational facilities, or workplaces.

Everyone is given a device to wear. The devices measure the time it takes for a sound to travel from one person to another. Sound travels approximately 0.340 meters per millisecond, so for a social distance of 2 meters, sound takes approximately 6ms to travel that distance. We can use high frequency sound, so that it remains inaudible to people.

3. AIM AND OBJECTIVES
3.1 Aim:
To design a wearable badge that warns the users if they encroach another user's safe social distance by using the ultrasonic sensor and RF waves.

3.2 Objectives:
1. To design a device to ensure social distance of 2 m between two people and to build at least two prototypes for testing.
2. To accurately synchronize between the devices, thereby establishing a network wherein the devices can communicate efficiently with each other.
3. To alert the user via the Beeper and the Vibration Motor if the time taken between the sent and received RF Packet is less than 6 ms.

3.3 Methodology:
We recognized the Social Distancing issue and began our research on the subject. During the Literature Survey, we came across a crude device using an Ultrasonic Distance Sensor that alerts the user via a beeper when social distance is disobeyed. This device sparked the inspiration to build a more reliable and compact device, capable of communicating with other devices, thereby forming a network.
We decided to make use of Radio Waves as the system needs to be nearinstantaneous. After a thorough market survey, we selected the nRF24L01+ Transceiver Module among the other RF Modules available. Referring to articles, we concluded that the Receiver Transducer de-soldered from the HC SR-04 Module would serve efficiently as the RF receiver. We also decided to use the versatile ATmega-328p microcontroller as the main unit. For prototyping, we concluded that the Arduino Nano R3 board would be apt as it is compact and versatile.
One of the goals of the design is to minimize the component count and leverage the Arduino Nano as much as possible for the ultrasonic send and receive. Unfortunately, an Arduino Nano draws significant current (30-40mA) all the time, in order to power the MCU and the USB to serial interface. This means an Arduino is great for prototyping but the finished device needs to use less power to keep it small and battery operated. The finished device also needs to be able to manage battery charging, allowing the power to be turned on and off, and have a compact build.
![image](https://github.com/user-attachments/assets/9853b147-31d5-4d07-8967-25746c268698)
![image](https://github.com/user-attachments/assets/9f747726-dd0c-4e08-a360-c1191f01d212)
![image](https://github.com/user-attachments/assets/73b9aa97-92a6-4fb8-b4ea-76f022ee687a)

3.4 Specifications of the System:
Hardware:
1. Arduino Nanо:
Microcontroller: ATmega-328p
Operating Voltage: 5V
Input Voltage: 7V - 12V
2. nRF24L01+ Transceiver Module:
Operating Voltage: 1.8V - 3.6V (Input 5V tolerable)
Frequency: 2.4 GHz
Data Transfer Rate: 1-2 MB/s
Current Consumption: Transmission: 0.1mA
Reception: 14mA
Software:
Table 1: Survey of RF Modules
1. Arduino IDE:
Developer: Arduino Software
The Arduino Integrated Development Environment (IDE) is a cross-platform
application and is used for uploading programs to Arduino compatible boards.
2. Fritzing:
Developer: Interaction Design Lab, Potsdam
Fritzing is an open-source initiative to develop amateur or hobby CAD software for
the design of electronics hardware.

7. EXPECTED RESULTS
1. One device (the 'sender') sends an RF packet to all other devices in radio frequency range. It then begins listening for an ultrasonic ping. Device that receives the RF signal immediately responds with an ultrasonic ping.
2. The ping from the closest device to the 'sender' arrives first to the 'sender'. The 'sender' measures the duration between RF send and ultrasonic receive. If this duration is less than approximately 6ms, we know the users are too close, and the RF sender alerts its user via the piezo buzzer.
3. Each device becomes a 'sender' on random occasions in order to ensure the RF channel is shared and every user has distance measurements.
   
