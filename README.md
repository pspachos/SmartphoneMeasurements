# Smartphone Measurements

This repository contains data measured from various smartphones that relate to energy consumption and throughput. Currently, data exists for four Samsung phones: S4 Mini, Galaxy Note 3, Galaxy Note 4, and MEGA.

The Monsoon is a power monitor that can also be used as a supply. To measure each smartphone, the battery was disconnected and replaced with probes from the Monsoon to retrieve the amount of energy being used. The data provides power measurements for each of the phones along with voltage and current. In this series of data, the sample time was 0.2 seconds. The columns are organized as follows: Time(s), Current (A), Power (W), and Voltage (V).

The iPerf directory contains the corresponding WiFi throughput of the smartphones during the experiment. The Bluetooth tests transferred a single fixed size file and were timed to calculate the throughput. LTE throughput was determined by using a free speed test app. The columns are organized as follows: ID, Time (s), Packet Size (MB), and Bandwidth (Mbits/s).

All smartphones were tested with matching conditions including: full brightness, solid white background, and no third party background applications running aside from those relating to the experiment in question.  Every experiment lasted for three minutes with the exception of Bluetooth and LTE as separate tools and methods were required for throughput measurement. Power measurement started a minute after setting up the proper configuration, to ensure the only power consumption in the smartphone is from the experiments. There are five main experiments for each smartphone.

**Baseline.** The smartphone is powered but all the communications are disabled, including bluetooth, wireless and LTE connections. This baseline is used later on to estimate the actual power being used by the different types of wireless connections.

**WiFi (2.4 GHz).** The smartphone connects to a PC through a basic wireless router. iPerf3 was used to measure the throughput. iPerf3 contains options to either stream data to or from the smartphone based on a client/server model as well as stream through TCP or UDP. This setup contains four configurations for each phone:

- The phone is acting as the client and downloads data from the PC in TCP mode.
- The phone is acting as the client and downloads data from the PC in UDP mode.
- The phone is acting as the client and uploads data to the PC in TCP mode.
- The phone is acting as the client and uploads data to the PC in UDP mode.
 
**WiFi Direct (2.4 GHz).** The smartphone connects to the PC over WiFi Direct. The same options for server/client  and TCP/UDP as the previous WiFi experiments can also be applied here with iPerf3.

**Bluetooth.** The smartphone is connected to a Bluetooth peer to peer connection. There are two configurations that are run for this test:

- The phone acting as the client.
- The phone acting as the server.

Both configurations will be communicating with a LG G4 smartphone for the duration of the experiment.

**LTE.** The smartphone uses the LTE network to connect to the internet. Two configurations exist for these tests:

- The phone acting as the client.
- The phone acting as the server.

A total of 13 tests for each smartphone. Considering that all experiments are run with four different phones, 52 sets of data exist to be compared.
