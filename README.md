# simpppaal-executables

This directory contains the SIMPPAAL executables intended for the reviewers of the submitted TOSEM manuscript to evaluate. 
In the following we present the contents of the directory and a short tutorial on how one can run the SIMPPAAL tool.

## Contents

In order to be able to run the SIMPPAAL tool, you must download the complete directory. The tool is given as an executable .jar file named **SIMPPAAL.jar** wich is located in this directory.

The external libraries that the tool relies on are located in the **SIMPPAAL_lib** directory, whereas the plug-ins that generate the block routines are given in the **plugins/blockRoutine/Generators** directory. Finally, the **templates/automata** directory containts the TA templates for the discrete- and continuous-time blocks.

The **BBW** directory contains the Brake-by-Wire model from Volvo which we provide for demonstration purposes.

## Running SIMPPAAL

Once you have downloaded the entire simppaal-executable directory, locate the **SIMPPAAL.jar** file and double click on it. Once started, you shall see the graphical user interface (GUI) of the tool. In order to generate network of timed automata model, you have to provide the root Simulink model of the system, the sorted order of blocks which represents the sequential order at which the blocks are executed and a .xml file in which the generated model is to be storred. 

For the provided demo, please do the following: for the "**Simulink Model Folder**" click the respective "Browse" button which will open a file picker. Go inside the BBW folder and locate the "**brake_acc_nodiv.mdl**" file which is the root Simulink model file for the BBW system. Next, for the sorted order locate the **sortedorder.txt** file located in the same folder (**BBW**). Finally, you are allowed to select arbitraty file in an arbitrary location for the resulting model (**Select Timed Automata File**"). If you want to generate a new file for the model, just navigate to the directory where you want the model to be created and in the Save As text field write the name of the file with .xml extension.

Once all the required files have been provided, you can press the **Start** button to start the model generation procedure. In the console you can follow the progress of the model generation in real-time.

## Model Analysis

The models used for analysis are located in the **uppaal analysis models** folder. We create a separate model for each property due to the difference in the monitor automata.

The base model was generated using the SIMPPPAAL tool, however, each of the models have been manually adjusted to incorporate the missing block routines and to create the monitor automata. 

In order to be able to analyze the models, you must download the UPPAAL tool. The tool is free for academic use and it can be downloaded from the following [link](http://www.it.uu.se/research/group/darts/uppaal/download.shtml){:target="_blank"}.
