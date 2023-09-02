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

Ensure that the GPS subsystem components, including the M10Q-5883 GNSS GPS & Compass module, can work with the robot's power system and meet the required voltage levels. The GPS subsystem should provide accurate and precise location data to support navigation and data collection. Consider constraints related to the specified accuracy and precision of the GPS module. Take into account operating temperature, humidity, and vibration limits to ensure the GPS subsystem functions reliably in different environmental conditions. Ensure the GPS subsystem can seamlessly integrate with the chosen ROS, considering constraints such as data exchange formats, communication protocols, and synchronization with other robot systems. Enable effective integration and fusion of location data from the GPS subsystem with inputs from other sensors like cameras or lidar systems. Address constraints related to data synchronization, accuracy alignment, and calibration for accurate and comprehensive environmental data collection.

## List of constraints:
- Signal Accuracy and Precision
- Environmental Compatibility
- integration with ROS
- Sensor Fusion and Data Integration
- accurate enough and getting the signal 

# Buildable Schematics
## CAD models
## Electrical Schematics

# Analysis

# Software Consideration - Possible/Probable Software Solutions

# BOM
| Name of Items |  Description    | Used in which subsystem(s) | Part Number | Manufacturer | Quantity | Price | Total |
| ---           |     ---         |          ---               |      ---    |     ---      |    ---   |  ---  |  ---  |
| GPS           | M10Q-5883 GNSS GPS & Compass             |                            |             |              |          |       |       |
|               |                 |                            |             |              |          |       |       |
|               |                 |                            |             |              |          |       |       |
