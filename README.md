EDL 2025 Project Submission Repository.
Change this file to include the relevant information of your project. Refer to SUBMISSION_INSTRUCTIONS.md file and follow it for your final submission. Make sure to pass the GitHub Actions. (The Docs Added should turn green and it should say "passing")

Project Name: [P-03: Corrosion detector for insulated pipelines based on PCB planar coils and high resolution inductance measurement]
Team Number: [MON-18]
Team Members:
[Sanjay Meena (22B3978)]
[Devtanu Barman (22B3904)]
[Sania Mandal (22B1223)]
[Akash Jaiswal (22B3938)]
[Manoj Kumar Murmu (22B3989)]
Problem Statement:
"Corrosion detector for insulated pipelines based on PCB planar coils and high-resolution inductance measurement."

Solution
We developed a handheld corrosion detection device named CorroSense, designed specifically to detect pitting corrosion under insulation on metallic pipelines. The device leverages non-contact inductive sensing to detect subtle material loss beneath insulation layers without requiring any dismantling or physical intrusion.

At the core of CorroSense is an in-built planar PCB coil (part of high-resolution inductance measurement IC LDC1612), which serves as the sensing element. This coil is interfaced with the LDC1612, capable of detecting minute variations in inductance caused by corrosion-induced changes in the conductive material below.

To map these variations across the pipeline surface, we integrated a surface tracking mechanism using an optical encoder module (ZEB-OM115) extracted from a standard optical mouse. This encoder tracks the relative movement of the device across the surface, enabling 2D spatial localization of inductance data points.

A Raspberry Pi Pico acts as the main microcontroller for sensor data acquisition and communication.

CorroSense includes an audible beep alert when high corrosion is detected. This immediate feedback helps operators quickly identify critical corrosion areas. It enhances real-time monitoring and ensures that users are promptly aware of high corrosion levels.

The collected data is stored and processed on PC using Python scripts. We generated heatmaps to visualize corrosion-prone areas in a clear, intuitive manner via VSCode.

This system offers a low-cost, non-destructive and portable solution for industrial corrosion monitoring applications, significantly improving ease of inspection and reducing maintenance costs.

What We Learned and Achieved:
Inductive Sensing: Successfully utilized the in-built planar coil PCB in the LDC1612 chip for inductive sensing, enabling precise detection of corrosion beneath insulation layers without physical intrusion.

Sensor Integration: Integrated the LDC1612 sensor with the Raspberry Pi Pico using I2C communication, allowing real-time data collection and processing.

Position Mapping: Repurposed the optical encoder module (ZEB-OM115) from a standard optical mouse to track the device's movement across the pipeline surface, enabling accurate correlation between sensor readings and physical locations.

Embedded Systems and PCB Design: Gained hands-on experience in embedded systems programming, PCB design, and sensor fusion, merging multiple technologies into a functional, portable device.

Data Visualization: Learned how to process and visualize sensor data using Python, matplotlib, and NumPy to generate heatmaps and 3D surface plots, making corrosion detection clearer and more intuitive.

Real-Time Alerts: Implemented an audio alert system using the winsound library to notify users of critical corrosion levels, improving the system's responsiveness.

System Optimization: Fine-tuned the system to ensure real-time data collection, accurate corrosion level detection, and smooth user interaction, creating a fully integrated handheld device for industrial use.

Microcontroller Used:
Microcontroller: [Raspberry Pi Pico (RP2040)]

IDE Used: [Arduino IDE]

Upload Method: [USB]

Experiences
Positive Aspects
Technical Skills:
Developed a solid understanding of inductive sensing principles and implemented them in a real-world application.
Gained experience in PCB design and integration with microcontrollers for practical device development.
Successfully integrated multiple subsystems (sensing, data processing, movement tracking, and alerting) into a cohesive solution.
Teamwork:
Divided tasks efficiently among members, with each team member contributing to specific areas like hardware design, programming, or data visualization.
Regular collaboration and code reviews ensured a smooth workflow and minimal redundancy.
Cost-Effective Design:
Successfully repurposed existing components, such as the optical encoder from a standard optical mouse, to keep the overall project budget within limits.
End-User Focus:
Designed a user-friendly system with intuitive features like a beep alert and visualized corrosion data. This focus helped bridge the gap between technical innovation and practical usability.
Challenges and Hardships
Sensor Calibration:
Achieving consistent inductance readings required precise calibration, especially since variations in environmental factors (e.g., temperature, pipeline material) affected accuracy.
Recalibration consumed significant development time, as the sensor needed adjustments based on field trials.
Data Transmission Delays:
Initial data transfer from the Raspberry Pi Pico to the PC was slow due to communication bottlenecks. We mitigated this by optimizing the I2C protocol and adjusting baud rates.
Integration Difficulties:
Merging the LDC1612 sensor data with positional tracking (optical encoder readings) was challenging. Synchronizing the two data streams required significant debugging and refinement.
Learning Curve:
For some team members, learning advanced PCB design and embedded programming concepts presented a steep learning curve. However, this was overcome through peer learning and external resources.
Hardware Constraints:
Limited access to high-quality fabrication tools for the PCB meant that the prototype's durability was lower than desired. Temporary fixes were needed during testing.
Time Management:
Balancing the 12-week course with academic responsibilities posed scheduling challenges. Despite this, we delivered a functional prototype.
Unfinished Components and Future Work
Unfinished Components
Battery Integration:
The current design relies on a USB-powered connection. Integrating a rechargeable battery would enhance portability.
Reason: Limited time prevented us from optimizing power management circuits.
Advanced Data Processing:
While we achieved basic heatmap generation, advanced analytics like trend prediction and multi-layer corrosion mapping remain unexplored.
Future Work
Battery Integration and Power Optimization:
Adding a rechargeable battery and optimizing power consumption to extend operational time.
Implementation: Design and integrate a battery management system (BMS) with overcharge protection and low-power microcontroller modes.
Enhanced Data Analysis:
Implementing predictive analytics to assess the likelihood of future corrosion based on current trends.
Implementation: Use machine learning models trained on collected inductance data to predict corrosion hotspots.
Wireless Connectivity:
Enabling real-time data transfer via Wi-Fi or Bluetooth for improved usability.
Implementation: Integrate a wireless module (e.g., ESP32) and establish communication with a mobile app or cloud platform.
Field Trials and Feedback:
Conducting extensive field trials in industrial settings to refine the system based on user feedback.
Implementation: Collaborate with industry professionals to identify pain points and usability concerns.
Scalability:
Enhancing the system to support multi-device usage for larger pipelines.
Implementation: Develop a synchronization mechanism where multiple CorroSense units can communicate and coordinate their scans.
By addressing these aspects, the CorroSense project can transition from a prototype to a fully deployable industrial solution.

Repository Walkthrough:
Below is an organized walkthrough of the repository structure:

3d_models/
Purpose: Contains 3D models of the device components.
Contents:
STL or CAD files for the physical casing and other components.
others/
Purpose: Stores miscellaneous resources and outputs.
Subdirectories:
Comsol Simulations/: Contains COMSOL simulation files for electromagnetic behavior analysis.

FINAL_OUTPUT_HEATMAPS/: Final heatmaps generated from corrosion detection tests.

User Manual/: User guide for operating the CorroSense device.

pcb/
Purpose: Contains PCB schematics and manufacturing files.
Contents:
Schematics, layout designs, and Gerber files.
reports/
Purpose: Stores detailed reports and documentation.
Contents:
Progress reports, final project report, challenges, and future scope.
src/
Purpose: Contains all source code files for the project.
Subdirectories:
computer/:

Python scripts for data processing, communication, and heatmap generation.
rpi_pico/:

Embedded systems code for the Raspberry Pi Pico.
📁 bom.xls/
Purpose: Contains the Bill of Materials (BOM) for the project.
Contents:
A detailed list of all the components used in the project, including part numbers, quantities, and suppliers.
