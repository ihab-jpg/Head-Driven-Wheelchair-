# Head-Driven-Wheelchair
My project is a head-driven wheelchair designed for individuals with quadriplegia (people with paralysis who can only move their head). This design consists of an IMU sensor that picks up movement signals, a Raspberry Pi controller, and two motors synchronized using a PID algorithm.

Welcome to my project repository. I am Ihab, a mechatronics engineering student who loves problem-solving. The problem we are addressing here is how to make independence more accessible, especially for people with disabilities.

The project is simple yet effective. I will discuss the main components and upload the algorithm code for each.

1. Head Movement Sensing

Shutterstock
The head-movement sensing technology is inspired by the F-35 pilot helmet. It utilizes an MPU6050 sensor (please find the datasheet attached in the repository) to detect the direction of head movement. It is a 6-axis sensor consisting of a gyroscope and an accelerometer. Combined with internal variable capacitance technology, these components detect rotation speed and changes in linear velocity, respectively. We are interested in the terms roll, pitch, and yaw, which define rotation about the X, Y, and Z axes. The sensor is mounted on the user's head and connected via a flexible wire to a Raspberry Pi controller fixed under the seat. This connection uses the I2C protocol and two power wires, totaling four thin wires (see the attached connection diagram).

2. Propulsion and Control
Most importantly, the motors: I used two 400W Three-Phase BLDC (Brushless DC) motors salvaged from an abandoned hoverboard. These motors have eight wires: three for power and five for the internal Hall sensors. I drove them using a specialized PWM Hall Motor Control Driver Board (12V–48V). This driver takes power directly from the source and receives logic control signals (PWM, Enable, Stop, and Direction) from the main controller—the Raspberry Pi (datasheet attached).

The motor driver is versatile and can be used to:

Toggle the motor on and off at a fixed speed using its internal potentiometer.

Control motor speed via an external potentiometer (knob).

Utilize PWM control, which is the most powerful method. PWM (Pulse Width Modulation) allows for precise speed adjustments and direction changes by varying the width of the generated pulses sent to the driver.

To enable the PWM feature, you must place a jumper between two nodes on the controller (I will attach a labeled photo of the driver for reference).
