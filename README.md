# RoboCup 2018 Rescue Line
Programmes for 2018 RoboCup Rescue Line (Hwa Chong's Team Poivre)  
Final rank: Probably the last few teams  
Rules for RoboCup Rescue Line 2018 can be found [here](http://junior.robocup.org/wp-content/uploads/2018Rules/rescue_line_rules_final_2018.pdf).  
NXT was programmed using NXC as it was easier to code the communication between the nanos and the NXT.  
**WARNING: The code has yet to be tidied up and there is a huge lack of comments. Be ready for sphagetti code.**  

## Description of the robot
Our robot comprises 1 NXT and 2 Arduino Nano    
  * **Arduino Nano 1 (masternano) Consists:** 5 LDRs  
The LDRs were used for line tracing.  
* **Arduino Nano 2 (nanoultra) Consists:** 1 Ultrasonic Sensor (HC-SR04), 1 Compass (CMPS11, lots of issues :( )  
The compass is to allow us to detect the tilt (to let us know if the robot is on a ramp) and to detect its angle (to determine if there is a corner in the Evacuation Zone).  
* **NXT:** 2 HiTechnic NXT Color Sensor V2, 1 NXT Light Sensor , 3 NXT Motors  
The 2 Color Sensor were used to detect the green junction, while the light sensors were used to detect the entrance of the Evacuation Zone.  2 motors were used for manouvering and the last motor were used in the attachment to collect the balls. 

## Communications between the Arduino Nanos and NXT
Arduino Nano 2 communicates with Arduino Nano 1 via Serial, with Nano 2 being the slave and Nano 1 being the master. Nano 1 will then compile the readings from both Arduino Nanos which will then be sent via I2C to the NXT. Additionally, the 2 Color sensors communicates with the NXT via I2C. Using the values from the sensors, NXT will alter the movement of the robot accordingly.

## Files
* **Programmes**  
  * _"masternano"_ contains the code for Arduino Nano 1
  * _"nanoultra"_ contains the code for Arduino Nano 2.   
  * _"measurethresh.nxc"_ is used to measure the threshold of the LDRs 
  * _"see sensors.nxc"_ allowed us to view all the sensor readings at once.  
  * The code used for the different runs are titled respectively.   
* **Images**  
  * Images of the playfield used in Run 1 and Run 2
  * Top, side and back view of the robot
