# Predicting recrystallization in laser powder techniques

## Abstract
Laser Powder Bed Fusion (LPBF) of metallic powders is a new technique to shape metal in 3D shapes with immense freedom and flexibility compared to current industry techniques. Unfortunately, it is very hard to have consistent repeatability from the experiments because of a lack of proper quality monitoring. In our case, we focus on detection of one specific phenomenon of the matter called recrystallization. crystallisation is the process of atoms or molecules arranging into a well-defined, rigid crystal lattice in order to minimize their energetic state, it's a state has very interesting mechanical properties. Current methods used to detect if recrystallization has occured are very complicated and time intensive. Instead we provide code that, using a microphone setup during noisy laser bed experiments, attempts to extract features from the sound waves and analyses them with machine learning models to detect if recrystallization occured.

## Datasets and setting up locally to be able to run
We use soundwaves from different microphones in multiple experiments where we know for sure recrystallization happened or not. These files are very heavy, and altogether weight more than sixty gigabytes of memory. So they are stored in a google drive and must be downloaded locally while respecting this specific folder organization :


## Nomenclature explanation of the CSV files
CSV files with deformed in the name : during the laser heat treatment, recrystallization takes place
CSV files with RX in the name (previously recrystallized): during the laser heat treatment, no recrystallization happens because the sample is already recrystallized



## Code organization
There are three separate code files contained in the repository :
project : This codefile contains some of our exploratory data analysis templates, as well as the transfer learning based yamnet implementation.
SVM : This codefile contains the code for our support vector machine model.
The last code file is the code for our regular neural net implementation to solve the problem.

## results

