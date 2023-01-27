Subcellular element model of inner cell mass

Background
This code simulates the motion and deformation of cells with subcellular element (SCE) methods. The theoretical foundation and basic parameters of SCE modeling refers to reference (Sandersius and Newman 2008). The simulation of cell surface fluctuation and affinity refers to reference (Yanagida, Corujo-Simon et al. 2022). 

Configuration of code
The model was developed with C++ code. The code was compiled and built with Microsoft Visual Studio Community 2019 at Win 10 and Win 11 platform. An open-source library (Point Cloud Library, PCL 1.12.1, https://github.com/PointCloudLibrary/pcl/releases) and Open Multi-Processing (OpenMP, integrated in VS 2019) were used. They should be configured before compiling and building the code. The code does not require any other non-standard hardware.
Using the source code from GitHub repository. The folder SimulationCode_V1 includes the source code (.h and .cpp files) and input dataset (.csv files in folder "Exm"). We suggest installing Microsoft Visual Studio Community 2019 (https://visualstudio.microsoft.com/zh-hans/vs/older-downloads/). Other version of Visual studio or other Integrated Development Environment were not tested. 
The open-source library (Point Cloud Library, PCL 1.12.1, https://github.com/PointCloudLibrary/pcl/releases) need to be installed. 
Then create a new c++ project, put the source code files and dataset folder into the working path, configure the paths of PCL .h and .lib files, copy the .dll files into the working path too. Make sure OpenMP option is "ON". ISO c++ 14 is applied.
The time of code configuration depends on the time to install Microsoft Visual Studio Community 2019 and open-source library, which will cost about 45 minutes.

Running
1. In Main.cpp, Set "sPth" to the path of folder "Exm". .csv files in folder "Exm" will be read during running.
2. Choose the simulation mission from "ICM", "FLUCTUATE", or "Affinity". "ICM" is the simulation of cell sorting, "FLUCTUATE" and "Affinity" are used to calculate the cell surface properties.
3. Choose the boundary condition of Mission "ICM". 
    CEmbry::TE() = true or false means the simulation with or without trophectoderm.
    CEmbry::Osclt() = true or false means the simulation with or without blastocyst cavity oscillation.
4. The results will be exported to SCEProp.csv, SCEMotion.csv, CellProp.csv, CellMotion.csv, CellVelocity.csv and SortIndex.csv in folder "Exm".
5. With 12 cores of Inter i9-12900H cpu, simulation of 1 Oscillation cycle (1830s) will cost about 3600s real time. 
5. The results of 3D cell motion can be visualized with "CellViewer.html" developed with Javascript (details in the ReadMe.md in folder "ResultViewer").

Reference
1. Sandersius, S. A. and T. J. Newman (2008). "Modeling cell rheology with the subcellular element model." Physical biology 5(1): 015002.
2. Yanagida, A., E. Corujo-Simon, C. K. Revell, P. Sahu, G. G. Stirparo, I. M. Aspalter, A. K. Winkel, R. Peters, H. De Belly and D. A. Cassani (2022). "Cell surface fluctuations regulate early embryonic lineage sorting." Cell 185(5): 777-793. e720.
