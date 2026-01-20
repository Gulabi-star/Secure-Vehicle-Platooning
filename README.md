# SecureVehiclePlatooning_Demo
## 1. Baseline Platoon Operation without Attack and without Security
hello
https://github.com/user-attachments/assets/973168c6-86bc-40e6-a929-2d10d9952649

## 2. Impact of Replay-Spoofing Attack on Unencrypted CAM Transmission in a Ten-Vehicle Platoon
https://github.com/user-attachments/assets/e84a85e5-59d2-4efc-b66a-4be3a822e9a3

## 3. Mitigating Replay-Spoofing Attacks via Encrypted CAM Transmission in a Ten-Vehicle Platoon
https://github.com/user-attachments/assets/d2ef0ac6-dd7f-443a-af9a-582d4581ffa0

<b> 4. Three-vehicle platoon with unencrypted CAM transmission <br> (Highway scenario) </b> <br>
We use OMNeT++, and SUMO simulator to simulate vehicle platooning. OMNeT++ manages the wireless communication using Dedicated Short Range Communication (DSRC) protocol, while SUMO simulates and visualizes traffic flow on the road. To enable cooperative driving, we extend OMNeT++ with Veins and PLEXE. The video shows a highway scenario where three vehicles form a platoon, using DSRC for communication and a Cooperative Adaptive Cruise Control (CACC) to maintain safe spacing. The platoon performs coordinated braking, with all vehicles decelerating together while maintaining a safe distance. The vehicles continuously send and receive Cooperative Awareness Messages (CAMs) containing real-time data such as position, speed, and acceleration. This ensures smooth and safe braking. 

https://github.com/user-attachments/assets/10c6bece-209f-4906-8c0b-e1b175ed74bb

<b> 5. Three-vehicle platoon with encrypted CAM transmission <br> (Highway scenario)</b>  <br>
The video shows the same three-vehicle platoon but with ASCON, a lightweight authenticated encryption (AE) scheme integrated into the OMNeT++ network stack to secure DSRC-based vehicular communication. To enable encryption, floating-point vehicle data are converted into integers, causing a loss of precision due to truncation. This reduced accuracy propagates through the platoon and affects coordination among the vehicles. The video shows vehicles 2 and 3 collide during the breaking, demonstrating how precision loss can compromise platoon safety.

https://github.com/user-attachments/assets/9288b730-9ce8-48f9-bddc-495ab1bd004f

<b> 6. Ten-vehicle platoon with encrypted CAM transmission <br> (Map scenario)</b> <br>
Building on the previous scenario where precision loss led to a collision, we introduce SPlatoon, a tool comprising a precision-aware CAD framework and a platoon simulation setup. The tool takes as input a traffic scenario, vehicle trajectories, and dynamics. It outputs the maximum safe platoon size along with the corresponding security parameters required to ensure both safe and secure platooning. These parameters are evaluated using platoon simulations on highway roads imported from OpenStreetMap. The video shows a route from Munich to Frankfurt, Germany, with red blocks representing urban structures. Throughout the trip, including the decleration phases, the platoon maintained coordination, with no collisions and all safety metrics are met. This validates the CAD framework’s outputs, showing that the secure CAM transmission, when configured with appropriate secuirty paramerets has minimal impact on coordination and safety.

https://github.com/user-attachments/assets/7eaee705-da46-4e02-8f57-bf7fda95a73c






