# Ackermann Steering<br/>
## [Ackermann Simulator](Ackermann_Simulator.m)
The code simulates a very simplified kinematic model of ackermann steering commonly used in automobiles.<br />
Ref link: https://www.xarg.org/book/kinematics/ackerman-steering/<br /><br />
A simple PD controller is used to main a constant lateral distance. For the sake of simplicity we keep the forward velocity constant during the control action. The objective of this code was to biuld an intuition for tuning PD conitrol of an ackermann steered vehicle.<br />
### Controller:
Its worthwhile to mention that steering angle is not the same as car angle. Our control input is the steering angle not car angle, The objective of controller(100Hz) is slow the steering angle enough so that car angle catches up to the steering angle. To achieve this we have the Derevative component of PID. A dead band is also added in the middle, though it is not neccesary. Car dimensions to a 1/10 scale of an actual car.<br /><br />
### Markers:
Box -- Car<br /> Light Green line -- Car Angle (theta)<br /> Blue Line -- Steering Angle (phi)<br />Red Line -- Lateral step or goal<br /> All dimensions are in meters. Car angle and Steering angle plotted at origin.<br /><br /> 
### Output: 
To record a video change "vid_recorder" from 0 to 1. The file name by default is 'ackermann_simulator.avi'.<br /><br />
Testing:<br />        1) Kp = 1.5, Kd = 25  demos a working control ( but not best)<br /> 2) Kp = 1.5, Kd = 30  faster settling time but with steady state error<br /> 3) Kp = 1.5, Kd = 5   demos the need of Kd<br /> 4) change 'speed' to visualize the affect of car speed on controller<br /> 5) change 'goal' to change the goal or lateral step of the car<br /><br />
### Remarks:
The setting point as default is 1.5 m given that car width is  only 0.15m the goal is extermenly large for any controller to reach. A more practical value of 'goal' would be 0.5m.<br /> 
![](demo/AckermannSimulation-gif.gif)
