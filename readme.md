
## Overview
Robust multilingual speech processing systems that can handle diverse recording environments, accents, registers and spontaneous code-switching behaviours across 
individuals are much needed for advancing progress in fair and inclusive speech technologies. In response to the need for more reliable language identification and language diarization systems, we present the **Multilingual Everyday Recordings – Language Identification on Child-Directed Speech Challenge (MERLIon CCS Challenge)**. 

The MERLIon CCS Challenge has been pre-selected as a special session at [Interspeech 2023](https://www.interspeech2023.org/). 

The MERLIon CCS Challenge features a unique first-of-its-kind Zoom videocall dataset from 
the [Talk Together Study](https://www.frontiersin.org/articles/10.3389/fpsyg.2021.734936/full), with:  
- more than 30 hours of Singaporean English/Mandarin code-switched child-directed 
speech  
- featuring more than 100 voices 
- over 300 recordings manually annotated by at least 2 multilingual transcribers 

To access the MERLIon CCS dataset, please register for the challenge [here](https://ntusingapore.qualtrics.com/jfe/form/SV_1LY2Irep9sEkITk?jfefe=new).
More information can be found on [our website](https://sites.google.com/view/merlion-ccs-challenge/). 

## Evaluation plan
- [v1.2](https://bit.ly/merlion-ccs-eval-plan-v1-2)
- [v1.1](https://bit.ly/merlion-ccs-eval-plan-v1-1)
- [v1.0](https://bit.ly/merlion-ccs-eval-plan-v1)


## Tasks

There are two tasks: [Task 1 (Language Identification)](https://sites.google.com/view/merlion-ccs-challenge/task-1?authuser=0) and [Task 2 (Language Diarization)](https://sites.google.com/view/merlion-ccs-challenge/task-2?authuser=0) in the MERLIon CCS Challenge. 

## Baseline system
The [baseline system](https://github.com/MERLIon-Challenge/merlion-ccs-2023-baseline) is an end-to-end conformer model for both tasks. The model consists of four conformer encoder layers followed by a statistics pooling layer and three linear layers with ReLU activation in the first two linear layers. All self-attention encoder layers have eight attention heads with input and output dimensions being 512, and the inner layer of the position-wise feed-forward network is of dimensionality 2048. The 39-dimensional Mel Frequency Cepstral Coefficients (MFCC) features comprising 13-dim MFCCs and their first- and second-order deviations are extracted for each speech signal before being fed into the conformer encoder layers. The statistics pooling layer then generates a 1024-dimensional output which is finally projected by three linear layers to the number of target languages. The three linear layers comprise 1024, 512, and 2 output nodes.

The training data comprise 200 hours of AISHELL Mandarin data, 100 hours of Librispeech data, and 100 hours of National Speech Corpus data. The speech signals in these datasets are segmented into maximum of 3s prior to the feature extraction stage. The model is trained for five epochs with batch size 32 and updated with a learning rate that warms up from 0 to 10^-4 in 5000 steps followed by the cosine annealing decay.

An energy-based voice activity detection is performed on the test data to identify the silent parts for the diarization task. Each speech signal is partitioned into speech clips after removing silences before we perform language identification on these clips, where we assume there is no code-switch exists in each speech clip.

For Task 1 (Language Identification), the baseline system achieved the following results on the MERLIon CCS Development set (N:
| Equal Error Rate | Balanced Accuracy    | Current Accuracy  |
| :---:            | :---:                | :---:             |
|22.1328%          | 50.32%               | 77.7681%          |

For Task 2 (Language Diarization), the baseline system achieved the following results on the MERLIon CCS Development set:
| Language Diarization Error Rate | English Language Error Rate    | Mandarin Language Error Rate |
| :---:                           | :---:                          | :---:                        |
| 0.8404                       | 0.8051                       | 1.0115                      |
  
The baseline system and scoring scripts for each task can be found [here](https://github.com/MERLIon-Challenge/merlion-ccs-2023-baseline).

## Datasets

### Training Data

For both Task 1 and 2, there is a closed track and an open track, placing limits on the amount of training data that can be used. More information on the tracks and the training data can be found [here](https://sites.google.com/view/merlion-ccs-challenge/datasets?authuser=0).

### Development and Evaluation Datasets 
The development set and evaluation set are Challenge-ready partitions of a larger dataset from the [Talk Together Study](https://www.frontiersin.org/articles/10.3389/fpsyg.2021.734936/full) which examines parent-child interactions in multilingual Singapore, and will be provided by the organizers. Please [register](https://ntusingapore.qualtrics.com/jfe/form/SV_1LY2Irep9sEkITk) for the challenge and we will send you further instructions for accessing the datasets.

## Submission

Submissions of results will be made on CodaLab. More information can be found on [our website](https://sites.google.com/view/merlion-ccs-challenge/submission?authuser=0).

## Organising committee
Leibny Paola Garcia Perera, Johns Hopkins University
YH Victoria Chua, Nanyang Technological University
Hexin Liu, Nanyang Technological University
Fei Ting Woon, Nanyang Technological University
Andy Khong, Nanyang Technological University
Justin Dauwels, TU Delft
Sanjeev Khudanpur, John Hopkins University
Suzy J Styles, Nanyang Technological University


## Contact
Please contact Victoria at **merlion.challenge@gmail.com** or visit us at [our website](https://sites.google.com/view/merlion-ccs-challenge/) if you have any questions. 

Sign up for our [mailing list](https://groups.google.com/u/1/g/merlion-ccs-challenge) or join our [LinkedIn group](https://www.linkedin.com/groups/14193386/) for updates!
