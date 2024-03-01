---
title: Complex Example
layout: default
nav_order: 4
---


# Presentation of the complex example



# Process

### Step 1 : Download the simulation software Renew

Please refer to the [Renew Installation window](../renew.html).

### Step 2 : Download the complex example files

[Please click here to access the files on Github](https://github.com/eva-robillard/NWN_Complex).

### Step 3 : Open the example on Renew

The procedure for the launching on the example in Renew is:

1. Open the Powershell in the directory with the example files, containing the Java script Eval.java.
2. Execute "javac Eval.java" in the Powershell
3. Open Renew from the Powershell ( type in the path of the directory containing the Renew software adding \renew ) 
4. In Renew, open "execute_experiment.rnw"

### Step 4 : Simulate

Simulate Step by Step (Ctrl+I) or completely (Ctrl+R)

# Presentation of the files

## The System Net : for example system_net_4r for 4 heterogeneous robots

<img src="../pictures/sn_4.png" alt="SN" width="700"/>

This is the main pilot file that links all parts of the model together. In order to understand the different elements of this file, there is a **Color code** :
* Blue: System Net
* Green: Elements used to launch a simulation
* Red: Elements used to end a simulation
* Magenta: Processing of the information, display of the best solution

## The Specification Net (SpecOPN) : complexmission

The representation of the complex mission is heavy, it is presented in compact form and is thus not the most lisible. 

<img src="../pictures/complexmission.png" alt="mission" width="400"/>

## The Robot Petri Nets 

In this simulation, we use multiple types of RobotPN. Respectively, we present robot_assistant, robot_full, robot_monitoring, robot_patient and robot_supply_and_clean as presented in the paper. The representation of the nets was made with random layouts : the representation that opens on your computer may differ. 

<img src="../pictures/robot_assistant.png" alt="qpn" width="500"/> 

<img src="../pictures/robot_full.png" alt="qpn2" width="400"/>

<img src="../pictures/robot_monitoring.png" alt="qpn2" width="300"/> 

<img src="../pictures/robot_patient.png" alt="qpn2" width="400"/>

<img src="../pictures/robot_supply_clean.png" alt="qpn2" width="400"/>



# Information on the file

 * **System nets**: the file names contain the number of robots in the team. If the name contains "samerob" - the team is homogeneous, otherwise the team is heterogeneous;
 * **Mission net**: SimpleMission.rnw refers to the mission exemplified throughout the paper, and ComplexMission.rnw refers to the scenario with the hospital. In addition,  MissionE.rnw and MissionF.rnw contain missions with multiple final states. Their LTL Formulas are :
```
MissionE: (F G (a & b) | F G ( c & f) | F G (d & e)) & F ((a | c | d)& X F i) | (F G ((k | g) & F X (j | l))) ) 
```
```
MissionF (LTL formula: (F G (a & b) | F G ( c & f) | F G (d & e)) & F ((a | c | d)& X F i) | (F G(k | g))
```
 * **Robot nets**:  qpn_robot and qpn_robot_2 are used for the SimpleMission. The rest of the robot nets (robot_assistant, robot_full, robot_monitoring, robot_supply_and_clean, robot_patient) are used for the ComplexMission.
   
 > [!NOTE]
 > For teams of 2-5 robots, one experiment contains 100 simulations, for teams of 6-8 robots, an experiment contains 10 simulations, except the file names containing 1sim (1 simulation). 
