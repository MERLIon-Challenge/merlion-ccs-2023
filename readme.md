
## Overview
In response to the need for more reliable language identification and language diarization systems, we present: the MERLIon CCS Challenge, the first ever challenge featuring audio recordings from the Talk Together Study, a unique first-of-its-kind Zoom videocall dataset. Aligning closely with [Interspeech 2023](https://www.interspeech2023.org/)’s theme, we present the challenge of developing robust language identification and language diarization systems that are reliable for non-standard accented, bilingual, child-directed speech collected via a videocall platform. 
With this challenge, we hope to test the robustness of existing language diarization systems, and to get the research community to propose novel solutions in terms of adaptation, training, and novel embedding extraction for this particular set of tasks. 

More information can be found on [our website](https://sites.google.com/view/merlion-ccs-challenge/).

## Registration
Registration can be done by submitting below form.

[Register here](https://ntusingapore.qualtrics.com/jfe/form/SV_1LY2Irep9sEkITk?jfefe=new)


## Evaluation plan
- [v0.1](https://bit.ly/merlion-ccs-eval-plan-v1)


## Datasets
### Closed Tracks 
For the closed tracks of both Tasks 1 and 2, participants are only allowed to use the following to train their systems:
100 hours of clean speech from LibriSpeech ASR corpus (partition can be downloaded [here](https://www.openslr.org/resources/12/train-clean-100.tar.gz)). 

Note: There are other mirrors available at https://www.openslr.org/12/. Only the dataset labeled as training set of 100 hours "clean" speech (i.e., train-clean-100.tar.gz) should be used.

100 hours of preselected partition from the National Speech Corpus (partition can be downloaded [here](https://bit.ly/merlion-ccs-nsc-partition))

200 hours of preselected partition from AISHELL (filenames of preselected partition [here](https://bit.ly/merlion-ccs-aishell-filenames))

The Mandarin-English Codeswitching in Southeast Asia (LDC2015S04) Corpus 
This corpus is provided for the MERLIon CCS challenge courtesy of the Linguistic Data Consortium (LDC). Only registered participants of the challenge will be allowed access to the corpus. The corpus will be distributed by the LDC. To access this dataset, please sign the LDC data license agreement and send it to LDC directly (ldc@ldc.upenn.edu). Once LDC have verified the agreement, the team will receive further instructions for access to the dataset. 

Note: If a team includes groups from more than one organization, each organization on a single team must license the data. The data cannot be shared across different organizations even if they are on the same team. 

For the closed track, training data beyond the above datasets and their preselected partitions are not allowed.  
Please note that all participants in the challenge should make at least one valid submission to the closed track of Task 1 (Language Identification). 

### Open Tracks 
For the open tracks of both Task 1 and 2, participants are allowed to use all training data in the closed track listed above plus up to an additional 100 hours of any publicly available or proprietary data to train their systems. 
All training data should be thoroughly documented in the system description document at the end of the challenge, including how custom partitions of larger corpora were selected. Failure to document training data accurately will result in an invalid submission. 
For a list of suggested training corpora, please refer to Evaluation Plan. 
Pretrained models that are publicly available (e.g., wavLM and HuBERT) may also be used for the open tracks of the challenge. The name and version of the pretrained models must be documented in the system description document. Failure to document model and the version number accurately will result in an invalid submission. Proprietary pretrained models are not allowed. 

### Development Set 
The development set and evaluation set are Challenge-ready partitions of a larger dataset from the Talk Together Study which examines parent-child interactions in multilingual Singapore, and will be provided by the organizers. 

The MERLIon CCS development set is now available! Please register for the challenge and we will send you further instructions for accessing the dataset.  

Sign up for our [mailing list](https://groups.google.com/u/1/g/merlion-ccs-challenge) or join our [LinkedIn group](https://www.linkedin.com/groups/14193386/) for updates!


## Submission

Submissions of results will be made on Codalab. More information can be found on [our website](https://sites.google.com/view/merlion-ccs-challenge/submission?authuser=0).

## Planned schedule
Registrations Open : 18 Jan 2023 🎉

Registrations Close: 18 Feb 2023

Training Data Partitions Release: 25 Jan 2023 🎉

Evaluation Plan Release: 27 Jan 2023 🎉

Data Release (Development Set): 27 Jan 2023 🎉

Baseline System Release: Coming Soon 

Data Release (Evaluation Set): Coming Soon

Leaderboard Active: 1 Feb 2023

Official Evaluation Closes (Leaderboard Freeze): 28 Feb 2023

System Description Submission: 28 Feb 2023

INTERSPEECH Paper Submission Closes: 1 Mar 2023

INTERSPEECH Paper Update Submission Closes: 8 Mar 2023

Leaderboard Reopens*: 10 Mar 2023

INTERSPEECH Acceptance: 17 May 2023

*After the end of the official challenge period, the leaderboard will reopen for teams who want to continue developing their systems prior to Interspeech session (optional).


## Awards
Awards will be presented to participants/teams whose systems achieve the best performance.  Additional awards will be presented to participants/teams who report the most innovative methods as judged by the organisers.


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
Please contact Victoria at **merlion-challenge@gmail.com** or visit us at [our website](https://sites.google.com/view/merlion-ccs-challenge/) if you have any questions.
