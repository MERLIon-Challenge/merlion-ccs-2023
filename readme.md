## UPDATES (Last Updated 28/5/2024)

The MERLIon CCS Challenge 2023 was a special session at [Interspeech 2023](https://www.interspeech2023.org/), held on Wednesday 23rd August 2023 (4pm to 6pm). 

**The MERLIon CCS Challenge will remain open indefinitely to encourage model development. The development and evaluation set is publicly available (https://doi.org/10.21979/N9/ANXS8Z).**

When using the dataset, please cite:
- Chua, Victoria Yi Han; Garcia Perera, Leibny Paola; Khudanpur, Sanjeev; Khong, Andy W. H.; Dauwels, Justin; Woon, Fei Ting; Styles, Suzy J, 2023, "Development and Evaluation data for Multilingual Everyday Recordings - Language Identification on Code-Switched Child-Directed Speech (MERLIon CCS) Challenge", https://doi.org/10.21979/N9/ANXS8Z, DR-NTU (Data), V1
 
For a detailed description of the MERLIon CCS dataset, check out our Interspeech 2023 paper:
- Y. H. V. Chua, H. Liu, L. P. Garcia Perera, F. T. Woon, J. Wong, X. Zhang, S. Khudanpur, A. W. H. Khong, J. Dauwels, and S. J. Styles, [MERLIon CCS Challenge: A English-Mandarin code-switching child-directed speech corpus for language identification and diarization](https://www.isca-speech.org/archive/pdfs/interspeech_2023/chua23_interspeech.pdf), doi: 10.21437/Interspeech.2023-1446. 

The winning systems for open and closed tracks presented the following papers during the INTERSPEECH 2023 special session: 
- S. K. Gupta, S. Hiray, P. Kukde (2023). [Spoken Language Identification System for English-Mandarin Code-Switching Child-Directed Speech](https://www.isca-speech.org/archive/pdfs/interspeech_2023/gupta23_interspeech.pdf), doi: 10.21437/Interspeech.2023-1335 
- M. Shahin, Z. Nan, V. Sethu, B. Ahmed (2023). [Improving wav2vec2-based Spoken Language Identification by Learning Phonological Features](https://www.isca-speech.org/archive/pdfs/interspeech_2023/shahin23_interspeech.pdf), doi: 10.21437/Interspeech.2023-2533.
- K. Praveen, B. Radhakrishnan, K. Sabu, A. Pandey, M. A. B. Shaik (2023). [Language Identification Networks for Multilingual Everyday Recordings](https://www.isca-speech.org/archive/pdfs/interspeech_2023/gupta23_interspeech.pdf), doi: 10.21437/Interspeech.2023-2047.

We also presented an analysis of common errors where submitted systems collectively struggle when performing language identification on complex speech: 
- S. J. Styles, Y. H. V. Chua, F. T. Woon, H. Liu, L. P. Garcia Perera, S. Khudanpur, A. W. H. Khong, and J. Dauwels (2023). [Investigating model performance in language identification: beyond simple error statistics](https://www.isca-speech.org/archive/pdfs/interspeech_2023/styles23_interspeech.pdf), doi: 10.21437/Interspeech.2023-1707

The evaluation plan for the challenge can be found in the following sections. 

## Overview
Robust multilingual speech processing systems that can handle diverse recording environments, accents, registers and spontaneous code-switching behaviours across 
individuals are much needed for advancing progress in fair and inclusive speech technologies. In response to the need for more reliable language identification and language diarization systems, we present the **Multilingual Everyday Recordings – Language Identification on Child-Directed Speech Challenge (MERLIon CCS Challenge)**. 

The MERLIon CCS Challenge features a unique first-of-its-kind Zoom videocall dataset from 
the [Talk Together Study](https://www.frontiersin.org/articles/10.3389/fpsyg.2021.734936/full), with:  
- more than 30 hours of Singaporean English/Mandarin code-switched child-directed 
speech  
- featuring more than 100 voices 
- over 300 recordings manually annotated by at least 2 multilingual transcribers 

More information on can be found on [our website](https://sites.google.com/view/merlion-ccs-challenge/). 

## Evaluation plan
- [v1.2](https://arxiv.org/abs/2305.19493) (Last Updated on 17th Feb 2023; Uploaded to arXiV on 31 May 2023)
- [v1.1](https://bit.ly/merlion-ccs-eval-plan-v1-1)
- [v1.0](https://bit.ly/merlion-ccs-eval-plan-v1)


## Tasks

There are two tasks: [Task 1 (Language Identification)](https://sites.google.com/view/merlion-ccs-challenge/task-1?authuser=0) and [Task 2 (Language Diarization)](https://sites.google.com/view/merlion-ccs-challenge/task-2?authuser=0) in the MERLIon CCS Challenge. 

## Baseline system
The [baseline system](https://github.com/MERLIon-Challenge/merlion-ccs-2023-baseline) is an end-to-end conformer model for both tasks. The model consists of four conformer encoder layers followed by a statistics pooling layer and three linear layers with ReLU activation in the first two linear layers. All self-attention encoder layers have eight attention heads with input and output dimensions being 512, and the inner layer of the position-wise feed-forward network is of dimensionality 2048. The 39-dimensional Mel Frequency Cepstral Coefficients (MFCC) features comprising 13-dim MFCCs and their first- and second-order deviations are extracted for each speech signal before being fed into the conformer encoder layers. The statistics pooling layer then generates a 1024-dimensional output which is finally projected by three linear layers to the number of target languages. The three linear layers comprise 1024, 512, and 2 output nodes.

The training data comprise 200 hours of AISHELL Mandarin data, 100 hours of Librispeech data, and 100 hours of National Speech Corpus data. The partitions of each dataset can be found [here](https://sites.google.com/view/merlion-ccs-challenge/datasets?authuser=0). The speech signals in these datasets are segmented into maximum of 3s prior to the feature extraction stage. The model is trained for five epochs with batch size 32 and updated with a learning rate that warms up from 0 to 10^-4 in 5000 steps followed by the cosine annealing decay.

An energy-based voice activity detection is performed on the test data to identify the silent parts for the diarization task. Each speech signal is partitioned into speech clips after removing silences before we perform language identification on these clips, where we assume there is no code-switch exists in each speech clip.

For Task 1 (Language Identification), the baseline system achieved the following results on the MERLIon CCS Development set (N:
| Equal Error Rate | Balanced Accuracy    | Current Accuracy  |
| :---:            | :---:                | :---:             |
|22.1328%          | 50.32%               | 77.7681%          |

For Task 2 (Language Diarization), the baseline system achieved the following results on the MERLIon CCS Development set:
| Language Diarization Error Rate | English Language Error Rate    | Mandarin Language Error Rate |
| :---:                           | :---:                          | :---:                        |
| 86.6%                           | 83.93%                         | 99.8%    
  
The baseline system and scoring scripts for each task can be found [here](https://github.com/MERLIon-Challenge/merlion-ccs-2023-baseline).

## Datasets

### Training Data

For both Task 1 and 2, there is a closed track and an open track, placing limits on the amount of training data that can be used. More information on the tracks and the training data can be found [here](https://sites.google.com/view/merlion-ccs-challenge/datasets?authuser=0).

### Development and Evaluation Datasets 
The development set and evaluation set are Challenge-ready partitions of a larger dataset from the [Talk Together Study](https://www.frontiersin.org/articles/10.3389/fpsyg.2021.734936/full) which examines parent-child interactions in multilingual Singapore, and is now publicly available (https://doi.org/10.21979/N9/ANXS8Z).

## Submission

Submissions of results can be made on our CodaLab pages. More information can be found on [our website](https://sites.google.com/view/merlion-ccs-challenge/submission?authuser=0).

NOTE: The CodaLab pages have re-opened after Interspeech 2023. Please read the instructions on our website carefully for the formatting of results submission files and folders. 

## Organising committee
-Leibny Paola Garcia Perera, Johns Hopkins University
-YH Victoria Chua, Nanyang Technological University
-Hexin Liu, Nanyang Technological University
-Fei Ting Woon, Nanyang Technological University
-Andy Khong, Nanyang Technological University
-Justin Dauwels, TU Delft
-Sanjeev Khudanpur, John Hopkins University
-Suzy J Styles, Nanyang Technological University

## Contact
Please contact Victoria Chua at **merlion.challenge@gmail.com** or visit us at [our website](https://sites.google.com/view/merlion-ccs-challenge/) if you have any questions. 

Sign up for our [mailing list](https://groups.google.com/u/1/g/merlion-ccs-challenge) or join our [LinkedIn group](https://www.linkedin.com/groups/14193386/) for updates!
