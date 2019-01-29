# *__KAI__*
* **KAI** is a wearable band that recognizes gestures of your hand and performs actions.<br>
* It is compatible with any bluetooth enabled device including laptops,mobile phones,VR/AR and drones.<br>
* We can use KAI with any digital device and can control any digital device by tracking your hand and finger gestures .<br>
* It is Completely compatible with any applications in Mac, Windows and Linux laptops.<br>
* **KAI** device consits of battery that lasts long upto 8 hours and a dongle that can connect to multiple KAIS.<br>
* **KAI** can be used to perform shortcuts, mouse actions etc like Slide Up/Down, Zoom in/out, pinch etc.

# *__KAI ARCHITECTURE__* 
**KAI** Architecture has various components like Hardware, SDK, Control Centre Module and KAI control centre.<br>

 * **Hardware:**<br> 
    It acts as an interface for SDK.

* **SDK:**<br>
     SDK allows users to create profiles for desktop software.<br>
     User gestures are recognized and sent to dongle and then from dongle to SDK for decoding. The gesture code is present in modules and the related action is performed.
    SDK has two ways of communication.<br>
     * process: It uses console application for standard input/output.
     * WebSocket server: It listens to the port 2203.

* **Control Centre Module:**<br>
control centre allows you to choose the software based on the interaction
It contains modules and can handle the events.

* **KAI Control Centre:**<br>
Is a desktop application where user can selects an application and can choose any gestures to perform an action.<br>
It contains datatypes like
  * Gesture Data: contains slide up/down gestures
  * Pyr Data: contains gestures like roll, pitch, yaw
  * Accelerometer Data : contains x, y, z positions.
  * Gyroscope Data
  * Magnetometer Data
---
## *__Communicating with SDK:__*
1.  **Authentication:** During authentication, the module sends a moduleId and module secret, it returns the response type as authentication.<br>
    ```
    type: authentication,
    moduleId: 123,
    modulesecret: qwerty
    ```

1. **Setting Capabilities:** It sets the datatype to either true/false.
   ```
    type:setCapabilities,
    gestureData: true/false,
    pyrData: true/data,
    accelerometerData: true/false,
    gyroscopeData: true/false,
    magnetometerData: true/false
   ```

1. **Switch Hand:** It gives the response type as switch hand and also gives the information about hand either left or right.
   ```
      type: switchhand,
      KaiId: 123,
      hand: right/left,
      defaultlefthand: true/false,
      defaultrighthand: true/false
    ```

1. **List Connected KAIS:** It gives the count of KAIs along with KAI Id.
     ```
     type:connectedkai,
     kaiId:0,
     ```

1. **Incoming Data:** It recognizes the response type as incoming data along with kaiId and also gives the information about foreground process as chrome in linux.
    ```
    type: incoming data,
    kaiId: 0,
    foreground process: chrome
    ```

1. **Calibration:** It has two types<br>
     * Finger Calibration: Checks the position of fingers.
     * IMU calibration

1. **Unknown Data:** If the user sends the request with unknown datatype an erroe is sent as response. 




