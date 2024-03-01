---
title: Simple Example
layout: default
nav_order: 3
---


# Presentation of the simple example

<img src=".../Images/Captures d’écran/sn_simple.png" alt="logoUZ" width="200"/>

# Process

### Step 1 : Download the simulation software Renew

Please refer to the [Renew Installation window](../renew.html).

### Step 2 : Download the simple example files

[Please click here to access the files on Github](https://github.com/eva-robillard/NwN_simple).

### Step 3 : Open the example on Renew

The procedure for the launching on the example in Renew is:

1. Open the Powershell in the directory with the example files, containing the Java script Eval.java.
2. Execute "javac Eval.java" in the Powershell
3. Open Renew from the Powershell ( type in the path of the directory containing the Renew software adding \renew ) 
4. In Renew, open "system_net_2r.rnw"

### Step 4 : Simulate

Simulate Step by Step (Ctrl+I) or completely (Ctrl+R)


# Information on the files

**Color code** :
* Blue: System Net
* Green: Elements used to launch a simulation
* Red: Elements used to end a simulation
* Magenta: Processing of the information, display of the best solution




**Simulation information** : 
* At all times, you can observe the state of the robots nets by right-clicking the number contained by the Master Net place and double-clicking on one robot. 
* You can simulate by choosing the fired place. After having fired "init", you can double click on a transition si and choose what transition to fire. 
* This simulation is done for an LTL formula which implies the visit of three regions of interest ("a", "b", "c"), but requiring the visit of region "c" before visintg "a". The team of 3 robots evolves in an environment with 3 regions of interest from which two of them overlap.


**Addional remarks**:
* The system will be executed as many times as the initial marking of place "numSim".
* All the traces will be accumulated to the file named "log.txt".
* Besides storing in "log.txt" the solutions found, the "best" one will be in place named "bestSol". Being initially "", each time a new solution is obtained, it is compared with the current best, by means of the function "select_best" in the class "Eval". In its current version, "best" means "shorter" in terms of number of chars, but this is so just to check the feasability. The function could/should be much more sophisticated
* This example contains two different types of robots: two as the initial example, and a second one which is not allowed to visit the intersection area
* It has also been added a way of giving names to robots for an easier understanding of the solutions

 

