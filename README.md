# GNSSensing-Dataset

_Open-source GNSS and LiDAR datasets collected via UAV in Hong Kong for vegetation remote sensing_

Unmanned Aerial Vehicles (UAVs) are valuable low-cost remote sensing platforms with exceptional temporal and spatial flexibility. Leveraging UAVs for remote sensing requires lightweight, power-efficient sensors. While airborne LiDAR is highly effective, using reflected Global Navigation Satellite System (GNSS) signals may offer a passive sensing alternative. GNSS provides continuous global coverage, and its signal properties strongly correlate with environmental objects in scattering, reflection, and attenuation. Moreover, low-cost, lightweight consumer-grade receivers can easily capture these signals. Despite these advantages, acquiring experimental datasets remains challenging due to platform construction complexities and local airspace regulations. To address this gap and advance UAV-based GNSS remote sensing, this repository provides an open-access dataset. The collection contains LiDAR measurements, raw GNSS [RINEX](https://en.wikipedia.org/wiki/RINEX) data from an onboard dual-antenna system, and UAV flight logs in [PX4 ULog](https://docs.px4.io/main/en/dev_log/ulog_file_format) format, all captured across diverse vegetated areas in Hong Kong.

**Dataset Authors: ** Jiayi ZHOU, Qing Lin TAN, Sashenka GAMAGE, Md Sahat MAHMUD, Guohao ZHANG; Faculty of Engineering, The Hong Kong Polytechnic University

## Table of Contents
* [UAV Setup](#uav-setup)
* [Repository Structure](#repository-structure)
* [Dataset Summary](#dataset-summary)
* [Acknowledgements](#acknowledgements)
* [Related Publication](#related-publication)

## UAV Setup
The UAV platform for data collection is a Holybro X650 quadcopter. The platform is equipped with: 
* A [Pixhawk 6C flight controller](https://docs.holybro.com/autopilot/pixhawk-6c)
* An [M10 GPS module](https://docs.holybro.com/gps-and-rtk-system/m8n-m9n-m10-gps/standard-m10-m9n-m8n-gps/overview) (not for sensing purposes)
* A pair of [SiK telemetry radios](https://docs.holybro.com/radio/sik-telemetry-radio-v3)
* An [Nvidia Jetson Orin Nano](https://docs.nvidia.com/jetson/orin-nano-devkit/user-guide/latest/index.html)
* A [Livox Mid-360 LiDAR](https://www.livoxtech.com/mid-360)
* A pair of [Ublox F9P GNSS receivers](https://www.u-blox.com/en/product/zed-f9p-module) + [L1/L2 band antennas](https://www.u-blox.com/en/product/ann-mb-series#Product-description)
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
| Dataset | Description | Available Sensors | Flight Trajectory |
| --- | --- | --- | --- |
| [namsangwai_20251109/ground_hover](namsangwai_20251109/ground_hover) | UAV hovers over a waypoint over bare soil. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/feff3a11-2044-49cd-bcb0-d189549545e6" /> |



## Acknowledgements

## Related Publication
