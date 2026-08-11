# GNSSensing-Dataset

_Open-source GNSS and LiDAR datasets collected via UAV in Hong Kong for vegetation remote sensing_

Unmanned Aerial Vehicles (UAVs) are valuable low-cost remote sensing platforms with exceptional temporal and spatial flexibility. Leveraging UAVs for remote sensing requires lightweight, power-efficient sensors. While airborne LiDAR is highly effective, using reflected Global Navigation Satellite System (GNSS) signals may offer a passive sensing alternative. GNSS provides continuous global coverage, and its signal properties strongly correlate with environmental objects in scattering, reflection, and attenuation. Moreover, low-cost, lightweight consumer-grade receivers can easily capture these signals. Despite these advantages, acquiring experimental datasets remains challenging due to platform construction complexities and local airspace regulations. To address this gap and advance UAV-based GNSS remote sensing, this repository provides an open-access dataset. The collection contains LiDAR measurements, raw GNSS RINEX data from an onboard dual-antenna system, and UAV flight logs in PX4 Ulog format, all captured across diverse vegetated areas in Hong Kong.

## Table of Contents
* [UAV Setup](#uav-setup)
* [Repository Structure](#repository-structure)
* [Dataset Summary](#dataset-summary)
* [Acknowledgements](#acknowledgements)
* [Related Publication](#related-publication)

## UAV Setup
The UAV platform for data collection is a Holybro X650 quadcopter. The platform is equipped with: 
* A Pixhawk 6C flight controller
* An M10 GPS module (not for sensing purposes)
* A pair of SiK telemetry radios
* An Nvidia Jetson Orin Nano
* A Livox Mid-360 LiDAR
* A pair of Ublox F9P GNSS receivers + L1/L2 band antennas
  * Zenith antenna is an upward-facing Right-Hand-Circular-Polarized (RHCP) antenna
  * Nadir antenna is a downward-facing Left-Hand-Circular-Polarized (LHCP) antenna

<img width="100%" alt="UAV Setup" src="https://github.com/user-attachments/assets/10d3f1da-d85d-4842-bf41-6fddd7e23e53" />

## Repository Structure

```
location_date/
└── flight_type(_number)/
    ├── down_antenna_*.obs  # Raw RINEX data from the nadir LHCP antenna
    ├── up_antenna_*.obs    # Raw RINEX data from the zenith RHCP antenna
    └── *.ulg              # PX4 ULog file containing UAV flight logs
```

## Dataset Summary


## Acknowledgements

## Related Publication
