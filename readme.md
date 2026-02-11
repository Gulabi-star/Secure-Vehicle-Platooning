# SecureVehiclePlatooning_Demo

## Group A: Security under Attack Scenarios

### 1. Baseline Platoon Operation without Attack and without Security

We use **OMNeT++** and **SUMO** to simulate vehicle platooning. **OMNeT++** manages the wireless communication using the **Dedicated Short Range Communication (DSRC)** protocol, while **SUMO** simulates and visualizes traffic flow on the road. To enable cooperative driving, we extend **OMNeT++** with **Veins** and **PLEXE**.

The video shows a **highway scenario extracted from OpenStreetMap**, representing a real-world highway segment in **Germany**, where **ten red vehicles form a platoon**. The platoon uses **DSRC** for communication and a **Cooperative Adaptive Cruise Control (CACC)** to maintain safe spacing. During the trip, the platoon performs **coordinated braking at 4 mpss**, with all vehicles decelerating together while maintaining a safe distance. The vehicles continuously exchange **Cooperative Awareness Messages (CAMs)** containing real-time data such as position, speed, and acceleration, ensuring smooth and safe braking.

https://github.com/user-attachments/assets/973168c6-86bc-40e6-a929-2d10d9952649

### 2. Impact of Replay-Spoofing Attack on Unencrypted CAM Transmission in a Ten-Vehicle Platoon

In this scenario, the **purple vehicles represent external traffic**, and one of them acts as an **attacker vehicle** that launches a replay-spoofing attack on the platoon. The attacker impersonates the immediate predecessor of PM3 and injects outdated CAM messages into the communication channel. Since CAMs are transmitted **without encryption or authentication**, the forged packets are accepted by PM3, which corrupts its control inputs and disturbs the desired inter-vehicle spacing. As a result, platoon safety is compromised, leading to unsafe behavior and a collision between PM2 and PM3.

https://github.com/user-attachments/assets/e84a85e5-59d2-4efc-b66a-4be3a822e9a3

### 3. Mitigating Replay-Spoofing Attacks via Encrypted CAM Transmission in a Ten-Vehicle Platoon

This scenario is implemented using **SPlatoon**, a tool comprising a **precision-aware CAD framework** and a platoon simulation setup. The framework takes as input a traffic scenario, vehicle trajectories, and dynamics, and outputs the **maximum safe platoon size** along with the corresponding **security parameters** required to ensure both safety and security.

Under the same replay-spoofing attack as in Case 2, **ASCON-based encrypted and authenticated CAM transmission** is enabled. Forged packets fail authentication and are rejected by the receiver, preserving correct control inputs and maintaining safe inter-vehicle spacing. This validates the CAD framework’s outputs and shows that properly configured secure CAM transmission has minimal impact on coordination and safety.

https://github.com/user-attachments/assets/d2ef0ac6-dd7f-443a-af9a-582d4581ffa0

## Group B: Network Congestion Analysis 

### 4. Ten-Vehicle Platoon under High Network Congestion using RP Encrypted CAMs
A 100-vehicle highway scenario is simulated, where 10 vehicles form a platoon and the remaining 90 vehicles generate background traffic by broadcasting periodic 300-byte beacons. The platoon exchanges Reduced Precision (RP) ASCON-encrypted CAMs (234 bytes) while performing coordinated braking at 4 m/s².
Despite the congested network, all vehicles maintain stable coordination and safe inter-vehicle spacing during deceleration. The smaller encrypted packet size enables timely communication, preserving platoon safety under heavy channel load.

https://github.com/user-attachments/assets/c4000f00-9522-4b8f-85c0-fff648cd9803

### 5. Ten-Vehicle Platoon under High Network Congestion using FP Encrypted CAMs
Although authentication provides CAM security, the larger Full Precision (FP) encrypted CAM size (242 bytes) increases communication delay under congestion. During coordinated braking at 4 m/s², delayed CAM updates result in degraded spacing behavior and visible safety-bound violations.

This highlights the trade-off between numerical precision and communication latency under highly congested network conditions.

https://github.com/user-attachments/assets/cd4196e6-53a3-41c5-b60a-688e6858e53d

## Group C: Precision and CAD-Based Secure Platooning

### 6. Three-Vehicle Platoon with Unencrypted CAM Transmission (Straight Highway Scenario)

This scenario uses a **simplified straight highway model** to study platoon behavior under controlled conditions. A **three-vehicle platoon** operates using **unencrypted CAM transmission** and a **CACC controller** to maintain safe spacing.

The video shows coordinated braking, with all vehicles decelerating together while maintaining safe inter-vehicle distances through continuous exchange of CAMs containing position, speed, and acceleration. This case serves as a baseline for analyzing the impact of **reduced-precision encrypted CAM transmission** in Case 5.

https://github.com/user-attachments/assets/10c6bece-209f-4906-8c0b-e1b175ed74bb

### 7. Three-Vehicle Platoon using Reduced-Precision CAMs (Straight Highway Scenario)

This scenario considers the same straight highway setup as in Case 4, but with **ASCON-based encrypted CAM transmission** enabled. To control the size of encrypted packets and study its impact on platoon coordination, we apply **reduced-precision CAM** before encryption.

The video highlights the role of **precision-aware design** in preserving platoon safety under encrypted communication, even in a controlled highway setting.

https://github.com/user-attachments/assets/9288b730-9ce8-48f9-bddc-495ab1bd004f

### 8. Ten-vehicle platoon with encrypted CAM transmission (Map scenario)

Building on the previous scenario where precision loss led to a collision, we introduce SPlatoon, a tool comprising a precision-aware CAD framework and a platoon simulation setup. The tool takes as input a traffic scenario, vehicle trajectories, and dynamics. It outputs the maximum safe platoon size along with the corresponding security parameters required to ensure both safe and secure platooning. These parameters are evaluated using platoon simulations on highway roads imported from OpenStreetMap. The video shows a route from Munich to Frankfurt, Germany, with red blocks representing urban structures. Throughout the trip, including the decleration phases, the platoon maintained coordination, with no collisions and all safety metrics are met. This validates the CAD framework’s outputs, showing that the secure CAM transmission, when configured with appropriate secuirty paramerets has minimal impact on coordination and safety.

https://github.com/user-attachments/assets/7eaee705-da46-4e02-8f57-bf7fda95a73c







