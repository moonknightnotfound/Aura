# Receiver GNU Script

## Basic Flow

Signal from Osmocom -> FIR filters (separates our desired signal from the spectrum) -> Complex to Mag2 (outputs the power of the signal) -> Math chain (converting to dBFS unit) -> Subtracted output is SNR -> AGC (setting the high and low levels as the signal strength keeps on changing) -> Through threshold converting it to bits and storing in file.

## Observations

1. The SNR increases when the signal is on or off, and also the raw powers.
2. The time sink from the AGC block looks like a non-periodic square wave of unequal amplitudes.
3. The file sink shows the repeated bit stream (not the desired one; also, the reading of the bits file concludes when the TX is initiated and then turned off).
