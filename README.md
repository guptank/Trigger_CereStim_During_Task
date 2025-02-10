# Monkey CANTAB - Stimulation Interface for Paired Associate Learning (PAL) Task
This software interface allows integration of the Monkey CANTAB Paired Associate Learning (PAL) task with stimulation hardware, as it interfaces with two digital outputs sent by the Monkey CANTAB system during the task: STIMULUSINFO and REINFORCEMENTINFO.

## Overview
The Monkey CANTAB software during the PAL task sends two digital outputs:

* STIMULUSINFO: This signal is "ON" throughout the entire stimulus presentation.
* REINFORCEMENTINFO: This output is programmable in Monkey CANTAB and can have two different pulse widths for reward and punishment.
However, pre-stimulus stimulation is not possible with the default setup. To enable this functionality, this software was developed to interface with stimulation hardware.

## Requirements
To use this interface, the following are required:

* CANTAB Software: Installed and running the PAL Task on Monkey CANTAB.
* CereStim (Blackrock): For stimulation hardware.
* NI DAQ 6001: National Instruments Data Acquisition device.
* LABVIEW: For controlling the DAQ and managing stimulation parameters.


## Connection to DAQ
The following connections should be made between the DAQ and other devices:

* DAQ ai0: Receives the STIMULUSINFO signal from the CANTAB system.
* DAQ ai1: Receives the REINFORCEMENTINFO signal.
* DAQ a0: Sends a signal to trigger the CereStim stimulation hardware.


## How to Run 
* Select a Stimulation Condition: From the dropdown menu, choose one of the available stimulation conditions (see below).
* Enter Task Parameters: Ensure the task parameters match those configured in Monkey CANTAB.
* Execute LABVIEW Code: Run the provided LabVIEW code on a computer connected to the DAQ to trigger the appropriate stimulation conditions.


### Available Conditions
Choose from the following stimulation conditions available in the dropdown:

* Pre Sample Onset: Stimulation begins before sample onset and stops when STIMULUSINFO is turned off.
* Pre Choice Onset: Stimulation begins before choice onset and stops when STIMULUSINFO is turned off.
* Pre Sample And Choice Onset: Stimulation begins before sample and choice onset, stopping when STIMULUSINFO is turned off.
* Pre 1st Sample till SamplePhase Offset: Stimulation begins before the first sample and continues until the sample phase offset.
* Pre 1st Choice till ChoicePhase Offset: Stimulation begins before the first choice and continues until the choice phase offset.
* During Memory Delay: No stimulation during onset time; occurs during the memory delay phase.
* During ITI (Intertrial Interval): No stimulation during onset time; occurs during the intertrial interval.
* Entire Trial: Stimulation begins at Pre 1st Sample and ends at trial completion.
* Pre Sample Onset (STOPS AT STIMULUSINFO ON): Stimulation occurs before sample onset and stops when STIMULUSINFO is turned on.
* PreStim (n-m seconds): Customizable pre-stimulus interval in seconds.


## Notes
Pre-stimulus stimulation can be configured using this interface, which is not supported natively by Monkey CANTAB.
Ensure that all devices are correctly connected and configured before running the system.
