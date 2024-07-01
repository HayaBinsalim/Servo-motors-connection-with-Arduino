# Servo-motors-connection-with-Arduino
# Description 
Tinkercad is used in this project to show the connection of a circuit consisting of 6 servo motors, 6 potentiometers, and an Arduino. 
The link of the project: https://www.tinkercad.com/things/cJ3zu4UnsVf-mighty-amur/editel?tenant=circuits 
# Steps of Building the Circuit (Connections)
This project is based on Tinkercad. Tinkercad is a simple, online 3D design and modeling tool suitable for beginners. 
1. Browse Tinkercad (https://www.tinkercad.com/dashboard/designs/circuits); you will need to create an account.
2. Go to "Designs" and click on "+ Create" and select "Circuits"
3. First, from the components section to the right, add a Breadboard, and an Arduni Uno next to it.
4. Then, add 6 servo motors on top of the breadboard; do not connect them to it, yet.
5. Add 6 potentiometers, each for a servo motor.
6. Now start connecting; start by connecting the 5V pin in the arduni to the (+) side of the breadboard and the GND pin to the (-) side of the breadboard. This is to ensure the current has a closed circuit to flow in. It is advised to change the colours of the wires; the ones for the voltage supply should be red and the ones for the ground can be black. you can change the colours by clicking on the colored square on the top bar and selecting your desired colour. 
7. Next, start connecting the servo motors to the bread board; each of them should have two connection with the breadboard, one with (+) side for voltage supply and the other to the (-) side for the ground.
8. Connect each motor to the arduino starting from pin 7 to pin 12.
9. As previuosly done, connect each potentiometer to the (+) and (-) in the breadboard for the voltage to be supplied to them.
10. Finally, connect each of the potentiometers to the arduino atrating from pins A0 to A5, respectively.
Now you have the connections of the circuit done. You can add a code to the design to program the project and control the functioning of the motors.
