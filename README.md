# Self-Balancing-Robot
This Project introduces a two-wheeled self-balancing mobile robot based on a control moment gyroscope module. Two-wheeled mobile robots are able to achieve better mobility and rotation in small spaces and to move faster than legged robots such as humanoid type robots. For this reason, the two-wheeled mobile robot is generally used as a mobile robot platform. However, to maintain its balance, the two-wheeled robot needs to use movements of its two wheels. When an unexpected disturbance affects the robot, the robot maintains its balance with movements of the wheels and tilting of the body. If the disturbance exceeds the response capability of the robot, the robot will lose its stability. At the same time, the safety of the robot may be put at risk by movements to maintain balance. To address these issues, a robot was designed with a control moment gyroscope module to improve balance while minimizing movement. When a disturbance is applied to the robot, the disturbance is estimated by a disturbance observer and the control moment gyroscope controller compensates the disturbance. Using the control moment gyroscope module, the robot can maintain balance with just small movements of its wheels. Improved performance and stability were verified with experiments and simulations.
## how to operate 
### step 1:  "ON" the robot by Connecting male Black jack (upper) with Female black holder is downward
### step 2:  Keep on Stable base or ground and wait for 10 seconds sensor will calibrate
### step 3:  make it stand with human help for intial balancing point 
### step 4:  Bluetooth connectivity has been defined with application (Scan the QR )
### step 5:  Connect your bluetooth with the name of HC-05
### step 6:  Goto your application and click on setting option 
### step 7:  In setting option menu is defined with "connect to car" and Red will turn into green  
https://play.google.com/store/apps/details?id=braulio.calle.bluetoothRCcontroller

## Circuit Diagram 
![self balancing](https://user-images.githubusercontent.com/42414598/137737623-da3bc339-cce7-48e5-b398-441130cddab5.png)


## Resources
Material Required for the Projects 
## Hardwares 
* Arduino Uno R3
* MPU6050
* L298N Motor Driver 
* Bluetooth HC-05
* Acrylic chassis 
* Johnson DC Motor 100 rpm
* Motor clamp and screw packets
## Programming 
* Mpu6050 Package
* Arduino IDE 
# Methodology
Self balancing structures are ideal example to prove the extend of applicability of embedded systems, ruggedness of control systems
and an example to handle real-time systems. From the embedded context, these type of projects are helpful in providing the designer a much 
better insight about RTOS (real time operating systems), FPU (Floating point units) and the digital signal processing techniques.

 Here in this project we are targeting to self balance robot on its two rear wheels. This is a real time system where we have to take decision on the go. This robot on it's two wheel is unstable and won't be able to stand. Here we develop motor driving electronics(Hardware) and PID control script for balance the robot. 
 
# Getting started with the Accel-Gyro Module
Now-days gyroscopes are extremely small and very cheap to buy, so they are ideal for amateur electronics projects. Unfortunately these gyroscopes (both the cheap and the not-so-cheap versions) also come with their own problems. They are good for short-term and quick movements, but tend to drift over time as the error accumulates. They also record a lot of jitter and noise, which needs to be filtered by the micro-controller before the data can be used.

MPU-6050 6-axis accelerometer/gyroscope Arduino Library adapted for Arduino Library Manager by Electronic Cats, Feb 2019

The MPU6050 combines a 3-axis gyroscope and a 3-axis accelerometer on the same silicon die together with an onboard Digital Motion Processor(DMP) which processes complex 6-axis MotionFusion algorithms.

## Quick Installing
To install, use the Arduino Library Manager and search for "mpu6050" and install the library.

## Manual Installing
To install this library:

install it using the Arduino Library manager ("Sketch" -> "Include Library" -> "Manage Libraries..."), or
download a zipfile from github using the "Download ZIP" button and install it using the IDE ("Sketch" -> "Include Library" -> "Add .ZIP Library..."
clone this git repository into your sketchbook/libraries folder.
For more info, see https://www.arduino.cc/en/Guide/Libraries

## How Does Robot Balancing Work?
The MPU-6050 uses I2C to communicate with the micro-controller, I2C pins in Arduino are need to connect up the pins as shown in the schematics: the SDA line connects to the Analog pin 4, the SCL to Analog pin 5, power input to the 3.3v pin and the ground to the GND pin. If you are using one of the newer Arduinos, you could also connect the sensor to the dedicated SDA and SCL header pins
## Self-balancing Manual Tunning 
* In control theory, keeping some variable (in this case, the position of the robot) steady needs a special controller called a PID (proportional integral derivative). Each of these parameters has "gains", normally called Kp, Ki, and Kd. PID provides correction between the desired value (or input) and the actual value (or output). The difference between the input and the output is called "error". The PID controller reduces the error to the smallest value possible by continually adjusting the output. In our Arduino self-balancing robot, the input (which is the desired tilt, in degrees) is set by software. The MPU6050 reads the current tilt of the robot and feeds it to the PID algorithm, which performs calculations to control the motor and keep the robot in the upright position. PID requires that the gains Kp, Ki, and Kd values be "tuned" to optimal values. Engineers use software like MATLAB to compute these values automatically. Unfortunately, we can't use MATLAB in our case because it would further complicate the project. We will tune the PID values manually instead. Here's how to do this:
* Make Kp, Ki, and Kd equal to zero.
* Adjust Kp. Too little Kp will make the robot fall over, because there's not enough correction. Too much Kp will make the robot go back and forth wildly. A good enough Kp will make the robot go slightly back and forth (or oscillate a little).
* Once the Kp is set, adjust Kd. A good Kd value will lessen the oscillations until the robot is almost steady. Also, the right amount of Kd will keep the robot standing, even if pushed.
* Lastly, set the Ki. The robot will oscillate when turned on, even if the Kp and Kd are set, but will stabilize in time. The correct Ki value will shorten the time it takes for the robot to stabilize.
## Reference 
* http://shukra.cedt.iisc.ernet.in/edwiki/File:Physics.jpg
* https://maker.pro/arduino/projects/build-arduino-self-balancing-robot
* https://wired.chillibasket.com/2014/10/accel-gyro-sensors/
*        https://en.wikipedia.org/wiki/Inverted_pendulum#:~:text=An%20inverted%20pendulum%20is%20a,additional%20help%20will%20fall%20over.&text=The%20inverted%20pendulum%20is%20a,benchmark%20for%20testing%20control%20strategies.

