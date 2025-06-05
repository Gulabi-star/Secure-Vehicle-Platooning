# SecureVehiclePlatooning_Demo
<b> 1. Three-vehicle platoon with unencrypted CAM transmission <br> (Highway scenario) </b> <br>
The video shows a simple highway scenario where a three vehicles travel together as a platoon, using DSRC for commnication and a CACC controller to maintain safe spacing and coordination. To simulate this, we use OMNeT++, and SUMO. OMNeT++ manages the wireless network and supports DSRC communication protocol, while SUMO simulates and visuializes the traffic flow on the road. To enable cooperative driving features like platooning using DSRC, we use the Veins and Plexe extentions to OMNeT++. In this scenario, the platoon performs coordinated braking, where all vehicles decelerate together to halt while maintaining safe distance. The DSRC-equipped vehicles continuously send and receive Cooperative Awareness Messages (CAMs), sharing real-time data like position, speed, and acceleration. This ensures the braking is smooth and safety is preserved throught. 

https://github.com/user-attachments/assets/10c6bece-209f-4906-8c0b-e1b175ed74bb

<b> 2. Three-vehicle platoon with encrypted CAM transmission <br> (Highway scenario)</b>  <br>
The video shows the same three-vehicle platoon, but with ASCON, a lightweight authenticated encryption scheme integrated into the OMNeT++ network stack to secure DSRC-based vehicular communication. To enable encryption, floating-point vehicle data are converted into integers, causing a loss of precision due to trunctation. This reduced accuracy propagates through the platoon and affects coordination among the vehicles. As seen in the video, vehicle 2 and 3 collide during the breaking, demostrating how encryption induced precision loss can compromise platoon safety.

https://github.com/user-attachments/assets/9288b730-9ce8-48f9-bddc-495ab1bd004f

<b> 3. Ten-vehicle platoon with encrypted CAM transmission <br> (Map scenario)</b> <br>

https://github.com/user-attachments/assets/7eaee705-da46-4e02-8f57-bf7fda95a73c



