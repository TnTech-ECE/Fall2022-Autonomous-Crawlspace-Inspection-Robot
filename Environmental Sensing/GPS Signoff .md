# Function of the subsystem:

The robot will use a GPS subsystem to track its location in real-time, which will help improve environmental data collection. By integrating GPS, the robot can continuously determine its precise coordinates, enhancing the accuracy and efficiency of data collection. It can navigate to specific locations based on GPS coordinates, allowing for targeted data collection from different points of interest. This approach enables more precise data gathering.

The team chose the M10Q-5883 GNSS GPS & Compass Module, for the function of real-time location tracking to improve environmental data collection in a robot.

The GPS subsystem works with the top-level controller and robotic operating system (ROS). The controller manages different parts of the robot and can use GPS data along with other sensors to make decisions and control its actions. ROS helps the GPS subsystem connect with other systems like mapping and path planning, making everything work together smoothly.

## Function:
The GPS subsystem helps the robot know exactly where it is at all times. It uses a special module called M10Q-5883 GNSS GPS & Compass to track its location accurately and continuously.

- The GPS subsystem communicates with the top-level controller, providing real-time location data that helps the controller make decisions and control the robot's actions.
- The GPS subsystem integrates with the robotic operating system (ROS), which allows it to seamlessly exchange data with other systems in the robot.
- The GPS subsystem shares its location data with mapping and path planning modules in ROS, enabling the robot to navigate to specific locations for targeted data collection.
- The GPS subsystem collaborates with other sensors, sharing its location data to enhance the robot's ability to gather accurate environmental data by combining information from multiple sources.

# Constraints:
First constraint that we need to considered is the GPS Signal Acquisition. The robot operates in an environment with limited sky visibility, it may struggle to acquire a strong GPS signal, leading to inaccurate or intermittent readings.

Second constraint that we need to considered is accuracy of GPS readings. The accuracy of GPS readings can be quantified using metrics such as horizontal accuracy, vertical accuracy, and time accuracy. 

Third constraint that we need to considered is environmental constraints. Environmental factors, such as signal blockage or degradation, can be modeled using signal propagation models. These models consider factors such as distance, obstacles, and signal attenuation to predict the quality of the GPS signal in a given environment.

| No.|  Specifications and Constraints                                                                                             | 
| ---|---                                                                                                                          |        
| 1  |Shall consider the constraint of limited sky visibility in the robot's environment, which may impede GPS signal acquisition  | 
| 2  |Shall acknowledge that the accuracy of GPS signals depends on the number of satellites in view.                              |
| 3  |Shall account for environmental constraints, including signal blockage or degradation                                        | 

# Analysis 
## Analysis (1): 
In situations where there are obstacles obstructing the line of sight between the GPS module and the satellites, the limited sky visibility can result in weaker GPS signals and a decrease in signal-to-noise ratio (SNR). To assess the effect of limited sky visibility on GPS signal quality, one can utilize the Log-normal Shadowing Model. This model considers the distance between the GPS module and the obstacles, allowing for the quantification of signal attenuation caused by the obstacles.
<br>
<br>
The Log-normal Shadowing Model: P_r = P_t - PL – X
<br>
P_r is a received signal power, which represents the strength of the signal received by the M10Q-5883 module. The GPS receiver receives GPS signals at 1575.42 MHz (L1 frequency) at a power level of -125 dBm (about 0.1 fWatt).
<br>
P_t is transmitted signal power, which represents the power of the signal transmitted by the satellites. 
<br>
For GPS, total L-band transmit power levels of 50-240 W were obtained, 
<br>
20-135 W for GLONASS
<br>
95-265 W for Galileo,
<br>
130-185 W for BeiDou-2. 
<br>
The path loss (PL) can be calculated using the Friis transmission equation:
PL = 20log10(d) + 20log10(f) - 147.55
<br>
Where the d is the distance between the GPS module and the satellite
<br>
Distance between the receiver and the satellites = propagation time x radio wave speed

Convert the received signal power from dBm to Watts: Ptx = 10^((-125 - 30) / 10) = 0.1 fWatt 
Assume typical values for the antenna gains, considering an omnidirectional antenna: Gtx = Grx = 0 dBi
Calculate the wavelength (λ) using the frequency of the GPS signal: λ = c / f = 299,792,458 m/s / (1575.42 MHz) = 0.190293 m
Substitute the values into the Friis transmission equation to find the distance (d):
d = λ / (4π) * 10^((Ptx - Prx + Gtx + Grx) / 20)
   = 0.190293 m / (4π) * 10^((0.1 - (-125) + 0 + 0) / 20)
   = 0.190293 m / (4π) * 10^((125.1) / 20)
   = 0.190293 m / (4π) * 10^(6.255)
   ≈ 0.190293 m / (4π) * 1,983,400.66
<br>
The approximate distance between the transmitter (satellite) and the receiver (module) is approximately:
d ≈ 0.190293 m / (4π) * 1,983,400.66
<br>

"A receiver uses signals from satellites to figure out how long it takes for radio waves to travel from the satellites to the receiver's antenna. The signals sent by the satellites include time information, so the difference between that time and the receiving time is called the propagation time. By multiplying this propagation time by the speed of radio waves (which is the same as the speed of light, approximately 299,792,458 meters per second), we can calculate the distance between the satellites and the receiver."

<br>

f is the frequency of the GPS signal.
<br>
the frequency of the transmitted signal is f = c/λ 
<br>
the frequency of the GPS signal is the GPS signal operates at a frequency of 1575.42 MHz (L1 frequency). The wavelength of the GPS signal is λ = c / f, where c is the speed of light and f is the frequency of the signal. For the GPS signal, the wavelength is approximately λ = 299,792,458 m/s / 1575.42 MHz
<br>

PL = 20log10(d) + 20log10(f) - 147.55
d ≈ 0.190293 m / (4π) * 1,983,400.66
f = 1575.42 MHz
<br>

PL = 20log10(0.190293 m / (4π) * 1,983,400.66) + 20log10(1575.42 MHz) - 147.55
<br>

Calculatiion:
<br>

20log10(0.190293 m / (4π) * 1,983,400.66)
   ≈ 20log10(0.190293 m / (4π) * 1,983,400.66)
   ≈ 20log10(0.190293 m / 7.85398) * 1,983,400.66)
   ≈ 20log10(0.0242102 m * 1,983,400.66)
   ≈ 20log10(48,152.98 m)
   ≈ 20 * log10(48,152.98)
   ≈ 20 * 4.682
   ≈ 93.648
<br>

20log10(1575.42 MHz)
   ≈ 20log10(1575.42 MHz)
   ≈ 20 * log10(1575.42)
   ≈ 20 * 3.197
   ≈ 63.94
<br>


PL ≈ 93.648 + 63.94 - 147.55
   ≈ 210.588 - 147.55
   ≈ 63.038

<br>

The path loss value of 63.038 indicates that the signal strength decreases as the distance between the transmitter (satellite) and receiver (module) increases. Higher path loss values indicate weaker signal strength. 

<br>

the signal-to-noise ratio (SNR):
<br>

The received signal power is given as -125 dBm, including additional losses.
<br>
The noise power in the system bandwidth (2.046 MHz) is given as -110 dBm.
<br>
The modulation scheme is direct spread-spectrum, which provides a processing gain of 43 dB.
<br>
the received power required is -135 dBm.
<br>
the received power required is -147 dBm.
<br>
SNR = Pr / N0 (Pr is the received signal power and N0 is the noise power).
<br>
SNR at Received Signal Power: SNR = -125 dBm / -110 dBm = 15 dB
<br>
SNR during Acquisition: SNR = -135 dBm / -110 dBm = 25 dB
<br>
SNR during Tracking: SNR = -147 dBm / -110 dBm = 37 dB

<br>
Higher SNR values indicate a better quality of service and higher resistance to noise and interference.
<br>

## Analysis (2): 


## Analysis (3): 


# Buildable Schematics
## CAD models
## Electrical Schematics

# BOM
| Name of Items |  Description        | Used in which subsystem(s) | Part Number     | Manufacturer   | Quantity | Price     | Total |
| ---           |     ---             |          ---               |      ---        |     ---        |    ---   |  ---      |  ---  |
| GPS           |GPS & Compass Module |  GPS subsystem             | M10Q-5883 GNSS  | rotorriot      |    1     |39.99$     |39.99$ |
| Arduino Nano  |ATmega328            |  GPS subsystem             | A000005         | Arduino        |    1     |24.90$     |24.90$ |
|               |                     |                            |                 |Total Components|    2     |Total Cost |64.89$ |

# References

https://www.techtarget.com/searchnetworking/definition/signal-to-noise-ratio

https://global.jaxa.jp/countdown/f18/overview/gps_e.html

https://link.springer.com/chapter/10.1007/978-3-642-72011-6_3

https://www.quora.com/How-is-the-distance-between-a-GPS-device-and-a-GPS-satellite-calculated

https://www.nxp.com/docs/en/brochure/75016740.pdf
