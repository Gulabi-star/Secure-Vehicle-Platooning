# SecureVehiclePlatooning_Demo
<b> 1. Three-vehicle platoon with unencrypted CAM transmission <br> (Highway scenario) </b> <br>
The video shows a simple highway scenario where a three vehicles travel togther as a platoon, using DSRC for commnication and a CACC controller to maintain safe spacing and coordination. To simulate this, we use OMNeT++, and SUMO. OMNeT++ manages the wireless network and supports DSRC communication protocol, while SUMO simulates and visuializes the traffic flow on the road. To enable cooperative driving features like platooning using DSRC, we use the Veins and Plexe extentions to OMNeT++. The DSRC-equipped vehicles continuously send and receive  Cooperative Awareness Messages (CAMs). These messages share real-time critical vehicle data such as position, speed, and acceleration, helping maintain safe inter-vehicle distances and smooth coordination. 
https://github.com/user-attachments/assets/10c6bece-209f-4906-8c0b-e1b175ed74bb

<b> 2. Three-vehicle platoon with encrypted CAM transmission <br> (Highway scenario)</b>

https://github.com/user-attachments/assets/9288b730-9ce8-48f9-bddc-495ab1bd004f

<b> 3. Ten-vehicle platoon with encrypted CAM transmission <br> (Map scenario)</b>

https://github.com/user-attachments/assets/7eaee705-da46-4e02-8f57-bf7fda95a73c



