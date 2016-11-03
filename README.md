# ESP_RFID_Thief
Port/Remix by Corey Harding from http://www.LegacySecurityGroup.com<br><br>
This is a port/remix of the Tastic RFID Thief to the Adafruit Feather HUZZAH, an ESP12E chip from the ESP8266 family.  It adds WiFi capability and makes the build nearly plug and play.  There is no SD card as there is a File System library FS.h being utilized and the board has an integrated battery and charging circuit along with WiFi.  One of the benefits of adding WiFi is that now you can remotely view your captures from any standard browser either through the built in access point or by having the ESP_RFID_Thief connect to an existing WiFi network/WiFi-cellular hot spot.  The ESP_RFID_Thief can now play a larger role during penetration testing in a Red Team scenario.  One team member can walk around with the device capturing tags or plant the device while other team members view the capture log.  This way the captured tags can be cloned off site and used by another team member walking in or sent via a network to a tag emulator that the field team member is carrying to avoid looking suspicious by not making the field team member view the logs and manually clone/emulate the card.

<br>
<b>Software used:</b><br>
Arduino IDE: Arduino IDE 1.6.11<br>
Board Manager/Libraries: esp8266 by ESP8266 Community version 2.3.0<br>
<br>
<b>Parts list:</b><br>
HID MaxiProx 5375<br>
Adafruit Feather HUZZAH<br>
2000mah 3.7V Adafruit LiPo Battery<br>
8xAA Battery Holder in Series(12V)<br>
Wire<br>
Solder and Iron<br><br>
<b>Construction:</b><br>
Set voltage jumper on 5375 to 12V.<br>
Optionally disable the beeper(SW1-4).<br>
Insert and screw down red wire from 12V Battery Pack to Positive(+) terminal on the 5375.<br>
Insert and screw down black wire from 12V Battery Pack to Negative(-) terminal on the 5375.<br>
Solder green wire from Data0(Data) to Pin 4 on Feather HUZZAH.<br>
Solder white wire from Data1(Clock) to Pin 5 on Feather HUZZAH.<br>
Solder a wire from GND on the Feather HUZZAH to the GND on the 5375.(Do NOT do the same for Positive)<br>
Attach Lipo Battery to Feather HUZZAH.<br>
Warning: The GPIO Pins on the Feather Huzzah are not supposed to be 5v tolerant(they operate at 3.3v) but this setup has been working fine for me on a breadboard with the 5375 reader powered by 8xAA Batteries. It is recommended to use a level shifter between the Data0/Data1 lines from the 5375 and Pin 4/5 on the Feather Huzzah.<br>

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
