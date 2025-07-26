<div align="center"> 
<h1> OpAmp - CIA 2024 </h1>
</div>
  

## Description

This repository contains an operational amplifier designed as part of the *Analog Integrated Circuits (CIA)* course, taught by Professor Dr. Cesar Augusto Prior during the first semester of 2024 in the Computer Engineering (UFSM) program.

It was my first experience with analog design and *layout* implementation.

The circuit was developed using the Virtuoso design environment and the *gpdk45* design kit.


## Applications 

-   Comparators

-   DC Amplifiers

-   Active Filters

-   Summing Amplifiers

-   Integrators / Differentiators


<p align="center">
  <img src="images/typical_app.png"  width="80%">
</p>

## Technical Specifications

<div align="center">

| Property                                 | Value  | Unit        |
|:----------------------------------------:|:------:|:-----------:|
| Power Supply Voltage                     | 2      | V           |
| Power Consumption                        | 0.53   | mW          |
| DC Gain                                  | 1235   | —           |
| DC Offset                                | 1      | V           |
| CMIR (Common-Mode Input Range)          | 0 – 1.9 | V          |
| Output Swing                             | 1.9 – 0 | V          |
| Open-Loop Gain                           | 61.8   | dB          |
| Gain Margin                              | 13.91  | dB          |
| Phase Margin                             | 55.59  | degrees (°) |
| Cutoff Frequency                         | 63     | kHz         |
| GBW (Gain-Bandwidth Product)             | 77.8   | MHz         |
| CMRR (Common-Mode Rejection Ratio)       | 64.9   | dB          |
| PSRR<sub>DC</sub> (Power Supply Rejection Ratio) | 66.35  | dB          |
| Settling Time                            | 38.5   | ns          |
| Slew Rate                                | 72     | V/µs        |

</div>

## Block Diagram

<p align="center">
<img src="images/diagrama_de_blocos.png" width="100%">
</p>


<p align="center">
<img src="images/block_params.png" width="85%">
</p>

*Regions 0, 1, and 2 represent cutoff, triode, and saturation, respectively.*

*C0 = 0.5pF*

## Layout

It was my very first one, so don’t expect miracles! 😅

<div style="text-align: center;">
<img src="images/Screenshot from 2025-07-21 10-43-55.png"  width="100%">
</div>

## DC Analysis

### Gain and Offset

A DC sweep from $0 \text{V}$ to $2 \text{V}$ was applied to the non-inverting input, while the inverting input was held at a constant $1 \text{V}$ DC. 

<div style="text-align: center;">
  <img src="images/dc_gain_offset_schema.png"  
       width="100%">
</div>

<br />

<div style="text-align: center;">
  <img src="images/dc_offset_and_gain.png" 
       width="100%">
</div>

### CMIR – Common-Mode Input Range

For the CMIR analysis, a unity-gain amplifier was built, in which the non-inverting input was linearly swept from $0\ \text{V}$ to $2\ \text{V}$.


<p align="center">
  <img src="images/CMIR_schema.png" 
       width="80%">
</p>
<br />
<div style="text-align: center;">
  <img src="images/CMIR.png" 
       width="100%">
</div>


### Output Swing 

<p align="center">
  <img src="images/output_swing_schema.png" 
       width="80%">
</p>
<br />
<div style="text-align: center;">
  <img src="images/Output_swing.png" 
       width="100%">
</div>

## AC Analysis

For the stability and frequency response tests, the DC level of both sources was set to $1\ \text{V}$, while a frequency sweep from $1\ \text{G}$ to $10\ \text{G}$ was applied to the non-inverting input, with 10 points per decade.


<p align="center">
  <img src="images/AC_Schema.png" width="80%">
</p>


### Stability

<p align="center">
  <img src="images/estabilidade.png" width="100%">
</p>


### Gain Margin

<p align="center">
  <img src="images/gain_margin.png" width="100%">
</p>


### Phase Margin

<p align="center">
  <img src="images/phase_margin.png" width="100%">
</p>


### Cutoff Frequency and GBW (Gain-Bandwidth Product)

<p align="center">
  <img src="images/frequencia de corte.png" width="100%">
</p>


The Gain-Bandwidth Product is:

$$GBW = Av_{DC} \cdot f_c = 1235 \cdot 63kHz = 77.8MHz$$

### CMRR (Common-Mode Rejection Ratio)

The frequency sweep was applied to both input signal sources.


<p align="center">
  <img src="images/CMRR_schema.png" width="80%">
</p>

<br />

<p align="center">
  <img src="images/CMRR.png" width="100%">
</p>


### PSRR (Power Supply Rejection Ratio)

The frequency sweep was applied to the power supply.


<p align="center">
  <img src="images/PSRR_Schemaa.png" width="80%">
</p>
<br />
<p align="center">
  <img src="images/PSRR.png" width="100%">
</p>

# Transient Analysis

A square wave was applied to the inverting input with a period of $50\ \mu\text{s}$, rise and fall times of $20\ \text{ps}$, and a pulse width of $25\ \mu\text{s}$.


<p align="center">
  <img src="images/tran_Schema.png" width="80%">
</p>

### Settling Time

<p align="center">
  <img src="images/settlingTime.png" width="100%">
</p>

### Slew Rate

<p align="center">
  <img src="images/slewRate.png" width="100%">
</p>
