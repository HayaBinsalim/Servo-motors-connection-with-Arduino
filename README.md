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
2. Go to "Designs" and click on "+ Create" and select "Circuits"
3. First, from the components section to the right, add a Breadboard, and an Arduino Uno next to it.
4. Then, add 6 servo motors on top of the breadboard; do not connect them to it, yet.
6. Now start connecting: Servo 1 (Left Hip): Digital Pin 3
Servo 2 (Right Hip): Digital Pin 5
Servo 3 (Left Knee): Digital Pin 6
Servo 4 (Right Knee): Digital Pin 9
Servo 5 (Left Ankle): Digital Pin 10
Servo 6 (Right Ankle): Digital Pin 11
7. Finally, connect the battery pack to the breadboard; make sure the positive and negative sides are both connected in the right place. The battery pack in this project consists of 4 cell of 1.5V batteries because the servo motors need 5 to 6V to work. 


# Circuit Diagram 
Now you have the connections of the circuit done. You can add a code to the design to program the project and control the functioning of the motors.
Below is an image of the final circuit connections. ![output](https://github.com/HayaBinsalim/Servo-motors-connection-with-Arduino/blob/main/ArdServo%20(1).png)

# Programming the Motors 
The code starts with including the 'Servo' library to control the servo motors. Then, each of the six servo motors will have a servo object created. The 'setup' function is responsible to cennecting each servo motro with a pin in the arduino.The final function here is the 'loop' function. It is responsible to repeating the movements of the servo motors based on the movement of the legs. The movement consists of first moving the right leg forward, returning it to neutral, moving the left leg forward, and finaly returning it to neutral. This way two steps are done. 

For a clearer represntation of the movements of the motors, you can open the link of the project given in the beginning of this file. 

