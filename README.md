# ESP_RFID_Thief

Ported/Remixed by Corey Harding from http://www.LegacySecurityGroup.com<br><br>
Most up to date code available from: http://exploit.agency/sploit/ESP_RFID_Thief<br>
Demo at: https://www.legacysecuritygroup.com/index.php/categories/9-rfid/26-adafruit-feather-huzzah-esp-12-remix-port-of-the-tastic-rfid-thief<br>
<br>

This is a port/remix of the Tastic RFID Thief to the Adafruit Feather HUZZAH, an ESP12E chip from the ESP8266 family.  It adds WiFi capability and makes the build nearly plug and play.  There is no SD card as there is a File System library FS.h being utilized and the board has an integrated battery and charging circuit along with WiFi.

<b>Parts list:</b><br>
HID MaxiProx 5375(Other Weigand Output RFID Readers will work such as the Prox Pro II 5455)<br>
Adafruit Feather HUZZAH<br>
2000mah 3.7V Adafruit LiPo Battery<br>
8xAA Battery Holder in Series(12V)<br>
Wire<br>
Solder and Iron<br>

<b>Software:</b><br>
Current Version Arduino IDE<br>
Latest ESP8266 Board Manager<br>

<b>Construction:</b><br>
Set voltage jumper on 5375 to 12V.<br>
Optionally disable the beeper(SW1-4).<br>
Insert and screw down red wire from 12V Battery Pack to Positive(+) terminal on the 5375.<br>
Insert and screw down black wire from 12V Battery Pack to Negative(-) terminal on the 5375.<br>
Solder green wire from Data0(Data) to Pin 4 on Feather HUZZAH.<br>
Solder white wire from Data1(Clock) to Pin 5 on Feather HUZZAH.<br>
Solder a wire from GND on the Feather HUZZAH to the GND on the 5375.(Do NOT do the same for Positive)<br>
Attach Lipo Battery to Feather HUZZAH.<br>

<b>Program:</b><br>
Optionally set the ssid and password of the access point being created by the Feather HUZZAH in the sketch source code(.ino file) as well as some other variables such as hidden ssid or IP address.  Or you can even edit the source to make it connect directly to your own network as a client vs being set up as an access point.  I made it easy to set in the source.<br>
Open Current Version Arduino IDE and Install the Library and Board via Board Manager using this link:<br>http://arduino.esp8266.com/stable/package_esp8266com_index.json <br>
Setup the proper board.<br>
Load sketch.<br>
Program.<br>

<b>Access:</b><br>
The Feather HUZZAH has created its own Access Point named "Exploit".<br>
By default the ssid is hidden.<br>
Connect to SSID: "Exploit" WPA2-PASSWORD: "DotAgency"<br>
Wait 90 seconds... while the SPIFFS file system is formatted for the first time.<br>
Open a web browser and connect to the IP address.  Default is http://192.168.1.1 <br>
You can now start scanning cards and view your captures at /log<br>

<b>LEGAL:</b><br>
Obey any international, federal, state, or local laws in your area.<br>
I ported/remixed the Tastic RFID Thief to the Feather HUZZAH for the purpose of proof of concept and legal white hat penetration testing.<br>
I can not and will not be held responsible for the use or misuse of this device.  It is solely up to you to make your own decisions.<br>

That was easy, huh?

Special thanks to Bishop Fox for releasing the original Tastic RFID Thief.<br>
Without them I wouldn't have had the inspiration or motivation to create a tool like this, let alone the code for decoding the Wiegand data.<br>
I hope this build inspires other people to port and remix more projects from the Arduino family over to the ESP8266 devices.<br>

Stay Legal!<br>
-Exploit.Agency
