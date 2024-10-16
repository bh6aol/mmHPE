# mmHPE: Robust Multi-Scale 3D Human Pose Estimation Using a Single mmWave Radar
This repository represents the official implementation of the [mmHPE: Robust Multi-Scale 3D Human Pose Estimation Using a Single mmWave Radar](https://doi.org/10.1109/JIOT.2024.3476350).

> [2024/10/10] We will release the code and dataset soon. Thanks.

## 1. Overview
![overview](imgs/overview.png)

| ![walking_place](imgs/walking_place.gif) | ![squat](imgs/squat.gif) |
|:------:|:-------:|
|walking in place|squatting deeply|
| ![walking_back_forth](imgs/walking_back_forth.gif) | ![walking_left_right](imgs/walking_left_right.gif) |
|walking back and forth|walking from side to side|
| ![stand_with_arm_swing](imgs/stand_with_arm_swing.gif) | ![sit_typing](imgs/sit_typing.gif) |
|standing and waving|sitting and typing|
| ![circle](imgs/circle.gif) | ![walking_random](imgs/walking_random.gif) |
|walking in a circle|walking at random|


## 2. Dataset
7 volunteers (including 5 males and 2 females) simulated 11 activities of daily life, including (1) walking in a circle; (2) sitting and turning their heads; (3)
sitting and shaking their legs; (4) sitting and using a cell phone; (5) sitting and typing; (6) squatting deeply; (7) standing and waving; (8) walking back and forth; (9) walking from side to
side; (10) walking in place; (11) walking at random. For each activity, subjects repeated it 8 times for 40 seconds each time.
```
mmHPE Dataset
 ├─radar
 │  ├─{subject}_{scene}_{sample}.bin
 │  └─...
 ├─video
 │  └─depth 
 │     ├─{subject}_{scene}_{sample}.mkv
 │     └─...
 └─label
    ├─{subject}_{scene}_{sample}.csv
    └─...
```


### 2.1 Devices && Configurations
 - [AWR1843BOOST mmWave radar](https://www.ti.com/tool/AWR1843BOOST) + [DCA1000EVM](https://www.ti.com/tool/DCA1000EVM)
 - [Azure Kinect](https://www.microsoft.com/en-us/d/azure-kinect-dk/8pp5vxmd9nhq)
```
-------- Radar Cfg --------
-- General
NUM_TX = 3
NUM_RX = 4

-- ProfileConfig
START_FREQ = 77 -- GHz
IDLE_TIME = 10 -- us
RAMP_END_TIME = 60 -- us
ADC_START_TIME = 4 --us
FREQ_SLOPE = 64.985 -- MHz/us
ADC_SAMPLES = 128
SAMPLE_RATE = 2500  -- ksps
RX_GAIN = 30 -- dB

-- FrameConfig
START_CHIRP_TX = 0
END_CHIRP_TX = 2 
CHIRP_LOOPS = 32 
PERIODICITY = 16.666665  -- ms
```

```
-------- Camera Cfg --------
FPS:              K4A_FRAMES_PER_SECOND_30
Depth mode:       K4A_DEPTH_MODE_WFOV_2X2BINNED
Color format:     K4A_IMAGE_FORMAT_COLOR_BGRA32
Color resolution: K4A_COLOR_RESOLUTION_720P
```

### 2.2 Download
Download `mmHPE Dataset` from [123pan](https://www.123pan.com/s/nkn0Td-OrZi3) (Code: onFg).


## 3. Installation
## 4. Citation
```
@article{wu2024mmhpe,
  title={mmHPE: Robust Multi-Scale 3D Human Pose Estimation Using a Single mmWave Radar},
  author={Wu, Yingxiao and Jiang, Zhongmin and Ni, Haocheng and Mao, Changlin and Zhou, Zhiyuan and Wang, Wenxiang and Han, Jianping},
  journal={IEEE Internet of Things Journal},
  year={2024},
  publisher={IEEE}
}
```
## 5. Acknowledgments



