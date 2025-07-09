# 40-Yard Dash Sprint Timer 
Do you think you can run a faster 40-yard dash than a NFL player? If you want an affordable method to test it without using manual hand timing that's prone to human error, then try using this sprint timer inspired by the NFL Combine's 40-yard dash! This project is a NFL Combine inspired automated electronic sprint timer that uses ESP32s for communication, VL53L1X motion sensors, and a LCD screen that will display your final elapsed time. How about we use this sprint timer project to test if your speed can compete with a NFL player's speed!

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Kevin Y | Los Gatos High School | Electrical Engineering | Incoming Senior

<!--- **Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.** -->

![Headstone Image](logo.svg)
  
# Final Milestone - Assembled Sprint Timer (Before modifications)

<!--- **Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.** -->

<!--- <iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE --->

## Description - Final Milestone
My final milestone was to complete my final product for my sprint timer before any possible further modifications. This milestone consisted of writing code to make the actual timer, cadding cases for both setups to store all the hardware and other parts, wiring and soldering metal pushbuttons to both the starting and finishing setups, and assembling everything. (not done yet)

## Challenges - Final Milestone
I only really ran into one major challenge when working with my code for the timer. There wasn't anything wrong with the code, but when I ran some trials by just waving my hand over the motion sensors, the elapsed time was inaccurate. Instead of resetting after each trial, the elapsed times kept adding up after each test. At first, I thought it was an issue with my code, but after making multiple changes without avail, I was completely lost. While working with (not done yet)

# Second Milestone - Getting 2 ESP32s to communicate
<iframe width="560" height="315" src="https://www.youtube.com/embed/q5YQB9iJI4Q?si=sCi90vI5DvDdba0C" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Description - 2nd Milestone
My 2nd milestone for my project was to establish communication between the two ESP32s. We need to know the MAC address of the receiving ESP32 to establish communication (Refer to 1st milestone description). First, I ran some simple code to print some random text on the serial monitor just to ensure that there were no issues with my hardware since I ran into multiple hardware problems earlier (Refer to Challenges section). Next, I ran some code to try and verify if the two ESPs could communicate and transfer data. If it was successful, it would print "Sent with success" on the serial monitor. If the receiving ESP successfully received the data, it would print the whole struct message on the serial monitor. Finally, all I had to do was change the struct to include the motion sensor readings so it would be able to be sent to the receiving ESP32 by adding necessary libraries and changing the code to allow the VL53L1X to record distance readings. The finishing setup of my timer includes the receiving ESP32 connected with the finishing VL53L1X motion sensor (Refer to Figure 2). The starting setup includes the sending ESP32 connected with the starting VL53L1X and an LCD screen (Refer to Figure 1). I used ESP-NOW communication to allow communication between my devices. ESP-NOW is a connectionless WiFi communication protocol which allows direct peer-to-peer communication between two devices. It allows communication directly over MAC addresses, which is why I needed to find the MAC address of the receiving ESP32 in my previous milestone. Using ESP-NOW and I2C connections ensured efficient communication and verified that there was successful communication between my two ESP32s, and allows me to start working on the actual timing aspect of my project. 
### SparkFun VL53L1X Motion Sensor
My project uses two SparkFun VL53L1X motion sensors. These two sensors detect when someone starts and ends their sprint. The VL53L1X uses a VCSEL (Vertical Cavity Surface Emitting Laser) and measures the time it takes for the light to reflect back from the object that passes the sensor to determine its distance from the sensor. The VL53L1X can measure distances up to about 4 meters. The SparkFun VL53L1X communicates using I2C protocol. The four pins I used with the VL53L1X were Ground (GND), Power (3.3V), Serial Data (SDA), and Serial Clock (SCL) (Refer to Figure 3). The Serial Data pin creates a data line which allows the process of transmitting and receiving data, and the Serial Clock pin acts as a clock signal which synchronizes data transmission between the motion sensor and any other devices. The Ground pins establishes a common ground between all connected devices, and ensures a stable and consistent voltage. Finally, the power pin provides sufficient power for the VL53L1X, which uses 3.3V. In my project, I used an ESP32 as the master device, and when I want to start a time trial, my code allows the ESP32 to initiate a start condition which begins communication between the ESP and the VL53L1X. 
### 16x2 LCD Screen with I2C Interface
I used a LCD Screen to display the elapsed time of any time trial using my project. The specific LCD display I used has an I2C module connected to it, which allows it to communicate using I2C protocol. 

## Challenges - 2nd Milestone
I ran into a ton of challenges and setbacks while trying to achieve my 2nd milestone. Due to problems with the hardware I was initially working with, I switched to using ESP32s instead of ESP32-S2s and switched to an LCD I2C screen instead of the OLED screen. For my 2nd milestone, I used the approach of simplifying the whole process into many small and simple steps. First, I tried to have one ESP32 send some text to the other ESP32, and it would print a success or failure message based on whether the transfer of information was successful or not. Following that, all I needed to do was to attach one of my VL53L1X sensors to the starting ESP32 and send its readings to the receiving ESP32. At first, ensuring all the code was correct was pretty frustrating, but once I started to go through every line of code one-by-one and learning to understand the function of each line, I was able to fix all my code and verify it without much difficulty. All of these challenges, from errors in my code to frustrating issues with my hardware, taught me this important process of trying to understand everything I was working with along with simplifying any big steps to make things easier and eliminate any major setbacks, and I'll continue to use this method to finish my project to ensure I understand every component of my project to the fullest and to eliminate major setbacks. 
### 2nd Milestone Challenges - Hardware issues
Initially, I used ESP32-S2s and an OLED screen both created by SparkFun. However, when attempting to achieve communication between both ESP32-S2s, nothing seemed to work. I used the code for both the "Start" and "Finish" setups from the SparkFun website instructions for the sprint timer, but nothing worked. According to Arduino IDE, there was nothing wrong with the code. Still, the serial monitor would not print any confirmation that showed communication between the two ESP32-S2s. Additionally, when plugging in the OLED screen to a power source, it just would not turn on. Nothing seemed to be able to power it on. I used a sufficient power source and all the wiring was secure with the use of Qwiic wiring, but the OLED screen just wouldn't turn on. It still wouldn't turn on when I tried running some code provided by SparkFun that was supposed to print a logo on the OLED. By experiencing these setbacks, I concluded it was a hardware issue. However, I didn't know if the VL53L1X motion sensor worked or not. I wasn't able to test it because the ESP32-S2s didn't seem to work either, so I couldn't get any distance readings from it. Therefore, I had to find another way to test if the VL53L1X sensors worked or not. 
### 2nd Milestone Challenges - Overcoming these challenges
In order to test the motion sensor, I started off by using Arduino and I tried to get the motion sensor readings to print on the LCD. I was unsuccessful, so I switched to something simpler by ignoring the LCD and attempting to print the motion sensor readings onto the serial monitor. I tried going through every line of code to try understanding what each line did. Throughout that whole process, I added some comments to my code to help me remember the function of every line. Not only did that allow me to gain a better understanding of my code, but also allowed me to fix everything and verify that it worked. Now I was easily able to get the VL53L1X to print its distance readings on the serial monitor, and changing the code to make it print on the LCD also didn't come with too much difficulty. Once I finished, I was able to confirm that the motion sensor and the LCD worked. 

## Next Steps - 2nd Milestone
Now that I've managed to get my 2 ESP32s to communicate, my next steps are going to be to make it so when the starting motion sensor detects motion such as a person passing through or someone waving their hand across, it will start an elapsed time. That will be the most significant part of my project because that makes my two setups work as an actual sprint timer. Once that is finished, my project is essentially done, but I will still need to do a couple extra steps like cadding and 3d printing covers to store my hardware and make it look like an actual 40-yard dash laser timer that is used in the NFL combine. All that is left after that is to make some slight modifications just to include my project's overall quality. 

# Figure 1 - Starting Setup Schematic
![Schematic Image](Ending Setup.png)
# Figure 2 - Finishing Setup Schematic
![Schematic Image](Starting Setup.png)
# Figure 3 - SparkFun VL53L1X Schematic
![Schematic Image](Motion sensor Schematic.png)
# Figure 4 - LCD Screen Schematic


# First Milestone - Finding the MAC Address of one ESP32-S2
<iframe width="560" height="315" src="https://www.youtube.com/embed/4wfWdBVm-4M?si=NU4qoyfDkIXT_a_3" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Description - 1st Milestone
My first milestone for my Sprint Timer intensive project was to find the Media Access Control(MAC) Address for one SparkFun Thing Plus ESP32-S2. I was provided two of these for the whole project, but we only need to find the MAC address for one of them. A MAC address is a specific 12-digit hexademical number that identifies a specific device on a network. MAC addresses are unique to a device and typically do not change and are hard-coded into any specific device's hardware. Finding the MAC address is important because you will need one of the ESP32-S2's MAC addresses in order to allow both ESPs to communicate between each other, which is needed because they will be connected to motion sensors that will communicate to record the elapsed time for a sprint. The MAC address allows two devices to communicate because it gives a specific designation to one device and allows the network to distinguish between the two devices. In order to obtain the MAC address, I had to run some code through Arduino IDE which would list out the MAC address for the specific ESP32-S2 that I connected to my computer. If the code is correct, the output box will show the MAC address for the hardware that is connected to my computer. The MAC address will be used later in the project to allow both ESPs to communicate with each other, which is necessary to allow this project to work. 

## Challenges - 1st Milestone
I only really ran into one challenge while trying to obtain the MAC address. When first installing the Arduino IDE, I used the ESP32 Starting Guide that was linked to the BlueStamp Student Wiki to set everything up. However, what I didn't realize was that the BlueStamp tutorial was for an ESP32. My project uses ESP32-S2, not ESP32. Thus, when I copied the code from the website onto Arduino IDE and uploaded it, I ended up getting an error that said my code failed uploading because the chip that was connected was ESP32-S2, not ESP32. All I had to do was to change the Arduino IDE ESP32 Dev Module into the ESP32-S2 Dev Module. However, at that initial moment, I didn't realize that the solution was the easy fix of changing the Dev Module. At first, I was clueless on what to do. I tried to look online for help, but Google didn't really even answer my question, so that was useless. It was not until next class when I payed more attention to what I already had on Arduino IDE when I realized that all I had to do was change the Dev Module to work with ESP32-S2. This challenge wasn't a really big roadblock by any means, but it had me very frustrated at first. From this, I learned to pay more attention and really analyze everything I already have and what I could possibly change in my code. 

## Next Steps - 1st Milestone
Now that I have obtained the MAC address for one ESP32-S2, the next steps I need to take will be to connect the ESP32-S2s to their respective hardware using the Qwiic connectors to create the starting and ending motion sensors. Once I've done that, I will need to verify and possibly fix the "Start" and "Finish" Codes for the starting and ending setups. Once the "Start" and "Finish" codes have been verified to work, that will have completed my 2nd milestone, which is to get all the code to work. After that, all that is left of the project will be to test everything to ensure it works, CAD and 3D print a cover, and to assemble everything.

# Bill of Materials

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| (2) Metal Pushbutton with Wires (16mm) | What the item is used for | $8.95 | <a href="https://www.sparkfun.com/metal-pushbutton-momentary-16mm-red.html"> Link </a> |
| 2Pack ESP32 Development Board CP2102 | Allows communication between both the starting and finishing setups for the sprint timer | $12.99 | <a href="https://www.amazon.com/Hosyond-Development-Bluetooth-Microcontroller-Compatible/dp/B09XDMVS9N/ref=sr_1_22_sspa?crid=3J11QQGHEG16C&dib=eyJ2IjoiMSJ9.is-SH_RLGHiZZUrqvTWU_JNOvdR7aKbmm4bb_y393N6jud_4gMIiqQQY-xb6H2GuvezVlU_delmFVm9Oexf_R6g0-RF67ww5hI4c8gPCBnY9VLfm-z9vuyqYhkrb4rjV2HC7t8_wDfdbWkkOiqLcEuCcn_zZVFSIvVcsNNqXS3TpkjOCIsvc5KxUoo_4iwKnZpov2nnurYeClr0k8efW12wn2qQxqotFQmIdnMbD5hU.8AMkbfskSULbXDXii1DfkNUzcJcAn97uuOVhUJgsfdg&dib_tag=se&keywords=esp32&qid=1751583893&sprefix=esp32%2Caps%2C181&sr=8-22-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9idGY&th=1"> Link </a> |
| (2) SparkFun Distance Sensor Breakout - 4mm, VL53L1X | Detects an object crossing the sensor within a threshold which will start or end the sprint timer | $29.95 | <a href="https://www.sparkfun.com/sparkfun-distance-sensor-breakout-4-meter-vl53l1x-qwiic.html"> Link </a> | 
| SparkFun Qwiic Cable Kit | What the item is used for | $12.95 | <a href="https://www.sparkfun.com/sparkfun-qwiic-cable-kit.html"> Link </a> | 
| 16x2 LCD Display with I2C Interface | Displays the elapsed time of a sprint | $7.00 | <a href="https://store-usa.arduino.cc/products/16x2-lcd-display-with-i-c-interface"> Link </a> | 
| (2) Anker PowerCore Slim 10K | Power sources to provide power to the starting and finishing setups | $25.99 | <a href="https://www.anker.com/products/a1229"> Link </a> | 

# Other Resources/Examples
<!--- One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)
To watch the BSE tutorial on how to create a portfolio, click here. --->

# Starter Project: RGB Slider
<iframe width="560" height="315" src="https://www.youtube.com/embed/QllSI647z14?si=3Erbfct-ZkgH6jQq" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe> 

## Description
I chose the RGB Slider for my starter project, and I chose this over the other options simply because I thought it would be cool to work with a little device with LED lights that I'm able to keep. The starter project is used for everyone to practice soldering to create a little project, and this project definitely helped me learn, practice, and get better at soldering. The RGB Slider contains a USB port, LED lights, and 3 sliders. All these materials will need to be soldered to the board. The USB port allows the RGB Slider to work by allowing it to be plugged into an external power source. A good power source could be your computer. The LED contains 3 colored lights: Red, blue, and green. Plugging in the RGB Slider into a power source and sliding the sliders on the board will cause the LEDs to either turn on or turn off. The 3 sliders on the RGB slider allow the lights to turn on or off, and you can choose which color you want to light up by using the corresponding labeled slider. Having multiple sliders on can also cause some of the colors in the light to mix. For example, having all 3 sliders on makes the light white. 
## Challenges
There were a couple of challenges that I faced while I was creating my starter project. The main challenge that came with the starter project was soldering. Before working on this project, I had never soldered anything before, so I had to learn how to do so before starting to create my RGB Slider. I was given a breadboard to practice learning how to solder, but I struggled with it a lot. At first, getting the solder into that cone-like or Hershey's Kisses shape was very difficult for me. However, after a lot of practice, I was able to consistently get that cone-like shape. I started the starter project a lot later than all my classmates since learning and practicing soldering took a very long time, but it allowed the soldering on my RGB Slider to be very good. An additional challenge I faced was that 2 of the 3 color sliders had gotten bent a little bit, which made the process of putting them onto the board more tedious. I eventually managed to get it to work by bending them to get the sliders into the right position, and that allowed me to finally put them onto the board and solder them too. 
## Next Steps
Now that my starter project is completed, I have gained more knowledge and practice with soldering which will help when I eventually get to the soldering portion of my intensive project. I will now be able to start working on my intensive project, which is the 40-Yard Dash Sprint Timer. 

# Appendix - Code
## Milestone 1 Code - Finding the MAC address
```
#include "WiFi.h"

void setup(){
  Serial.begin(115200); // Initializes serial communication
}

void loop(){
  WiFi.mode(WIFI_STA);
  Serial.print("The MAC address for this board is: ");
  Serial.println(WiFi.macAddress());
  while(1){     // This holds the loop, so it doesn't 
    }           // print the info a million times.
}
```
## Milestone 2 Code - Sending ESP32
```
#include <esp_now.h>
#include <WiFi.h>
#include "SparkFun_VL53L1X.h"
#include <Wire.h>
// MAC Address of the receiver ESP32
uint8_t broadcastAddress[] = {0x00, 0x4B, 0x12, 0x2F, 0xBD, 0x30};
// Define struct for sending data
typedef struct struct_message {
  char a[32];
  int b;     // Will hold the distance reading
  float c;
  bool d;
} struct_message;

struct_message myData;
// VL53L1X setup
SFEVL53L1X distanceSensor;
// ESP-NOW peer info
esp_now_peer_info_t peerInfo;

// Callback when data is sent
void OnDataSent(const uint8_t *mac_addr, esp_now_send_status_t status) {
  Serial.print("\r\nLast Packet Send Status:\t");
  Serial.println(status == ESP_NOW_SEND_SUCCESS ? "Delivery Success" : "Delivery Fail");
}

void setup() {
  Serial.begin(115200);
  delay(1000);  // Allow time for serial to start

  // Start I2C
  Wire.begin();

  // Initialize VL53L1X
  if (distanceSensor.begin() != 0) {
    Serial.println("VL53L1X not detected");
    while (1);
  }
  Serial.println("VL53L1X ready");

  // Set up WiFi as STA
  WiFi.mode(WIFI_STA);

  // Init ESP-NOW
  if (esp_now_init() != ESP_OK) {
    Serial.println("Error initializing ESP-NOW");
    return;
  }
  // Register callback and peer
  esp_now_register_send_cb(OnDataSent);
  memcpy(peerInfo.peer_addr, broadcastAddress, 6);
  peerInfo.channel = 0;
  peerInfo.encrypt = false;

  if (esp_now_add_peer(&peerInfo) != ESP_OK) {
    Serial.println("Failed to add peer");
    return;
  }
}

void loop() {
  // Start a ranging measurement
  distanceSensor.startRanging();

  // Wait for data to be ready
  while (!distanceSensor.checkForDataReady()) {
    delay(1);
  }

  // Read distance in mm
  int distance = distanceSensor.getDistance();

  // Stop ranging to save power
  distanceSensor.clearInterrupt();
  distanceSensor.stopRanging();

  // Populate the struct
  strcpy(myData.a, "Distance reading");
  myData.b = distance;
  myData.c = 1.2;      // You can replace this with more sensor data if needed
  myData.d = false;    // Or use this to indicate some event

  // Send the data
  esp_err_t result = esp_now_send(broadcastAddress, (uint8_t *) &myData, sizeof(myData));

  if (result == ESP_OK) {
    Serial.print("Sent distance: ");
    Serial.println(distance);
  } else {
    Serial.println("Error sending the data");
  }

  delay(2000);  // Delay between readings
}
```
## Milestone 2 Code - Receiving ESP32
```
#include <esp_now.h>
#include <WiFi.h>
#include "SparkFun_VL53L1X.h"
#include <Wire.h>

// Structure example to receive data
// Must match the sender structure
typedef struct struct_message {
    char a[32];
    int b;
    float c;
    bool d;
} struct_message;

// Create a struct_message called myData
struct_message myData;

// callback function that will be executed when data is received
void OnDataRecv(const uint8_t * mac, const uint8_t *incomingData, int len) {
  memcpy(&myData, incomingData, sizeof(myData));
  Serial.print("Bytes received: ");
  Serial.println(len);
  Serial.print("Char: ");
  Serial.println(myData.a);
  Serial.print("Int: ");
  Serial.println(myData.b);
  Serial.print("Float: ");
  Serial.println(myData.c);
  Serial.print("Bool: ");
  Serial.println(myData.d);
  Serial.println();
}
 
void setup() {
  // Initialize Serial Monitor
  Serial.begin(115200);

  Serial.println("ESP-NOW Receiver Initialized, waiting for data...");
  
  // Set device as a Wi-Fi Station
  WiFi.mode(WIFI_STA);

  // Init ESP-NOW
  if (esp_now_init() != ESP_OK) {
    Serial.println("Error initializing ESP-NOW");
    return;
  }
  
  // Once ESPNow is successfully Init, we will register for recv CB to
  // get recv packer info
  esp_now_register_recv_cb(OnDataRecv);
}
 
void loop() {

}
```
## Final Milestone Code - Starting/Sending Setup Code
```
#include <esp_now.h>                                  // Library for ESP-NOW communication
#include <WiFi.h>                             
#include <Wire.h>                                     // I2C communication library
#include <LiquidCrystal_I2C.h>                        // LCD I2C library
#include "SparkFun_VL53L1X.h"                         // Sparkfun VL53L1X distance sensor library

LiquidCrystal_I2C lcd(0x27, 16, 2);                   // Initialize 16x2 LCD. I2C Address: 0x27
SFEVL53L1X distanceSensor;                            // Create instance of distance sensor

uint8_t finishMac[] = {0x00, 0x4B, 0x12, 0x2F, 0xBD, 0x30}; // MAC address of finishing ESP32

typedef struct struct_message {
  char msgType[10];                                   // Message says either "START" or "STOP"
  unsigned long timestamp;                            // Timestamp in milliseconds
} struct_message;

struct_message messageToSend;                         // Message to send to finish ESP32
bool timingStarted = false;                           // Indicates if timing has started
unsigned long startTime = 0;                          // Variable to store start time

// Callback function when data is received from another ESP32
void OnDataRecv(const uint8_t * mac, const uint8_t *incomingData, int len) {
  struct_message received;                            // Temporary structure to hold incoming data
  memcpy(&received, incomingData, sizeof(received));  // Copy received data into structure

  // If STOP message is received and timing was started
  if (strcmp(received.msgType, "STOP") == 0 && timingStarted) {
    unsigned long endTime = millis();                 // Record current time as end time
    unsigned long elapsed = endTime - startTime;      // Calculate elapsed time

    lcd.clear();                                      // Clear LCD
    lcd.setCursor(0, 0);                              
    lcd.print("Time:");                               
    lcd.setCursor(0, 1);                              
    lcd.print(elapsed / 1000.0, 2);                   // Display elapsed time in seconds (2 decimals)
    lcd.print(" sec");                                // Units

    Serial.print("Elapsed Time: ");                   // Prints elapsed time to Serial Monitor
    Serial.println(elapsed);

    timingStarted = false;                            // Resets timing
  }
}

void setup() {
  Serial.begin(115200);                               // Start Serial Monitor
  Wire.begin();                                       // Initialize I2C communication
  lcd.init();                                         // Initialize LCD screen
  lcd.backlight();                                    // Turn on LCD backlight
  lcd.setCursor(0, 0);                        
  lcd.print("Ready...");                      

  if (distanceSensor.begin() != 0) {                  // Initialize distance sensor
    Serial.println("Sensor fail");                    // If fails, prints an error message
    while (1);                                        
  }

  distanceSensor.setDistanceModeLong();               // Set sensor to long-distance mode
  distanceSensor.startRanging();                      // Start measuring distance

  WiFi.mode(WIFI_STA);                                // Set WiFi to Station mode (required for ESP-NOW)
  WiFi.disconnect();                                  // Disconnect from any previous WiFi

  if (esp_now_init() != ESP_OK) {                     // Initialize ESP-NOW
    Serial.println("ESP-NOW failed");                 // Print error if failed
    return;                                   
  }

  esp_now_register_recv_cb(OnDataRecv);               // Register callback for receiving data

  esp_now_peer_info_t peerInfo = {};                  // Create peer info struct
  memcpy(peerInfo.peer_addr, finishMac, 6);           // Set peer MAC address
  peerInfo.channel = 0;                               
  peerInfo.encrypt = false;                           

  if (!esp_now_add_peer(&peerInfo)) {                 // Add the peer
    Serial.println("Peer added");                     // Confirm peer was added
  }
}

void loop() {
  // If timing hasn't started and new distance data is ready
  if (!timingStarted && distanceSensor.checkForDataReady()) {
    uint16_t distance = distanceSensor.getDistance(); // Read distance in mm
    distanceSensor.clearInterrupt();                  // Clear sensor interrupt

    Serial.print("Distance: ");                       
    Serial.println(distance);                         // Debug: print distance

    if (distance < 100) {                             // Threshold of 100mm (Won't start timing unless an object makes it within the threshold)
      startTime = millis();                           // Records time
      messageToSend.timestamp = startTime;            // Include timestamp in message
      strcpy(messageToSend.msgType, "START");         

      esp_now_send(finishMac, (uint8_t *)&messageToSend, sizeof(messageToSend)); // Send start message

      lcd.clear();                                    
      lcd.setCursor(0, 0);
      lcd.print("Timing...");                         // Display "Timing..." on LCD. Indicates that timer is running
      Serial.println("Start detected");              
      timingStarted = true;                           // Flag that timing has started
    }
  }
}
```
## Final Milestone Code - Finishing/Receiving Setup Code
```
#include <esp_now.h>                          // ESP-NOW communication library
#include <WiFi.h>                             // Required for setting WiFi mode
#include <Wire.h>                             // I2C communication library
#include "SparkFun_VL53L1X.h"                 // VL53L1X distance sensor library

SFEVL53L1X distanceSensor;                    // Create instance of distance sensor

uint8_t startMac[] = {0x38, 0x18, 0x2B, 0x89, 0xEE, 0xBC}; // MAC address of starting ESP32

typedef struct struct_message {
  char msgType[10];                           // Message type: "START" or "STOP"
  unsigned long timestamp;                    
} struct_message;

bool objectDetected = false;                  // Flag to prevent multiple triggers

void setup() {
  Serial.begin(115200);                       // Start Serial Monitor
  Wire.begin();                               // Initialize I2C communication

  if (distanceSensor.begin() != 0) {          // Initialize sensor
    Serial.println("Sensor fail");            // Print error if initialization fails
    while (1);                                
  }

  distanceSensor.setDistanceModeLong();       // Set long range mode
  distanceSensor.startRanging();              // Start distance measurements

  WiFi.mode(WIFI_STA);                        // Set WiFi mode to Station
  WiFi.disconnect();                          // Disconnects from any previous WiFi connections

  if (esp_now_init() != ESP_OK) {             // Initialize ESP-NOW
    Serial.println("ESP-NOW failed");         // If it fails, print error message and stop
    return;
  }

  esp_now_peer_info_t peerInfo = {};          // Create peer info struct
  memcpy(peerInfo.peer_addr, startMac, 6);    // Set peer address (start ESP32)
  peerInfo.channel = 0;                       // Default channel
  peerInfo.encrypt = false;                   

  esp_now_add_peer(&peerInfo);                // Add peer (start ESP32)
}

void loop() {
  if (distanceSensor.checkForDataReady()) {           // Check if new distance data is available
    uint16_t distance = distanceSensor.getDistance(); // Read distance
    distanceSensor.clearInterrupt();                  // Clear interrupt for next reading

    Serial.print("Distance: ");               
    Serial.println(distance);                         // Print distance to Serial

    if (distance < 100 && !objectDetected) {          // If object within 100mm and not already detected
      struct_message stopMsg;                         // Create STOP message
      strcpy(stopMsg.msgType, "STOP");                // Set message type
      stopMsg.timestamp = millis();                   // Optional timestamp

      // Send STOP signal back to start ESP32
      esp_err_t result = esp_now_send(startMac, (uint8_t *)&stopMsg, sizeof(stopMsg));
      if (result == ESP_OK) {
        Serial.println("Stop signal sent");           // Confirm send
      } else {
        Serial.print("Send failed: ");                // Reports failure
        Serial.println(result);
      }

      objectDetected = true;                          // Mark object as detected
    } else if (distance > 300) {                      // If object is out of range (Won't be declared an object)
      objectDetected = false;                         // Reset detection flag
    }
  }
}
```
