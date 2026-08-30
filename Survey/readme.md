survey.grc

SDR channel survey tool - measures signal power on a selected channel relative to a noise reference, to detect occupied FM-band channels.

Signal chain

osmosdr_source_0 - SDR input, 20 Msps, tuned to receiver_center_freq (97.9 MHz default)

Two parallel freq_xlating_fir_filter taps, both decimating to 200 kHz (Bandwidth):
- Signal path - centered on channel_selector (the channel under test, tunable 88-200 MHz via GUI slider)
- Noise reference path - offset +600 kHz from the signal path, used as a floor/reference

Each path: complex_to_mag_squared -> moving_average (1000-sample, scaled x10e-3) -> nlog10 -> power in dB

blocks_sub_xx_0 subtracts noise-reference dB from signal dB to give relative SNR

Outputs

qtgui_freq_sink_x_0 - full-band spectrum display (Blackman-Harris window, -140 to 10 dB range)
qtgui_number_sink_0 - SNR (dB), signal minus noise reference
qtgui_number_sink_1 - raw signal power (dB)

Key variables

| Variable | Value | Meaning |
|---|---|---|
| samp_rate | 20e6 | SDR sample rate |
| Bandwidth | 200e3 | Post-decimation channel bandwidth |
| channel_selector | 88e6 to 200e6 (GUI slider, 100 kHz steps) | Channel under test |
| receiver_center_freq | 97.9e6 | SDR tuner center freq |

Note

The noise reference is a fixed +600 kHz offset from the channel under test, not a true noise floor measurement - valid as long as that offset itself doesn't land on another active channel.
