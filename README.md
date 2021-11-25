# RFID-DOOR-LOCK-V2-IOT
This project build on the original door lock design https://github.com/humzah-77/RFID-DOOR-LOCK.

This program makes use of the built in EEPROM which allows storage of data indefinetly. The benifit of using the EEPROM is that is keeps the data in the event of power loss or accidently hitting the reset button on the Arduino board.

This program also uses the Arduino IOT cloud. I used the Arduino Nano 33 IOT to connect to the cloud And an Arduino Uno to control the lock. *(I could have controlled the lock and cloud using just the Arduino Nano but both boards are already controling other projects so I decided to just keep them as is and communicate between the two)**. I then connect both Arduinos together. **(I tried to use the RX/TX pins on both arduino but ran into some trouble communicating between the two boards. I need to do more reasearch to get the serial communication working)**. In the mean time I have used 4 digital pins on each Arduino to communicate between the two. I only need to send a true or false(0 or 1) between the boards so the digital pins are used.

<img width="1415" alt="Screen Shot 2021-11-24 at 8 25 45 PM" src="https://user-images.githubusercontent.com/58381410/143340638-98c10807-b24d-4328-88ac-81dd5d527b75.png">

How To Run:

1.  Wire modules and boards 
2.  Upload setupeeprom.ino to the Arduino Uno board
3. Once uploaded scan a RFID card 
4. Once scanned the ID will be saved into EEPROM as the mastercard in slots 1,2,3,4 along with EEPROM poisition curser variable stored in slot 0
5. Upload rfiddoorlock.ino to Arduino Uno board
6. Connect Arduino Nano to cloud
7. Upload lockv2cloud.ino onto the Arduino Nano from cloud
8. Create the Widgets and the cloud variables 
  eg.(String message;
  bool lock;
  bool openlock;
  bool adding;
  bool removing;)
8. Download the arduino cloud app to control from your phone
9. Now the system is ready

Whats New:

 You can create cloud widgets that allow you to monitor when the door was opened or closed, and intiate adding/removing modes.
 
 Widgets:
 Computer 
 
 <img width="1464" alt="Screen Shot 2021-11-23 at 8 44 06 PM" src="https://user-images.githubusercontent.com/58381410/143155941-044fc6a4-7060-4d16-b149-9fbec4319adb.png">
 
 Mobile
 
![image_123986672-2](https://user-images.githubusercontent.com/58381410/143156176-3d719666-b36d-4ded-b27a-53cbecf6891f.JPG)
 ![image_123986672](https://user-images.githubusercontent.com/58381410/143156159-54a9196a-9a9d-4158-a39c-3f2ac17b6728.JPG)
 
 Creating Widgets:

<img width="1503" alt="Screen Shot 2021-11-23 at 8 48 05 PM" src="https://user-images.githubusercontent.com/58381410/143156318-4bf34a45-4a92-4e60-a317-b5322bf627f9.png">

<img width="1489" alt="Screen Shot 2021-11-23 at 8 48 42 PM" src="https://user-images.githubusercontent.com/58381410/143156374-c7354e99-2a88-424a-9bf1-a1efb5fe1196.png">

<img width="1496" alt="Screen Shot 2021-11-23 at 8 49 03 PM" src="https://user-images.githubusercontent.com/58381410/143156403-035b6f13-0dd0-4105-ba50-2402a095f351.png">

<img width="1505" alt="Screen Shot 2021-11-23 at 8 49 19 PM" src="https://user-images.githubusercontent.com/58381410/143156431-0a7cfbba-1c3d-459e-b60a-5887ba2027e5.png">



<img width="1496" alt="Screen Shot 2021-11-23 at 8 49 36 PM" src="https://user-images.githubusercontent.com/58381410/143156461-1a44853b-8be1-48e3-b95b-6e8dbd5cec85.png">

     
