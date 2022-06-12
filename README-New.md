# dcase2021_task2_mobile_net_v2
MobileNetV2-based baseline system for [DCASE2021 Challenge Task 2](http://dcase.community/challenge2021/task-unsupervised-detection-of-anomalous-sounds).

## Description
This system consists of two main scripts:
- `00_train.py`
  - "Development" mode: 
    - This script trains a model for each machine type by using the directory `dev_data/<machine_type>/train/`.
  - "Evaluation" mode: 
    - This script trains a model for each machine type by using the directory `eval_data/<machine_type>/train/`. (This directory will be from the "additional training dataset".)
- `01_test.py`
  - "Development" mode:
    - This script makes a csv file for each section including the anomaly scores for each wav file in the directories `dev_data/<machine_type>/source_test/` and `dev_data/<machine_type>/target_test/`.
    - The csv files are stored in the directory `result/`.
    - It also makes a csv file including AUC, pAUC, precision, recall, and F1-score for each section.
  - "Evaluation" mode: 
    - This script makes a csv file for each section including the anomaly scores for each wav file in the directories `eval_data/<machine_type>/source_test/` and `eval_data/<machine_type>/target_test/`. (These directories will be from the "evaluation dataset".)
    - The csv files are stored in the directory `result/`.
as Yohei Kawaguchi mentioned before here are some steps below you should follow to get your results

-after unzipping any version put the code inside a folder called dcase2021_task2_mobile_net_v2
-create a folder called results 
-create another folder called model
-if you want to get same results as version 2 or 3 you should add 30% more data pitch shifted or time stretched using notebook called data-augmenting.py
-to run the training process open the prompt and set up your dependencies in an enviroment open the folder dcase2021_task2_mobile_net_v2
-then type 00_train.py -d
-to test type 00_test.py

## Dependency
We develop the source code on Ubuntu 16.04 LTS and 18.04 LTS.
In addition, we checked performing on **Ubuntu 16.04 LTS**, **18.04 LTS**, **CentOS 7**, and **Windows 10**.

### Software packages
- p7zip-full
- Python == 3.6.5
- FFmpeg

### Python packages
- Keras                         == 2.3.0
- Keras-Applications            == 1.0.8
- Keras-Preprocessing           == 1.0.5
- matplotlib                    == 3.0.3
- numpy                         == 1.18.1
- PyYAML                        == 5.1
- scikit-learn                  == 0.22.2.post1
- scipy                         == 1.1.0
- librosa                       == 0.6.0
- audioread                     == 2.1.5 (more)
- setuptools                    == 41.0.0
- tensorflow                    == 1.15.0
- tqdm                          == 4.43.0

## Citation
If you use this baseline system, please cite all the following three papers:
- Yohei Kawaguchi, Keisuke Imoto, Yuma Koizumi, Noboru Harada, Daisuke Niizumi, Kota Dohi, Ryo Tanabe, Harsh Purohit, and Takashi Endo, "Description and Discussion on DCASE 2021 Challenge Task 2: Unsupervised Anomalous Sound Detection for Machine Condition Monitoring under Domain Shifted Conditions," in arXiv e-prints: 2106.04492, 2021. [URL](https://arxiv.org/abs/2106.04492)
- Noboru Harada, Daisuke Niizumi, Daiki Takeuchi, Yasunori Ohishi, Masahiro Yasuda, Shoichiro Saito, "ToyADMOS2: Another Dataset of Miniature-Machine Operating Sounds for Anomalous Sound Detection under Domain Shift Conditions," in arXiv e-prints: 2106.02369, 2021. [URL](https://arxiv.org/abs/2106.02369)
- Ryo Tanabe, Harsh Purohit, Kota Dohi, Takashi Endo, Yuki Nikaido, Toshiki Nakamura, and Yohei Kawaguchi, "MIMII DUE: Sound Dataset for Malfunctioning Industrial Machine Investigation and Inspection with Domain Shifts due to Changes in Operational and Environmental Conditions," in arXiv e-prints: 2105.02702, 2021. [URL](https://arxiv.org/abs/2105.02702)
