# Description
This repository is aimed for comparing 2D positioning solutions between different GNSS/INS integration methods, including Fixed-gain Kalman Filter (KF), Adaptive Kalmam Filter (AKF), Factor Graph Optimization (FGO), and Adaptive Factor Graph Optimization (AFGO)


## STEP 1: Run "Make_Format.m" inside folder "DataPrepare"
Before running all the scripts, "EnvFolder" is the "FOLDER_STORING_ALL_THE_PREPARED_DATASETS" manually-prepared by users. It is designed to contain:
- An empty folder named "IntiResults"
- MAT_FILE_OF_EXTRACTED_GNSS_FEATURES.mat
- MAT_FILE_OF_CNN_PREDICTION_FOR_EACH_GNSS_EPOCH.mat
- TXT_FILE_OF_GROUND_TRUTH_INFORMATION.txt
- CSV_FILE_OF_INS_DATA.csv
- MAT_FILE_OF_GNSS_DATA.mat

After running the codes, the following files are expected to be generated in folder "EnvFolder/IntiResults" 
- PROCESSED_DATA_FOR_KALMAN_FILTER.mat
- PROCESSED_DATA_FOR_FACTOR_GRAPH_OPTIMIZATION.mat
- COMMOM_INFORMATION_FOR_BOTH_INTEGRATION_METHODS.mat

And the following files are expected to be generated in folder "DataPrepare" 
- MAT_FILE_STOREING_STRING_OF_PATH_OF_EnvFolder.mat

## STEP 2: Run "Main_GNSS_INS_Integration.m"
The variable "CurFolder" in the script exactly represents folder "EnvFolder/IntiResults"

Configure the variables "KF_ON" and "FGO_ON" in order to execute the four integration methods:
- KF_ON = [1 0], FGO_ON = [0 0]; run the script (KF)
- KF_ON = [0 1], FGO_ON = [0 0]; run the script (AKF)
- KF_ON = [0 0], FGO_ON = [1 0]; run the script (FGO)
- KF_ON = [0 0], FGO_ON = [0 1]; run the script (AFGO)

After running the script, the following files are expected to be generated in folder "EnvFolder/IntiResults" 
- POSITIONING_SOLUTIONS_OF_ALL_INTEGRATION_METHODS.mat

And the following matlab figures are expected to be generated after in folder "EnvFolder/IntiResults"
- After running KF
  - Traj_KF.fig (2D trajectory of Truth/GNSS/KF)
  - 2dE.fig (2D error of Truth/GNSS/KF throughout the time frame)
- After running AKF
  - Traj_AKF.fig (2D trajectory of Truth/GNSS/KF/AKF)
  - 2dE.fig (2D error of Truth/GNSS/KF/AKF throughout the time frame)
- After running FGO
  - Traj_FGO.fig (2D trajectory of Truth/GNSS/KF/AKF/FGO)
  - 2dE.fig (2D error of Truth/GNSS/KF/AKF/FGO throughout the time frame)
- After running AFGO
  - Traj_AFGO.fig (2D trajectory of Truth/GNSS/KF/AKF/FGO/AFGO)
  - 2dE.fig (2D error of Truth/GNSS/KF/AKF/FGO/AFGO throughout the time frame)



