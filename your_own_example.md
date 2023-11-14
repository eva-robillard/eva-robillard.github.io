---
title: Your Own Example
layout: default
nav_order: 5
---

# What are the steps for testing out your own example with our model ? 

## Create a Büchi Petri Net from your LTL global mission.

This can be done by abiding by the following steps:

1. Translate your LTL formula into a Büchi automaton using the SPOT software. 
2. Save the automaton, the file will have an .xml type extension.
3. Change the extension to .hoa (this can be done by opening the .xml file in the notepad and saving it under the .hoa extension)
4. Go into the folder that holds the folder hoa2pnml. Open the Powershell there.
5. Write this command line :
'''
java -jar hoa2pnml.jar NameOfTheHoaFile (without adding the extension .hoa)
'''
6. The .hoa file is now a .pnml model visible by Renew.

## Robot nets


      So, the command line to execute a .sns file with all the information in one file is the following: (you have to be in the path where you have the Renew project):

path of Renew project java -jar "path of the renew\loader.jar" startsimulation nameoffile.sns execute experiment
