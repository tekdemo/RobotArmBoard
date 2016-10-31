# Robot Arm Control Board

Teensy based control board designed for adding closed loop control to OWI-535 Robotic Arm Edge kit. 

## Setup

### Power
Using the 6 D cell battery output is suggested. See assembly notes for more details.

The Teensy is not powered by the batteries, and must be provided USB power for the robot to operate. 

### Motors

Each motor is driven by a pair of signal pins signals from the Teensy. Setting one `HIGH` and the other `LOW` will result in moving the motor, and thus each joint. 

- Pins `10` and `9` control `M1`, opening and closing the claw.
- Pins `6` and `5` control `M2`, the "wrist" joint
- Pins `4` and `3` control `M3`, the "elbow" joint. 
- Pins `20` and `21` control `M4`, the "shoulder" joint. 
- Pins `22` and `23` control `M5`, which rotates the arm 
- Pin `13` controls the light on the claw end. This is the same as the Teensy's built in LED.

### Analog Feedback

For closed loop feedback, the following pins are available:
- Pin `A1` corresponds to `M1`'s potentiometer. 
- Pin `A2` corresponds to `M2`'s potentiometer. 
- Pin `A3` corresponds to `M3`'s potentiometer. 
- Pin `A4` corresponds to `M4`'s potentiometer. 
- Pin `A5` corresponds to `M5`'s potentiometer. 

Note, each potentiometer "tuning" will be somewhat different, and require some setup for each robot and each joint. 

### Controller Input
The controller uses the same analog pins as the Analog feedback. As a result, it's not simple to use the controller for input when the analog feedback is plugged in. However, doing so will not harm the electronics. 

- Pin `A1` corresponds to `M1`'s joystick. 
- Pin `A2` corresponds to `M2`'s joystick. 
- Pin `A3` corresponds to `M3`'s joystick. 
- Pin `A4` corresponds to `M4`'s joystick. 
- Pin `A5` corresponds to `M5`'s joystick. 
- Pin `A0` corresponds to the Light slider. 

Due to the joystick construction the joystick will only generate a few values. When read using `AnalogRead`, you will get roughly `512` when the joystick is idle, and around `1023` or `0` when the joystick is pressed. 

The LED switch is wired up to it's own unique input, and can be used alongside a closed loop input without issue. The `LED` switch will be around `512` when off, and `1023` when on.

## Assembly

### Power Input

### Motors

### Controller Input Section