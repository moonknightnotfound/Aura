# Receiver2 Script (Using Symbol Synchroniser)

## Basic Flow

Signal from Osmocom -> Separates our desired signal -> Complex to Mag2 (outputs raw power) -> AGC (setting the high and low levels as the signal strength keeps on changing) -> Adding with a constant to bring the reference level around zero for the synchroniser -> Symbol sync (to follow the clock drifts) -> Threshold (to output either 1 or 0 as per the set parameters).

## Observations

1. The time sink from the synchroniser output somewhat looks like steady values.

Run the Python script given below with the input file connected to AGC to get parameters to tune the Add Const block and the threshold parameters.

Input of the Add Const block will be (-mean provided by the script).

Command to run the script: `python3 calibrate_agc.py name_of_your_file.bin`
