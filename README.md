# Digitisation
Collection of scripts for digitising fNIRS configurations
Currently maintained by [jia.zhang.25@ucl.ac.uk](mailto:jia.zhang.25@ucl.ac.uk)

## Overview
The following steps for digitising a cap has been demonstrated in-person in CogNIRS meetings. More elaborate tutorials will be updated in due course.

> - Take 3D scan of a head wearing a cap and export as `.obg` file
> - Open `.obg` file in [Meshlab](https://www.meshlab.net/) 
> - Create `.csv` file into reference points and optode coordinates, see [folder organsation](#folder-organisation) for more detail.
> - Run `SCStoMNI.m` to convert spatial coordiantes into MNI coordinates
> - Run MNI space analysis of your own choice using the `POS.mat` files created

## SCS to MNI

This script (`SCStoMNI.m`) converts the spatial coordinates produced by Meshlab into MNI coordinates. Please make sure to add the `Toolboxes` folder to your path.

## Folder Organisation
The script requires 3 files. The 2 `.csv` files containing your reference points and a `channel_config.txt` file. The path to these files are specified in the code:

```matlab
F{1,1}= "Data\M1\capM_p01_MotCorr_coord.csv"; % optode coordiantes csv
F{1,2}= "Data\M1\capM_p01_MotCorr_orig.csv"; % reference points coordinates csv
F{1,3}= "Data\channel_config.txt"; % channel configuration
```
You do not need to follow the same folder organisation, but the output `POS.mat` file will be saved in the same folder as the `.csv` files.

However, it is ***essential*** that your `.csv` and `channel_config.txt` files follow the same template as the example files in `/Data`. For your information, the channel config file in this example is shown below:

![ChannelConfig](https://github.com/CogNIRS/Digitization/blob/main/ChannelMap.png)