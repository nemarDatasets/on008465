[![DOI](https://img.shields.io/badge/DOI-10.82901%2Fnemar.on008465-blue)](https://doi.org/10.82901/nemar.on008465)

NeuralEcho MACS high-density communication-related EEG dataset
================================================================

Overview
--------
This dataset contains high-density EEG recordings from 30 healthy,
right-handed, native Chinese-speaking adults. Participants performed imagined
and executed vocalization and writing tasks involving four Chinese strokes
(heng, shu, pie and na) and four English letters (a, b, c and d).

Experimental design
-------------------
Each participant completed eight runs of 64 trials. The factorial design
crossed task mode (motor imagery or motor execution), action (read/speak or
write), script (Chinese or English) and token identity, yielding 32 event-coded
conditions and 15,360 task events.

Data organization
-----------------
The BIDS root contains BrainVision EEG data and metadata. Proprietary Neuroscan
source recordings are under sourcedata/. EEGLAB preprocessing derivatives and
subject-level machine-learning exports are under derivatives/. Those two
directories are intentionally listed in .bidsignore because they are shared
for reuse but are not part of raw-BIDS validation.

Electrode coordinates and reference
-----------------------------------
The electrodes.tsv files contain a shared 127-channel cap-layout template
derived from Code/127cn.csv. Coordinates are expressed in millimetres using
the EEGLAB ALS convention: positive x points anteriorly, positive y points to
the participant's left and positive z points superiorly. These are template
coordinates repeated across participants, not participant-specific digitized
positions. Trigger is an acquisition channel and is therefore excluded from
electrodes.tsv. The continuous recordings used the bilateral mastoid
electrodes M1 and M2 as the EEG reference.

Authors and contributors
------------------------
Huang Jinfeng; Kangqiao Liu; Li Zhongjie; Jin Yongdong.
Data were collected and curated collaboratively by Tianjin University,
Shenzhen University and NeuralEcho Technology Co., Ltd.

References
----------
Appelhoff, S. et al. MNE-BIDS: Organizing electrophysiological data into the
BIDS format and facilitating their analysis. Journal of Open Source Software
4, 1896 (2019). https://doi.org/10.21105/joss.01896

Pernet, C. R. et al. EEG-BIDS, an extension to the brain imaging data structure
for electroencephalography. Scientific Data 6, 103 (2019).
https://doi.org/10.1038/s41597-019-0104-8
