# 40-Yard Dash Sprint Timer 
<!--- Replace this text with a brief description (2-3 sentences) of your project. This description should draw the reader in and make them interested in what you've built. You can include what the biggest challenges, takeaways, and triumphs from completing the project were. As you complete your portfolio, remember your audience is less familiar than you are with all that your project entails! -->

<!--- You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions: --->

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Kevin Y | Los Gatos High School | Electrical Engineering | Incoming Senior

<!--- **Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.** -->

![Headstone Image](logo.svg)
  
# Final Milestone

<!--- **Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.** -->

<!--- <iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE --->



# Second Milestone - Getting 2 ESP32s to communicate
<iframe width="560" height="315" src="https://www.youtube.com/embed/q5YQB9iJI4Q?si=sCi90vI5DvDdba0C" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<!--- For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone --->

# Description - 2nd Milestone
My 2nd milestone for my Sprint Timer was to allow both of my ESP32s to communicate with each other. In order to allow two ESP32s to communicate, we need to know the MAC address of the ESP32 that will receive the information. I found the MAC address by running a couple lines of code, which is shown in the 1st milestone documentation. In order to test if the two ESP32s could communicate, I tried a couple different methods to verify that the two ESP32s were able to communicate. First, I ran some simple code to print some random text on the serial monitor just to ensure that there were no issues with my hardware since I ran into multiple hardware problems earlier which I'll go into more detail about when talking about my challenges. Next, I ran some code that would attempt to verify that the sending ESP had the ability to send information and that the receiving ESP was able to receive the information being sent by the sending ESP. If the delivery of data was successful, it would print "Sent with success" on the serial monitor. If the receiving ESP successfully received the data, it would print the whole struct message on the serial monitor. (Not done yet)

# Challenges - 2nd Milestone
I ran into a lot of challenges while trying to achieve my 2nd milestone. Initially, I used ESP32-S2s and an OLED screen both created by SparkFun. However, when attempting to achieve communication between both ESP32-S2s, nothing seemed to work. I used the code for both the "Start" and "Finish" setups from the SparkFun website instructions for the sprint timer, but nothing printed on the serial monitor that showed any sort of communication between the two ESP32-S2s. According to Arduino IDE, there was nothing inherently wrong with the code, and everything was verified. Still, the serial monitor would not print any confirmation that showed the two ESP32-S2s sending and receiving information. Additionally, when plugging in the OLED screen to a power source, it just would not turn on. Nothing I did seemed to make it turn on. By experiencing these setbacks, I concluded it was a hardware issue. However, I didn't know if the VL53L1x motion sensor worked or not. I wasn't able to test it because the ESP32-S2s didn't seem to work either, so I couldn't get any distance readings from it. I had to find some other way to test if the motion sensor worked or not. As a result, I switched to using ESP32s instead of ESP32-S2s and switched to an LCD I2C screen instead of the OLED screen. (not done yet)

# Next Steps - 2nd Milestone
Now that I've managed to get my 2 ESP32s to communicate, my next steps are going to be to make it so when the starting motion sensor detects motion such as a person passing through or someone waving their hand across, it will start an elapsed time. That will be the most significant part of my project because that makes my two setups work as an actual sprint timer. Once that is finished, my project is essentially done, but I will still need to do a couple extra steps like cadding and 3d printing covers to store my hardware and make it look like an actual 40-yard dash laser timer that is used in the NFL combine. All that is left after that is to make some slight modifications just to include my project's overall quality. 

# Schematics 
<!--- Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. --->

# First Milestone - Finding the MAC Address of one ESP32-S2
<iframe width="560" height="315" src="https://www.youtube.com/embed/4wfWdBVm-4M?si=NU4qoyfDkIXT_a_3" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

# Description - 1st Milestone
My first milestone for my Sprint Timer intensive project was to find the Media Access Control(MAC) Address for one SparkFun Thing Plus ESP32-S2. I was provided two of these for the whole project, but we only need to find the MAC address for one of them. A MAC address is a specific 12-digit hexademical number that identifies a specific device on a network. MAC addresses are unique to a device and typically do not change and are hard-coded into any specific device's hardware. Finding the MAC address is important because you will need one of the ESP32-S2's MAC addresses in order to allow both ESPs to communicate between each other, which is needed because they will be connected to motion sensors that will communicate to record the elapsed time for a sprint. The MAC address allows two devices to communicate because it gives a specific designation to one device and allows the network to distinguish between the two devices. In order to obtain the MAC address, I had to run some code through Arduino IDE which would list out the MAC address for the specific ESP32-S2 that I connected to my computer. If the code is correct, the output box will show the MAC address for the hardware that is connected to my computer. The MAC address will be used later in the project to allow both ESPs to communicate with each other, which is necessary to allow this project to work. 

# Challenges - 1st Milestone
I only really ran into one challenge while trying to obtain the MAC address. When first installing the Arduino IDE, I used the ESP32 Starting Guide that was linked to the BlueStamp Student Wiki to set everything up. However, what I didn't realize was that the BlueStamp tutorial was for an ESP32. My project uses ESP32-S2, not ESP32. Thus, when I copied the code from the website onto Arduino IDE and uploaded it, I ended up getting an error that said my code failed uploading because the chip that was connected was ESP32-S2, not ESP32. All I had to do was to change the Arduino IDE ESP32 Dev Module into the ESP32-S2 Dev Module. However, at that initial moment, I didn't realize that the solution was the easy fix of changing the Dev Module. At first, I was clueless on what to do. I tried to look online for help, but Google didn't really even answer my question, so that was useless. It was not until next class when I payed more attention to what I already had on Arduino IDE when I realized that all I had to do was change the Dev Module to work with ESP32-S2. This challenge wasn't a really big roadblock by any means, but it had me very frustrated at first. From this, I learned to pay more attention and really analyze everything I already have and what I could possibly change in my code. 

# Next Steps - 1st Milestone
Now that I have obtained the MAC address for one ESP32-S2, the next steps I need to take will be to connect the ESP32-S2s to their respective hardware using the Qwiic connectors to create the starting and ending motion sensors. Once I've done that, I will need to verify and possibly fix the "Start" and "Finish" Codes for the starting and ending setups. Once the "Start" and "Finish" codes have been verified to work, that will have completed my 2nd milestone, which is to get all the code to work. After that, all that is left of the project will be to test everything to ensure it works, CAD and 3D print a cover, and to assemble everything.

# Bill of Materials

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| (2) Metal Pushbutton with Wires (16mm) | What the item is used for | $8.95 | <a href="https://www.sparkfun.com/metal-pushbutton-momentary-16mm-red.html"> Link </a> |
| (2) SparkFun Thing Plus - ESP32-S2 | What the item is used for | $24.50 | <a href="https://www.sparkfun.com/sparkfun-thing-plus-esp32-s2-wroom.html"> Link </a> |
| (2) SparkFun Distance Sensor Breakout - 4mm, VL53L1X (Qwiic) | What the item is used for | $29.95 | <a href="https://www.sparkfun.com/sparkfun-distance-sensor-breakout-4-meter-vl53l1x-qwiic.html"> Link </a> | 
| SparkFun Qwiic Cable Kit | What the item is used for | $12.95 | <a href="https://www.sparkfun.com/sparkfun-qwiic-cable-kit.html"> Link </a> | 
| SparkFun Qwiic OLED Display (0.91 in., 128x32) | What the item is used for | $10.95 | <a href="https://www.sparkfun.com/sparkfun-qwiic-oled-display-0-91-in-128x32-lcd-24606.html"> Link </a> | 
| (2) Anker PowerCore Slim 10K | What the item is used for | $25.99 | <a href="https://www.anker.com/products/a1229"> Link </a> | 

# Other Resources/Examples
<!--- One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here. --->

# Starter Project: RGB Slider
<iframe width="560" height="315" src="https://www.youtube.com/embed/QllSI647z14?si=3Erbfct-ZkgH6jQq" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe> 

# Description
I chose the RGB Slider for my starter project, and I chose this over the other options simply because I thought it would be cool to work with a little device with LED lights that I'm able to keep. The starter project is used for everyone to practice soldering to create a little project, and this project definitely helped me learn, practice, and get better at soldering. The RGB Slider contains a USB port, LED lights, and 3 sliders. All these materials will need to be soldered to the board. The USB port allows the RGB Slider to work by allowing it to be plugged into an external power source. A good power source could be your computer. The LED contains 3 colored lights: Red, blue, and green. Plugging in the RGB Slider into a power source and sliding the sliders on the board will cause the LEDs to either turn on or turn off. The 3 sliders on the RGB slider allow the lights to turn on or off, and you can choose which color you want to light up by using the corresponding labeled slider. Having multiple sliders on can also cause some of the colors in the light to mix. For example, having all 3 sliders on makes the light white. 
# Challenges
There were a couple of challenges that I faced while I was creating my starter project. The main challenge that came with the starter project was soldering. Before working on this project, I had never soldered anything before, so I had to learn how to do so before starting to create my RGB Slider. I was given a breadboard to practice learning how to solder, but I struggled with it a lot. At first, getting the solder into that cone-like or Hershey's Kisses shape was very difficult for me. However, after a lot of practice, I was able to consistently get that cone-like shape. I started the starter project a lot later than all my classmates since learning and practicing soldering took a very long time, but it allowed the soldering on my RGB Slider to be very good. An additional challenge I faced was that 2 of the 3 color sliders had gotten bent a little bit, which made the process of putting them onto the board more tedious. I eventually managed to get it to work by bending them to get the sliders into the right position, and that allowed me to finally put them onto the board and solder them too. 
# Next Steps
Now that my starter project is completed, I have gained more knowledge and practice with soldering which will help when I eventually get to the soldering portion of my intensive project. I will now be able to start working on my intensive project, which is the 40-Yard Dash Sprint Timer. 

# Milestone 2 Code - Sending ESP32
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

# Milestone 2 Code - Receiving ESP32
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

# Milestone 1 Code
```
#include "WiFi.h"

void setup(){
  Serial.begin(115200);

}

void loop(){
  WiFi.mode(WIFI_STA);
  Serial.print("The MAC address for this board is: ");
  Serial.println(WiFi.macAddress());
  while(1){     // This holds the loop, so it doesn't 
    }           // print the info a million times.
}
``` 
