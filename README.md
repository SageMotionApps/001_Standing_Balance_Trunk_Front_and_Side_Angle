# 001 Standing Balance Trunk Front and Side Angle
Measure and train trunk side and front angles during standing.

### Nodes Required: 5 
 - Sensing (1): trunk (middle of back, switch pointing up) 
 - Feedback (4): 
    - feedback_left: Node used to provide haptic feedback when the participant exceeds the threshold set in the app configuration panel.
    - feedback_right: Node used to provide haptic feedback when the participant exceeds the threshold set in the app configuration panel.
    - feedback_front: Node used to provide haptic feedback when the participant exceeds the threshold set in the app configuration panel.
    - feedback_back: Node used to provide haptic feedback when the participant exceeds the threshold set in the app configuration panel.


## Algorithm & Calibration
### Algorithm Information
The raw quaternions from the IMU are converted to Euler angles, and the roll angle is extracted using well established mathematical principles. If you'd like to learn more about quaternion to Euler angles calculations, we suggest starting with this Wikipedia page: [Conversion between quaternions and Euler angles](https://en.wikipedia.org/wiki/Conversion_between_quaternions_and_Euler_angles)

### Calibration Process:
The angle calculated is the global roll angle for the IMU. This must be aligned with the segment. No initial static calibration is performed to compensate for misalignment with the segment.

## Description of Data in Downloaded File
- time (sec): time since trial start
- TSA (deg): trunk side angle (medial-lateral), positive is to the right
- TFA (deg): trunk forward angle (anterior-posterior), positive is forward 
- max_lean_right (deg): The feedback threshold of max right lean set by the user in the app configuration panel.
- max_lean_left (deg): The feedback threshold of max left lean set by the user in the app configuration panel.
- max_lean_front (deg): The feedback threshold of max front lean set by the user in the app configuration panel.
- max_lean_back (deg): The feedback threshold of max back lean set by the user in the app configuration panel.
- feedback_right_state: feedback status for if the sensor has crossed the max right lean threshold. 
  - 0 is “feedback off”
  - 1 is “feedback on”
- feedback_left_state: feedback status for if the sensor has crossed the max left lean threshold. 
  - 0 is “feedback off”
  - 1 is “feedback on”
- feedback_front_state: feedback status for if the sensor has crossed the max front lean threshold. 
  - 0 is “feedback off”
  - 1 is “feedback on”
- feedback_back_state: feedback status for if the sensor has crossed the max back lean threshold. 
  - 0 is “feedback off”
  - 1 is “feedback on”
- SensorIndex: index of raw sensor data
- AccelX/Y/Z (m/s^2): raw acceleration data
- GyroX/Y/Z (deg/s): raw gyroscope data
- MagX/Y/Z (μT): raw magnetometer data
- Quat1/2/3/4: quaternion data (Scaler first order)
- Sampletime: timestamp of the sensor value
- Package: package number of the sensor value

# Development and App Processing Loop
The best place to start with developing an or modifying an app, is the [SageMotion Documentation](http://docs.sagemotion.com/index.html) page.