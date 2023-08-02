# Interactive Blocksworld Application Manual

This manual describes all steps necessary to obtain the source code the Interactive Blocksworld application. Additionally it is shown how the application can be used in the Unreal Engine editor.
Furthermore, configuration settings in the game are elaborated.


The source code for the application can be downloaded externally since some files are too large for GitHub.
The source code consists of a config, content and source file. The config file contains all configurations and settings of the application.
The content file contains Blueprints, meshes, textures and other Unreal Engine files. The source file contains all C++ classes.

The source code can be downloaded here:


The code was generated with the engine version 5.1.1. To use the application in the Unreal editor, a new project must be created with the engine.
From there config, content and source files can be copied and pasted in the newly created project. In some cases, for the editor to work the UProject file containing the project ID is necessary. This file is also contained in the source code.

The application can be extended by adding user interface functionality. This is mostly done in Blueprints in the content folder. Otheer implementations are written in C++ in the content folder.
The application can be packaged in the editor.

The application uses a third-party library: the graph visualization tool graphviz. This tool has to be linked. The graphviz library can be obtained by the following command on Ubuntu/Debian distributions:

sudo apt install graphviz

For other distributions the command may be a bit different. The location where the graphviz library must be, is specified in the Block.build.cs file in the source folder. This location can also be changed or made customizable.

To use the Fast Downward planner in the application, the configuration file must be customized in the application. The configuration file consists of a path to the Python interpreter and a path to the fastdownward.py file. Fast Downward can be downloaded on the dedicated GitHub page (https://github.com/aibasel/downward). If these configurations are not specified, the planner cannot be run.

The application provides a system where states can be saved. The purpose is that states with different difficulties can be generated and used for different target groups. Either these states are generated in the application by applying actions. Instead, the SavedStates file can be altered to generate new initial states. The format of this file is defined as follows:

NAME_OF_THE_STATE: CONTAINERID_LANDSTACK1 CONTAINERID_LANDSTACK1;CONTAINERID_SHIPSTACK1 CONTAINERID_SHIPSTACK1,CONTAINERID_SHIPSTACK2 CONTAINERID_SHIPSTACK2,CONTAINERID_SHIPSTACK3 CONTAINERID_SHIPSTACK3;CONTAINERID_ATTACHEDCONTAINER

An example instance of a saved state would be:

SavedState: 3;0 1 2,4 5,7 8;6