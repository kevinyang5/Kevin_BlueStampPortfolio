# 40-Yard Dash Sprint Timer 
<!--- Replace this text with a brief description (2-3 sentences) of your project. This description should draw the reader in and make them interested in what you've built. You can include what the biggest challenges, takeaways, and triumphs from completing the project were. As you complete your portfolio, remember your audience is less familiar than you are with all that your project entails! -->

<!--- You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions: --->
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

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



# Second Milestone

<!--- **Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone --->

# Schematics 
<!--- Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. --->

# Code
<!--- Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs.

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
``` --->

# First Milestone - Finding the MAC Address of one ESP32-S2

 **Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


# Description - 1st Milestone
My first milestone for my Sprint Timer intensive project was to find the Media Access Control(MAC) Address for one SparkFun Thing Plus ESP32-S2. I was provided two of these for the whole project, but we only need to find the MAC address for one of them. A MAC address is a specific 12-digit hexademical number that identifies a specific device on a network. MAC addresses are unique to a device and typically do not change and are hard-coded into any specific device's hardware. Finding the MAC address is important because you will need one of the ESP32-S2's MAC addresses in order to allow both ESPs to communicate between each other, which is needed because they will be connected to motion sensors that will communicate to record the elapsed time for a sprint. The MAC address allows two devices to communicate because it gives a specific designation to one device and allows the network to distinguish between the two devices. In order to obtain the MAC address, I had to run some code through Arduino IDE which would list out the MAC address for the specific ESP32-S2 that I connected to my computer. If the code is correct, the output box will show the MAC address for the hardware that is connected to my computer. The MAC address will be used later in the project to allow both ESPs to communicate with each other, which is necessary to allow this project to work. 

# Challenges - 1st Milestone
I only really ran into one challenge while trying to obtain the MAC address. When first installing the Arduino IDE, I used the ESP32 Starting Guide that was linked to the BlueStamp Student Wiki to set everything up. However, what I didn't realize was that the BlueStamp tutorial was for an ESP32. My project uses ESP32-S2, not ESP32. Thus, when I copied the code from the website onto Arduino IDE and uploaded it, I ended up getting an error that said my code failed uploading because the chip that was connected was ESP32-S2, not ESP32. All I had to do was to change the Arduino IDE ESP32 Dev Module into the ESP32-S2 Dev Module. However, at that initial moment, I didn't realize that the solution was the easy fix of changing the Dev Module. At first, I was clueless on what to do. I tried to look online for help, but Google didn't really even answer my question, so that was useless. It was not until next class when I payed more attention to what I already had on Arduino IDE when I realized that all I had to do was change the Dev Module to work with ESP32-S2. This challenge wasn't a really big roadblock by any means, but it had me very frustrated at first. From this, I learned to pay more attention and really analyze everything I already have and what I could possibly change in my code. 

# Code - 1st Milestone
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
