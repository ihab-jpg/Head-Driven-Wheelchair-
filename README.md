# Head-Driven-Wheelchair-
My project is  a head-driven wheelchair that is designed for people with quadriplegia (paralyzed people that can only move their head). This design consists of an IMU sensors that picks up the signal, a Raspberry Pi controller, and 2 synchronized motors using PID. 

Welcome to my project repositry. I am Ihab, a mechatronics engineering student that love problem solving, and the problem we are solving here is how to make indipendancy more common especially for people with disabilities. 

The project is simple, yet effective and does the job, I will be talking about the main components of the project and for each I will upload its algorithm code. 


First of all, the head movement sensing technology is inspired from the F-35 pilot helmet, and consists of an IMU6050 sensor (please find its datasheet attached on the repositry) which detects the head movement direction. Its a 6-axis sensor that consists of a gyroscope and an accelorometer, which both combined and using internal variable capacitance reading technology, detect how fast it is rotating, and how fast is the speed changing respectivly. We are intereted in the terms roll, pitch, and yaw, which define the rotation about all the 3 axsis x, y, and z respectivly. The sensor is mounted on top of the head of the person, and connected using a flexible wire to a raspberry Pi controller that is fixed under the seat, the connection is using I2C protocol, and 2 power wires, which add up to 4 thin wires (please find the connection diagram attached). 

Secondly and most importantly the motors, I used 2 DC 6-60V 400W BLDC Three Phase DC Brushless Motor, which I took from an abadoned hover borad. These motors have 8 wires hanging out of them, 3 power wires and 5 wires for the internal hall sensor. I drived them using a special Motor Controller PWM Hall Motor Control Driver Board 12V 24V 48V. This driver is a board that takes its input from the power source directly and its logic control(PWM, enabler, stop, and direction) from the main controller (in my case Raspberry Pi) (please find its datasheet attached).

The motor driver is a multi purpose driver where you can use it to:
1) control the motor on and off at a fixed speed using its internal potentiometer
2) control the motor speed using an external potentiometer (knob) that you can wire easily
3) PWM control, which is the most powerful one, where you can do all the above features plus change its direction, PWM stands for pulse width modulation, where a generated pulse that its width is changed based on the required speed and direction is encoded and sent to the driver, where the driver decodes it and perform the required control.
    To equip the PWM feature, you will need to make a jumper connection between 2 nodes at the controller (I will attach a photo of the driver with labels)


