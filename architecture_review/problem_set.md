### Please answer the following questions and push your answers to your team's remote repository

For true/false question, if the statement is false, provide a description of why it is false.

- What are some of the difference between the Intel Aero Drone (i.e. a research and development drone) vs other "commercial" or "toy" drones?
   - Contains a high-level processing architecture running Linux as well as the basic low-level flight controller board.
   - Contains a pair of cameras with Intel's RealSense and infrared grid illumination technology for creating 3D depth maps.

- What are some current applications of autonomous drones? Can you think of any future applications as technology improves (e.g. faster, smaller, more efficient computers)?
	
   - Aerial Vision, remote sensing, ability to fly into and operate inside environments dangerous or inhospitable for humans, aerial transport, swarm drones...

- Describe the difference between the Aero Compute Board and Aero Flight Controller. What purposes do each serve? What operating systems do each run? Do you know where both of these boards are located on the drone?
	
  - The Aero Compute Board is a smart high-level SOC running Linux with custom python software; this has reasonably large latency. 
  - The Aero FLight Controller is a realtime low-level controller running NuttX and PX4 firmware; this system only uses basic low-level commands and thus can control and stabilize the drone in realtime. Both boards are located in the upper center of the drone, inside the CPU enclosure marked Intel.

- Which communication architecture are we using to connect are computers to the drone: Peer2Peer or centralized? What about the remote control - drone communication?

  - We are using centralized communication architecture:Wi-Fi. For the remote control, we are using Peer2Peer:Radio P2P.

- True or False: For manual flight control, the remote control communicates with the drone over wifi.

  - False. The remote control uses Peer2Peer: Radio P2P - an RF connection.

- In order to know where the drone is in the world, it needs some form of positioning sensor/algorithms, otherwise it would be flying blind. What are the different types of positioning sensors available? Which do you think we are going to use during the class?

  - There is an IMU (Inertial Measurement Unit - containing an accelerometer and a magnetometer), a compass, a GPS and a pair of cameras - infrared and visible for 3D depth maps. 

- True or False: during our indoor flights, we can use the GPS sensor to estimate the drone's position in the world.

  - False, as walls, ceilings and other objects can cause attenuation and scattering of the signal. 

- Are optical flow algorithms responsible for mapping the environment? If not, can you describe conceptually what optical flow does?

  - Yes. Optical flow is the apparent movement of pixel sets (objects) between consecutive frames. The drone camera will recognize objects and measure their respective flow and can use this to hover over those objects or simply stabilize themselves in flight.

- Which sensor on the Intel Aero Drone enables 3D visual mapping? 

  - The pair of infrared cameras enable 3D visual mapping up to 4-5m.

- How does the Aero Compute Board communicate with the Aero Flight Controller? 

  - The Aero Compute Board communicates with the Aero FLight Controller through a serial port using the MAVLink protocol.

- What is PX4 and where is it running on the drone? 

  - PX4 is the firmware running on the Aero Flight Controller enabling realtime low-level commands on the drone.

- Which of these best describes MAVLink: 1. an operating system used on the drone, 2. a sensor on the drone, 3. a communication protocol on the drone, 4. a programming language


  - (3) MAVLink is the communication protocol used to communicate between the Aero Compute Board and the Aero Flight Controller.

- If I want to write a new, complex computer vision algorithm for the drone, should I add it to the Aero Flight Controller firmware? if not, where should I add it and why?

  - No, since the Aero Flight Controller can only execute basic low-level commands in realtime; it is incapable of running such computationally intesive tasks. In addition, the cameras are not connected to the Aero Flight Controller. The algorithm should be added to the Aero Compute Board. The Aero Compute Board is directly connected to the cameras, has the processing power and connects to the Aero Flight Controller through MAVLink. 
