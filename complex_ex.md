---
title: Complex Example
layout: default
nav_order: 4
---


# Presentation of the complex example




# Presentation of the files

## The System Net : for example system_net_4r for 4 heterogeneous robots

<img src="../pictures/sn_4.png" alt="SN" width="700"/>

This is the main pilot file that links all parts of the model together. In order to understand the different elements of this file, there is a **Color code** :
* Blue: System Net
* Green: Elements used to launch a simulation
* Red: Elements used to end a simulation
* Magenta: Processing of the information, display of the best solution

## The Specification Net (SpecOPN) : complexmission

The LTL mission is complex, and reflects a futuristic realistic scenario where a team of heterogeneous robots assist in hospital procedures.

```math
Mission: \diamondsuit (b_1 \wedge b_2) \wedge \diamondsuit (b_3 \wedge b_6)  \wedge \diamondsuit (b_4 \wedge b_5) \wedge \neg (b_1 \vee b_3 \vee b_4) \mathcal{U} (b_7 \vee b_{11}) \wedge \diamondsuit (b_8 \vee b_9 \vee b_{10} \vee b_{12})
```

The representation of the complex mission as a Petri net is heavy, it is presented in compact form and is thus not the most lisible. The representation under Petri net formalism was done automatically as described in Renew page.

<img src="../pictures/complexmission.png" alt="mission" width="400"/>

## The Robot Petri Nets 

In this simulation, we use multiple types of RobotPN. Respectively, we present robot_assistant, robot_full, robot_monitoring, robot_patient and robot_supply_and_clean as presented in the paper. The representation of the nets was made with random layouts : the representation that opens on your computer may differ. 

<img src="../pictures/robot_assistant.png" alt="qpn" width="300"/> 

<img src="../pictures/robot_full.png" alt="qpn2" width="500"/>

<img src="../pictures/robot_monitoring.png" alt="qpn2" width="300"/> 

<img src="../pictures/robot_patient.png" alt="qpn2" width="500"/>

<img src="../pictures/robot_supply_clean.png" alt="qpn2" width="500"/>



# Information on the file

 * **System nets**: the file names contain the number of robots in the team. If the name contains "samerob" - the team is homogeneous, otherwise the team is heterogeneous;
 * **Mission net**: SimpleMission.rnw refers to the mission exemplified throughout the paper, and ComplexMission.rnw refers to the scenario with the hospital. In addition,  MissionE.rnw and MissionF.rnw contain missions with multiple final states. Their LTL Formulas are :
```math
MissionE: \diamondsuit \square b_1 \wedge b_2 \vee \diamondsuit \square b_3 \wedge b_6 \vee  \diamondsuit \square b_4 \wedge b_5 \vee \wedge \diamondsuit ((b_1 \vee b_3 \vee b_4) \wedge \bigcirc \diamondsuit b_9) \vee (\diamondsuit \square ((b_{11} \vee b_7) \wedge \diamondsuit \bigcirc (b_{10} \vee b_{12})))
```
```math
MissionF \diamondsuit \square b_1 \wedge b_2 \vee \diamondsuit \square b_3 \wedge b_6 \vee  \diamondsuit \square b_4 \wedge b_5 \vee \wedge \diamondsuit ((b_1 \vee b_3 \vee b_4) \wedge \bigcirc \diamondsuit b_9) \vee  (\diamondsuit \square ((b_{11} \vee b_7)
```
 * **Robot nets**:  qpn_robot and qpn_robot_2 are used for the SimpleMission. The rest of the robot nets (robot_assistant, robot_full, robot_monitoring, robot_supply_and_clean, robot_patient) are used for the ComplexMission.
   
 > [!NOTE]
 > One experiment include multiple simulations, as follows: 1000 simulations for the first three cases (2-5 robots), 250 simulations for 6 robots, 85 simulation for 7 robots and 300 simulations for 8 robots. 
