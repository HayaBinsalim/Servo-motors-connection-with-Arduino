# Servo-motors-connection-with-Arduino
# Description 
Tinkercad is used in this project to show the connection of the circuit.
The link of the project: https://www.tinkercad.com/things/cJ3zu4UnsVf-mighty-amur/editel?tenant=circuits 


# Components Required 
- Arduino Uno
- 6 x Servo Motors
- Breadboard and Jumper Wires
- Power Supply
- 4 x 1.5V Battery

  
# Building the Circuit (Connections)
This project is based on Tinkercad. Tinkercad is a simple, online 3D design and modeling tool suitable for beginners. 

1. Browse Tinkercad (https://www.tinkercad.com/dashboard/designs/circuits); you will need to create an account.
2. Go to ***Designs*** and click on ***+ Create*** and select ***Circuits***
3. First, from the components section to the right, add a Breadboard, and an Arduino Uno next to it.
4. Then, add 6 servo motors on top of the breadboard; do not connect them to it, yet.
5. Now start connecting: <br />

    **Servo 1** (left hip): Digital **Pin 3** <br />
    **Servo 2** (right hip): Digital **Pin 5** <br />
    **Servo 3** (left knee): Digital **Pin 6** <br />
    **Servo 4** (right knee): Digital **Pin 9** <br />
    **Servo 5** (left ankle): Digital **Pin 10** <br />
    **Servo 6** (right ankle): Digital **Pin 11** <br />

6. Finally, connect the battery pack to the breadboard; make sure the positive and negative sides are both connected in the right place. The battery pack in this project consists of 4 cell of 1.5V batteries because the servo motors need 5 to 6V to work. 

The motors are all connected to the digital pins of the Arduino because digital pins provide precise control over the servo motors. They can output specific pulse-width modulation (PWM) signals required to set the angle of each servo accurately. This allows for fine-grained control of the robot's movements, ensuring coordinated and synchronized actions necessary for walking.

# Circuit Diagram 
Now you have the connections of the circuit done. You can add a code to the design to program the project and control the functioning of the motors.
Below is an image of the final circuit connections.

![output](https://github.com/HayaBinsalim/Servo-motors-connection-with-Arduino/blob/main/ArdServo%20(1).png)

# Programming the Motors 

## The Algorithm
1.	All motors are off; angles are all 0 degrees.
   
### One step with right leg
2.	servo1 (left hip) is set to 90 degrees (neutral) and shift all weight to the left leg
3.	servo3 (left knee) is set to 90 degrees (straight).
4.	servo5 (left ankle) is set to 90 degrees (neutral).
5.	servo2 (right hip) is set to 45 degrees (bending forward).
6.	servo4 (right knee) is set to 135 degrees (bent downside).
7.	servo6 (right ankle) is set to 45 degrees.
8.	Delay for 500 milliseconds for the servos to finish the movements. The robot's right leg has now moved forward.
9.	servo2 (right hip) to 90 degrees (neutral).
10.	servo4 (right knee) to 90 degrees (straight).
11.	servo6 (right ankle) to 90 degrees (neutral).
12.	Delay for 500 milliseconds for the servos to finish the movements. The robot's right leg's joints now are back to their initial position, but they are moved forward. One step is done.
    
### One step with left leg
13.	servo1 (right hip) is set to 90 degrees (neutral) and shift all weight to the left leg
14.	servo3 (right knee) is set to 90 degrees (straight).
15.	servo5 (right ankle) is set to 90 degrees (neutral).
16.	servo2 (left hip) is set to 45 degrees (bending forward).
17.	servo4 (left knee) is set to 135 degrees (bent downside).
18.	servo6 (left ankle) is set to 45 degrees.
19.	Delay for 500 milliseconds for the servos to finish the movements. The robot's left leg has now moved forward.
20.	servo2 (left hip) to 90 degrees (neutral).
21.	servo4 (left knee) to 90 degrees (straight).
22.	servo6 (left ankle) to 90 degrees (neutral).
23.	Delay for 500 milliseconds for the servos to finish the movements. The robot's left leg's joints now are back to their initial position, but they are moved forward. One step is done.
24.	The 'loop' function is used to repeat these steps for the robot to walk. 

## The Code 
The code starts with including the ```Servo``` library to control the servo motors. 

```
#include <Servo.h>
```
Then, craete a servo objetc for each of the servo motors using the following code.

```
Servo servo1; // Left Hip
Servo servo2; // Right Hip
Servo servo3; // Left Knee
Servo servo4; // Right Knee
Servo servo5; // Left Ankle
Servo servo6; // Right Ankle
```

The ```setup``` function is responsible to cennecting each servo motro with a pin in the arduino.

```
void setup() {
  servo1.attach(3);
  servo2.attach(5);
  servo3.attach(6);
  servo4.attach(9);
  servo5.attach(10);
  servo6.attach(11);
}
```

The final function here is the ```loop``` function. It is responsible to repeating the movements of the servo motors based on the movement of the legs. The movement consists of first moving the right leg forward, returning it to neutral, moving the left leg forward, and finaly returning it to neutral. This way two steps are done. 

```
void loop() {
  // Step 1: Move right leg forward
  servo1.write(90); // Left hip neutral
  servo2.write(45); // Right hip forward
  servo3.write(90); // Left knee straight
  servo4.write(135); // Right knee bent
  servo5.write(90); // Left ankle neutral
  servo6.write(45); // Right ankle adjusted
  delay(500); // Wait for 500 milliseconds

  // Step 2: Move right leg back to neutral
  servo2.write(90); // Right hip neutral
  servo4.write(90); // Right knee straight
  servo6.write(90); // Right ankle neutral
  delay(500);

  // Step 3: Move right leg to neutral, move left leg forward
  servo1.write(45); // Left hip forward
  servo2.write(90); // Right hip neutral
  servo3.write(135); // Left knee bent
  servo4.write(90); // Right knee straight
  servo5.write(45); // Left ankle adjusted
  servo6.write(90); // Right ankle neutral
  delay(500); // Wait for 500 milliseconds

  // Step 4: Move left leg back to neutral
  servo1.write(90); // Left hip neutral
  servo3.write(90); // Left knee straight
  servo5.write(90); // Left ankle neutral
  delay(500); // Wait for 500 milliseconds
}
```

In brief, the ```void loop()``` function orchestrates a bipedal robot's walking cycle by sequentially adjusting servos for its hips, knees, and ankles. Initially, the servos move the right leg forward while keeping the left leg neutral, then return the right leg to a neutral position. Next, the left leg is moved forward while the right leg remains neutral, returning the left leg to a neutral position. Each movement phase is followed by a 500-millisecond delay to allow for smooth transitions. This sequence repeats indefinitely, enabling the robot to simulate a walking motion.

For a clearer represntation of the movements of the motors, you can open the link of the project given in the beginning of this file. 

