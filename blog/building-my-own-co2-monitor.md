---
title: 'Building my own CO2 monitor'
date: '2024-04-07T05:21:37-04:00'
author: Dries
summary: 'How I created a CO2 monitoring system for our bedroom and uncovered some surprising insights about air quality.'
image: blog/esp32-s3-with-scd41
tags:
  - Electronics
  - ESP32
featured: true
published: true
type: blog
url: /building-my-own-co2-monitor
id: 5596
---

For years, I have worried about the [CO<sub>2</sub>](https://en.wikipedia.org/wiki/Carbon_dioxide) levels in our kids' bedroom. Until recently, our two sons shared a small bedroom in our apartment. Every night, they insisted on shutting the door to block out light and noise. Yet, once they fell asleep, I'd quietly open the door to make sure they had enough fresh air to fuel their dreams.

As we breathe, our bodies naturally expel CO<sub>2</sub> (carbon dioxide). When CO<sub>2</sub> reacts with water within our body it becomes [carbonate](https://en.wikipedia.org/wiki/Carbonate), which can subtly shift our body's internal balance. That is why high CO<sub>2</sub> levels, like in sealed bedrooms, can be harmful.

Outdoor CO<sub>2</sub> levels average around 400 ppm (parts per million), but indoor levels are considered healthy up to 800 ppm. Between 800 and 1200 ppm, minor discomfort may begin, and levels above 2,000 ppm indicate poor air quality, posing health risks.

A [pivotal study by Harvard University](https://iopscience.iop.org/article/10.1088/1748-9326/ac1bd8/meta) found that for every 500 ppm increase in CO<sub>2</sub>, cognitive response times slow by 1.4-1.8%, and productivity decreases by 2.1-2.4%. Furthermore, [another study](https://link.springer.com/chapter/10.1007/978-981-13-9520-8_99) links high CO<sub>2</sub> levels to reduced sleep quality. These findings highlight the effects of indoor CO<sub>2</sub> levels on both our physical health, mental performance and sleep quality.

After developing [my own thermometer](https://dri.es/building-my-own-temperature-and-humidity-monitor), I grew interested in CO<sub>2</sub> monitoring. Although there are many commercial CO<sub>2</sub> detectors available, I opted to build my own CO<sub>2</sub> monitor using my thermometer project as the starting point. Replacing the temperature and humidity sensor with a CO<sub>2</sub> sensor was a straightforward process.

It did require a deep dive into CO<sub>2</sub> sensors, which led me to the Sensirion SCD41 sensor. Unlike many other CO<sub>2</sub> sensors that merely estimate CO<sub>2</sub> levels, the SCD41 sensor utilizes advanced photoacoustic NDIR technology to accurately measure the actual CO<sub>2</sub> concentrations. According to the [documentation](https://sensirion.com/media/documents/9E7DA521/627C2C8D/CD_IN_SCDxx_Transmissive_and_photoacoustic_NDIR_sensing_D1.pdf):

> The SCD4x series is based on photoacoustic NDIR technology. The technology exploits the characteristic property of CO<sub>2</sub> molecules to strongly absorb infra-red (IR) light with wavelengths around 4.2 µm. When shining light of this wavelength through a gas sample, the CO<sub>2</sub> concentration can thus be calculated from the proportion of light that is absorbed.

<div class="large">
  [image blog/esp32-s3-with-scd41]
</div>

My ESP32 device measures CO<sub>2</sub> levels every few minutes, connects to WiFi and sends this data to my web service endpoint at `https://dri.es/sensors`. This endpoint processes and visualizes the data. Unlike [our basement temperature](https://dri.es/sensors/basement-belgium), I've chosen to keep the CO<sub>2</sub> data private and not available to the public.

After I updated the client code on the ESP32 development board to use the new sensor, I also had to make small adjustments to the backend code used for data visualization.

Once I got everything working, I sneaked my project into our bedroom, sidestepping any objections by Vanessa, about turning our bedroom into a gadget lab.

The next morning, I was met with some surprising data: CO<sub>2</sub> levels had spiked to 2,500 ppm! This was unexpected as we always sleep with the door slightly open and a ceiling fan on low.

[image blog/co2-bedroom-before resize=false]

Such high CO<sub>2</sub> levels, as highlighted in Harvard University's research, can adversely impact sleep quality and cognitive functions.

After triple checking my code and monitoring the levels for several more nights, the trend was clear: CO<sub>2</sub> concentrations consistently increased overnight, reaching levels beyond the recommended guidelines.

Armed with a few days of data, I presented my discoveries to Vanessa. Initially met with her characteristic skepticism (read: an eye-roll), she swiftly enabled the air cycling mode on our Nest thermostat. This function automatically activates the fan to circulate air, ensuring fresh air without the need to heat or cool.

The graph below shows how using the air cycling mode on our thermostat significantly improved CO<sub>2</sub> levels in our bedroom. It proved to be much more effective than just keeping the door open and relying on a ceiling fan. What took me several nights to construct and analyze, Vanessa remedied in under a minute.

[image blog/co2-bedroom-after resize=false]

Of course, opening a window is a simple method to improve indoor air quality and would likely reduce CO<sub>2</sub> levels more effectively than the Nest's air cycling mode. However, I'm told that living in a city and having white curtains makes us hesitant to do so.

Nevertheless, this project highlights how a bit of curiosity and creativity can enhance the health and comfort of our living spaces.

Starting your own CO<sub>2</sub> monitor project can be an exciting and rewarding endeavor. In the rest of this blog post, I'll help you get started. I've detailed my hardware setup and provided the client-side code. As mentioned, the backend code builds on [my thermometer project](https://dri.es/building-my-own-temperature-and-humidity-monitor), so please consult that for further details.

### Hardware used

For this project, I bought:

1. [Adafruit ESP32-S3 Feather](https://www.adafruit.com/product/5323): A microcontroller board with Wi-Fi and Bluetooth capabilities, serving as the central processing unit of my project.
2. [Adafruit SCD41 sensor](https://www.adafruit.com/product/5190): A high-accuracy CO<sub>2</sub> and temperature sensor.
3. [3.7v 500mAh battery](https://www.adafruit.com/product/1578): A small and portable power source.
4. [STEMMA QT / Qwiic JST SH 4-pin cable](https://www.adafruit.com/product/4399): To connect the sensor to the board without soldering.

### Client code

What I also love about [Sensirion](https://sensirion.com/) is that they have Arduino libraries for their sensors, including for the SCD4x series (<https://github.com/Sensirion/arduino-i2c-scd4x>). These can easily be installed through Adafruit IDE.

[image blog/sensirion-scd4x-installation-arduino-ide schema=false resize=false]

Once installed, incorporating it into your project is straightforward–simply include `#include "SensirionI2CScd4x.h"` in your code.

Below is the complete client code. It comes with very detailed code comments to make it easy to understand.

```c
#include "SensirionI2CScd4x.h"
#include "Adafruit_MAX1704X.h"
#include "WiFiManager.h"
#include "ArduinoJson.h"
#include "HTTPClient.h"
#include "Wire.h"

// The Adafruit_SCD4x sensor is a CO2, temperature and humidity sensor with 
// an I2C interface.
SensirionI2CScd4x scd4x;

// The Adafruit ESP32-S3 Feather comes with a built-in MAX17048 LiPoly / LiIon
// battery monitor. The MAX17048 provides accurate monitoring of the battery's
// voltage. Utilizing the Adafruit library helps us not only obtain the raw
// voltage data from the battery cell, but also converts this data into a more
// intuitive battery percentage or charge level. We will pass on the battery
// percentage to the web service endpoint, which can visualize it or use it to 
// send notifications when the battery needs recharging.
Adafruit_MAX17048 maxlipo;

// The setup() function is used to initialize the device's hardware and 
// communications. It's executed once at startup. Here, we begin serial 
// communication, initialize sensors, connect to Wi-Fi, and send initial 
// data. 
void setup() {
  Serial.begin(115200);

  // Wait for the serial connection to establish before proceeding further.
  // This is crucial for boards with native USB interfaces. Without this loop,
  // initial output sent to the serial monitor is lost. This code is not
  // needed when running on battery.
  // delay(5000);

  // Generates a unique device ID from a segment of the MAC address. 
  // Since the MAC address is permanent and unchanged after reboots, 
  // this guarantees the device ID remains consistent. To achieve a 
  // compact ID, only a specific portion of the MAC address is used, 
  // specifically the range between 0x10000 and 0xFFFFF. This range 
  // translates to a hexadecimal string of a fixed 5-character length, 
  // giving us roughly 1 million unique IDs. This approach balances 
  // uniqueness with compactness.
  uint64_t chipid = ESP.getEfuseMac();
  uint32_t deviceValue = ((uint32_t)(chipid >> 16) & 0x0FFFFF) | 0x10000;
  char device[6]; // 5 characters for the hex representation + the null terminator.
  sprintf(device, "%x", deviceValue); // Use '%x' for lowercase hex letters

  // Initialize the MAX17048 sensor.
  if (maxlipo.begin()) {
   Serial.println(F("MAX17048 battery monitor initialized."));
  }
  else {
   Serial.println(F("Could not find MAX17048 battery monitor!"));
   return;
  }

  // Initialize the SHT4x sensor.
  scd4x.begin(Wire);

  uint16_t error;

  // Adjust the temperature sensor's offset to 1 degree to correct for deviations,
  // including sensor self-heating and environmental factors (e.g., sun exposure).
  // The factory default is 4 degrees. Customize this offset for your specific
  // environment to enhance the accuracy of temperature readings.
  error = scd4x.setTemperatureOffset(1.0);
  if (error) {
   Serial.print(F("Error trying to set temperature offset: "));
   Serial.println(error);
   return;
  }

  // Initiate a one-time measurement of CO2 concentration, relative humidity, and
  // temperature. We use "single shot" mode, which means the sensor performs a
  // one-time measurement. This process takes approximately 5 seconds to complete.
  // After the measurement, the result is available for retrieval.
  error = scd4x.measureSingleShot();
  if (error) {
   Serial.print(F("Error trying to put sensor in single shot mode: "));
   Serial.println(error);
   return;
  }

  // Implement a delay of 1 second before initiating the next measurement. This
  // delay helps ensure the sensor has adequate time to prepare for the next
  // reading. This practice aligns with general sensor operation guidelines,
  // where a brief pause between measurements can help in achieving more accurate
  // and stable readings by allowing the sensor's internal components to stabilize.
  delay(1000);

  // According to the sensor's datasheet, we should ignore the first CO2 reading
  // after the sensor has been powered on or reset. The rationale behind this is
  // that the sensor's readings need one measurement to stabilize. Thus, we
  // perform a second "single shot" measurement, and use the results of this
  // second reading.
  error = scd4x.measureSingleShot();
  if (error) {
   Serial.print(F("Error trying to put sensor in single shot mode: "));
   Serial.println(error);
   return;
  }

  // Read the CO2, temperature and humidity values from the sensor.
  uint16_t co2 = 0;
  float temperature = 0.0f;
  float humidity = 0.0f;
  error = scd4x.readMeasurement(co2, temperature, humidity);
  if (error) {
   Serial.print(F("Error trying to read measurement: "));
   Serial.println(error);
   return;
  } 

  // Read the battery charge level and cap it at 100%. This step corrects any
  // readings above 100%, which seems to occur due to measurement anomalies or
  // calculation inaccuracies. This ensures the displayed or reported battery
  // level is credible.
  float batteryPercent = maxlipo.cellPercent();
  batteryPercent = (batteryPercent > 100) ? 100 : batteryPercent;

  WiFiManager wifiManager;

  // Uncomment the following line to erase all saved WiFi credentials.
  // This can be useful for debugging or reconfiguration purposes.
  // wifiManager.resetSettings();
  
  // This WiFi manager attempts to establish a WiFi connection using known
  // credentials, stored in RAM. If it fails, the device will switch to Access
  // Point mode, creating a network named "Temperature Monitor". In this mode, 
  // connect to this network, navigate to the device's IP address (default IP
  // is 192.168.4.1) using a web browser, and a configuration portal will be 
  // presented, allowing you to enter new WiFi credentials. Upon submission, 
  // the device will reboot and try connecting to the specified network with 
  // these new credentials.
  if (!wifiManager.autoConnect("CO2 Monitor")) {
   Serial.println(F("Failed to connect to WiFi ..."));

   // If the device fails to connect to WiFi, it will restart to try again.
   // This approach is useful for handling temporary network issues. However,
   // in scenarios where the network is persistently unavailable (e.g. router
   // down for more than an hour, consistently poor signal), the repeated
   // restarts and WiFi connection attempts can quickly drain the battery.
   ESP.restart();

   // Mandatory delay to allow the restart process to initiate properly.
   delay(1000);

   return;
  }

  // Send collected data as JSON to the specified URL.
  sendJsonData("https://dri.es/sensors", device, co2, temperature, humidity, batteryPercent);

  // WiFi consumes significant power so turn it off when done.
  WiFi.disconnect(true); 
 
  // Enter deep sleep for 10 minutes. The ESP32-S3's deep sleep mode minimizes 
  // power consumption by powering down most components, except the RTC. This
  // mode is efficient for battery-powered projects where constant operation 
  // isn't needed. When the device wakes up after the set period, it runs
  // setup() again, as the state  isn't preserved.
  Serial.println(F("Going to sleep for 10 minutes ..."));
  ESP.deepSleep(10 * 60 * 1000000); // 10 mins * 60 secs/min * 1,000,000 μs/sec.
}

bool sendJsonData(const char* url, const char* device, float co2, float temperature, float humidity, float battery) {

  StaticJsonDocument<200> doc;

  // Round floating-point values to one decimal place for efficient data
  // transmission. This approach reduces the JSON payload size, which is
  // important for IoT applications running on battery.
  doc["device"] = device;
  doc["co2"] = String(co2, 0);
  doc["temperature"] = String(temperature, 1);
  doc["humidity"] = String(humidity, 1);
  doc["battery"] = String(battery, 0);

  // Serialize JSON to a string.
  String jsonData;
  serializeJson(doc, jsonData);

  // Initialize an HTTP client with the provided URL.
  HTTPClient httpClient;
  httpClient.begin(url);
  httpClient.addHeader("Content-Type", "application/json");

  // Send a HTTP POST request.
  int httpCode = httpClient.POST(jsonData); 

  // Close the HTTP connection.
  httpClient.end();

  // Print debug information to the serial console.
  Serial.println("Sent '" + jsonData + "' to " + String(url) + ", return code " + httpCode);
  
  return (httpCode == 200);
}

void loop() {
  // The ESP32-S3 resets and runs setup() after waking up from deep sleep,
  // making this continuous loop unnecessary.
}
```
