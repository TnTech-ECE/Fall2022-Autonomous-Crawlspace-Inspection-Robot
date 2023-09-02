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


# Buildable Schematics
## CAD models
## Electrical Schematics

# Analysis 

# BOM
| Name of Items |  Description        | Used in which subsystem(s) | Part Number     | Manufacturer   | Quantity | Price     | Total |
| ---           |     ---             |          ---               |      ---        |     ---        |    ---   |  ---      |  ---  |
| GPS           |GPS & Compass Module |  GPS subsystem             | M10Q-5883 GNSS  | rotorriot      |    1     |39.99$     |39.99$ |
| Arduino Nano  |ATmega328            |  GPS subsystem             | A000005         | Arduino        |    1     |24.90$     |24.90$ |
|               |                     |                            |                 |Total Components|    2     |Total Cost |64.89$ |

# References
