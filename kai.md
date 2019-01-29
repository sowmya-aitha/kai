# KAI:
* _Kai is a wrist band that allows us to interact with devices with hand getures._
* _Kai can be used as a pointer ,to switch slides, draw , for zoom in and zoom out._
* _It is compatible with all the applications in mac,windows and linux laptops._
* _It recognizes the smallest movements of the fingers  that allows you to interact with your devices._
# Kai Architecture:
__It includes:-__<br>
* Hardware
* SDK
* KAI Control Center 
* Control Center
* json 
* C#
* Python<br>
## 1.Hardware:<br>
 _Hardware act as an interface for SDK._<br>
 ## 2.SDK:<br>
*  _Using SDK kai is programmed to control any digital device using gestures._<br>
* __SDK has 2 ways for communication:__<br>
__1.Process__: _It is console application based on standard input and standard output._<br>
__2.WebSocketServer__ :_It listens on port 2203._
## 3.KAI Control Center :<br>
* _KAI control center helps to control and design the kai._
* _using  KAI control center you can construct the gesture controls for Photoshop._
* _It has datatypes:_ <br>
  1.Gesture datatype:<br>swipe up/down.<br>
  2.Pyr datatype:<br> pitch,pinch,rool,yaw.
## 4.Control center:<br>
* _Control center consists of modules,which has the event related to gestures._
* _It allows us to choose the interaction options based on the software what we choose._<br>
1.User gesture are recieved by dongle from there decoding takes place and handled by SDK.<br>
2.The decoded information is sent to the modules,where the gesture related code is present and action takes place according to it.<br>
## JSON FORMAT:
1. **Authentication**:<br>During authentication,module must send ModuleId and ModuleSecret.<br>
```
type:authentication,
moduleId:123,
Modulesecret:qwerty
```
2. **Setting Capabilities**:
<br>Sets the data type to either true/false.
```
type:setCapabilities,
gestureData:true/false,
pyrData:true/false,
accelerometerData:true/false,
gyroscopeData:true/false
```
3. **Calibration**:<br>2 types of calibration<br>
1.**finger calibration**:  checks the position of fingers.<br>
2.**IMU calibration**
4. **List Connected kais**:This gives the count about how many wearable devices are connected.
```
type:connectedKai,
kaiId:0
```
5. **Get kai data**:<br> Which gives information about the kaiId and type.<br>
6. **switchHand**:<br>
It gives the response type as switch hand and also gives the information about hand either left/right.<br>
```
type:switchHand,
kaiId:123,
hand:left/right,
defaultLeftHand:true/false,
defaultRighthand:true/false
```
7. **Incoming Data**:<br>
It gives the information about the foreground process a chrome in linux.<br>
8. **Unknow Data**:<br>If request is unknow type,an error response is sent.
## workflow:<br>
First it starts with initialization,connect()  and eventHandlers.