# GNSSensing-Dataset

_Open-source GNSS and LiDAR datasets collected via UAV in Hong Kong for vegetation remote sensing_

Unmanned Aerial Vehicles (UAVs) are valuable low-cost remote sensing platforms with exceptional temporal and spatial flexibility. Leveraging UAVs for remote sensing requires lightweight, power-efficient sensors. While airborne LiDAR is highly effective, using reflected Global Navigation Satellite System (GNSS) signals may offer a passive sensing alternative. GNSS provides continuous global coverage, and its signal properties strongly correlate with environmental objects in scattering, reflection, and attenuation. Moreover, low-cost, lightweight consumer-grade receivers can easily capture these signals. Despite these advantages, acquiring experimental datasets remains challenging due to platform construction complexities and local airspace regulations. To address this gap and advance UAV-based GNSS remote sensing, this repository provides an open-access dataset. The collection contains LiDAR measurements, raw GNSS [RINEX](https://en.wikipedia.org/wiki/RINEX) data from an onboard dual-antenna system, and UAV flight logs in [PX4 ULog](https://docs.px4.io/main/en/dev_log/ulog_file_format) format, all captured across diverse vegetated areas in Hong Kong.

**Dataset Authors:** Jiayi ZHOU ([@zhlouise](https://github.com/zhlouise)), Qing Lin TAN ([@A4paper2003](https://github.com/A4paper2003)), Sashenka GAMAGE ([@sashenkagamage](https://github.com/sashenkagamage)), Md Sahat MAHMUD ([@gd-Sahat](https://github.com/gd-Sahat)), and Guohao ZHANG; Faculty of Engineering, The Hong Kong Polytechnic University

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
| [namsangwai_20251109/tree_hover](namsangwai_20251109/tree_hover) | UAV hovers over a waypoint over dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/84fd5a54-d564-49e3-8fa1-cfab21d918e6" /> |
| [namsangwai_20251109/waypoint_dynamic](namsangwai_20251109/waypoint_dynamic) | UAV hovers multiple waypoints over dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/c58468d2-3393-40ce-aec4-812e37006c90" /> |
| [namsangwai_20251109/survey_1](namsangwai_20251109/survey_1) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/776eb851-3f85-41bd-af5d-c5350c5c6115" /> |
| [namsangwai_20251109/survey_2](namsangwai_20251109/survey_2) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/f400f396-d4c9-4fa5-a7bb-68fe61990a4b" /> |
| [namsangwai_20251109/survey_3](namsangwai_20251109/survey_3) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/6b5186a3-ee96-4eba-b9ee-b55c09b17b67" /> |
| [mountdavis_20260201/survey_1](mountdavis_20260201/survey_1) | UAV flies over a survey area that covers bare ground with grass. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/a345626e-8da1-4324-a40e-14edcb3db44e" /> |
| [mountdavis_20260201/survey_2](mountdavis_20260201/survey_2) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/e4d021cd-cda0-434d-9dab-1c0994276c83" /> |
| [mountdavis_20260201/survey_3](mountdavis_20260201/survey_3) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/f440c2d8-a419-4a30-b614-201256d73d90" /> |
| [mountdavis_20260201/survey_4](mountdavis_20260201/survey_4) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/b8e91e84-5c92-4f64-a0c4-131e141faed7" /> |
| [shingmun_20260308/survey_1](shingmun_20260308/survey_1) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/a4707664-02a3-4977-835a-1afcc885faed" /> |
| [shingmun_20260308/survey_2](shingmun_20260308/survey_2) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/3bbec392-873e-4fe3-9642-b9e46ee031e2" /> |
| [shingmun_20260308/survey_3](shingmun_20260308/survey_3) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/676a8c81-427e-4394-afe0-d850e9120cb0" /> |
| [shingmun_20260308/survey_4](shingmun_20260308/survey_4) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/b7ef9eea-509e-4b53-a40c-57aeb8f13ee3" /> |
| [mountdavis_20260331/survey_1](mountdavis_20260331/survey_1) | UAV flies over a survey area that covers bare ground with grass. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/d60a5ddc-d7c1-4135-af59-65dc0bf2db38" /> |
| [mountdavis_20260331/survey_2](mountdavis_20260331/survey_2) | UAV flies over a survey area that covers bare ground with grass. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/582a249a-bf9c-4630-933d-75ddc243dfd6" /> |
| [mountdavis_20260331/survey_3](mountdavis_20260331/survey_3) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/8dab3c28-8e54-48b2-b3c9-28d4464c8cc2" /> |
| [mountdavis_20260331/survey_4](mountdavis_20260331/survey_4) | UAV flies over a survey area that covers dense vegetation. | GNSS | <img width="100%" src="https://github.com/user-attachments/assets/74557eb4-8d94-4e65-90e8-947dcbafd4e4" /> |

## Acknowledgements
This dataset was produced as part of a final-year project supported by the Faculty of Engineering, The Hong Kong Polytechnic University.

## Related Publication
TBA
