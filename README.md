# Connecting BMP180 to Firebase
This project uses a D1 Mini microcontroller to read temperature and pressure data from a BMP180 sensor, display it on an OLED screen, and upload the readings to Firebase Firestore. The system uses WiFiManager for flexible WiFi and Firebase credential configuration. 

*Hardware Requirements*

* D1 Mini (ESP8266-based microcontroller)
* BMP180 Barometric Pressure Sensor
* 0.96" I2C OLED Display (SSD1306)

 *Software Requirements*

* Firebase account

*Firebase Setup*

1.	Create a Firebase Account:

* Go to Firebase Console.
* Sign in with your Google account or create one.

2.	Create a Firebase Project:

* Click on "Add project" and follow the setup instructions.

3.	Enable Firestore Database:

* In your Firebase project dashboard, navigate to Build > Firestore Database.
* Click on "Create database" and select "Start in test mode" for development purposes.

4.	Enable Email/Password Authentication:

* Go to Build > Authentication > Sign-in method.
* Enable the "Email/Password" sign-in provider.

5.	Register a User:

* Under Users, click on "Add user" and enter an email address and password.
6.	Obtain Firebase Configuration Details:

* Navigate to Project Settings > General.
* Under "Your apps", register a new Web app (</>) to retrieve your API Key and Project ID.

*OLED Display Behavior*

* On Boot, the OLED displays:
> Initializing...
> Connect to BMP180 Config
> Edit Credentials
> Save

* After Connecting to WiFi, the OLED Displays:

> Connected

* During Operation the OLED Displays sensor data:

> Temp: XX.XX C
> Press: XXXXX Pa

*Deployment via Solution Builder*

1.	Access Carenuity's Solution Builder:
* Open solutionbuilder.carenuity.com

2.	Upload the Provided Firmware:
   * Choose the BMP180 binary file corresponding to this project.
 	 * Connect your D1 Mini via USB and select the port.
   * Flash the firmware using the platform.

3.	Configure WiFi and Firebase:

* After flashing, the D1 Mini will start the "BMP180 Config" portal.
* Connect to the "BMP180 Config" WiFi network using a browser.
* A form will appear allowing you to enter:

> WiFi SSID & Password
> Firebase API Key
> Firebase Project ID
> Firebase Email & Password

 * Save settings; the device will automatically connect and begin uploading data.

 *Firebase Output:*

* Realtime Sensor Data:
> Sensor readings are uploaded to Firestore under a defined collection and document path.

* Graph overview:
> View real-time graphs of temperature and pressure data on the Firestore dashboard via  the project overview section.


*Troubleshooting*

      * If the configuration portal does not appear, reset the device.
      * Ensure the BMP180 sensor is correctly wired and functional.
      * Double-check all Firebase credentials.
