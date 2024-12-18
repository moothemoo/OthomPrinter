# OthomPrinter
OthomPrinter is my personal project which was designed from scratch over the course of 2021-2022. Through this project, I gained familiarity with the engineering design process. The requirements and design were by
far the longest parts of this project; by nature of being a personal project and exploring unknown territory, the requirements and design were closely linked, with things changing drastically enough that the 
printer had been redesigned from the ground up through a total of three iterations. The learning process involved understanding the properties of many thermoplastics, the limitations of various linear guide 
systems, the limitations of different kinematic systems, fluid dynamics for the part cooling ducts, a little bit of electronics, and vibration management, to name just a few. This journey became my  my core
reason to pursure robotics and automation.

![Assembly Screenshot](Images/AssemblyScreenshot.png)


# Model Viewing
To view the CAD model, please copy and paste the link below into a new tab. If you do not do this, you may get a 403 Error.
https://cad.onshape.com/documents/486057f9bfa2f3c877bee928/w/97106b5181098ec6194ae382/e/accf4027831999f4600c351c

# Mechanical Details
OthomPrinter is a CoreXY kinematics printer with a 350mm x 350mm x 350mm build volume. It features kinematic bed mounting, a lightweight toolhead, a counterspring bed setup, and 3030 extrusion construction. The 
toolhead uses a LGX Lite extruder and a groove mount hotend, which, in this case, is a E3D V6. A dual fan system is used to provide part cooling. An Omron inductive proximity sensor is used to provide relatively 
accurate bed detection.

# Software Details
The printer uses an open source firmware, klipper, which simplifies the configuration process of the printer board, and provides a number of useful motion control utilities, allowing compensation for vibration and
filament pressure lag, among other things. The control board is an Octopus pro, an STM32 based control board, with a split control system with a raspberry pi, which hosts a web server through MainsailOS, a debian
based operating system which cuts all frills in order to give gcode streaming top computation priority, which reduces possible stutters

# Electronics Details
The electronics are quite simple as an advantage of using prepackaged control boards. The control board is able to handle both logic and motor power, but is not able to handle a sufficient amount of power for bed 
heating. A 750 Watt, 120 VAC bed heater is used for heating, which is throttled by a PWM controlled solid state relay. A 350 Watt switching power supply is used to provide 24 VDC to the control board, which has
onboard converters for 5V, which then powers the raspberry pi.

# Additional Details
This printer was designed in Onshape, due to its simple, but effective toolset, while being highly accessible. The low-security nature of cloud-based CAD was not an issue for a personal project, and the advanced 
features (mainly simulation and generative design) which are available in more powerful CAD softwares were not required.
