# Integrating iEEG Analysis with Neural Network Models to Decode Neural Activity and Simulate Memory Processes 

This repository contains the code and analysis for processing and modeling single-cell recordings from the human medial temporal lobe (MTL) using intracranial electroencephalography (iEEG). This is a leisure exploratory analysis that I performed on a 30-minute multi-unit recording in the **Medial Temporal Lobe** of an epileptic patient, obtained from Itzhak Fried's lab at UCLA. The dataset is authored by Rodrigo Quian Quiroga and was posted on December 9, 2019 on the Leicester University dataset webpage.

The workflow includes spike sorting, post-cluster analysis, and the integration of Recurrent Neural Networks (RNNs), Artificial Neural Networks (ANNs), and Spiking Neural Networks (SNNs).

## Dataset Information

- **Download Link:** [UCLA Data Download](https://figshare.le.ac.uk/articles/dataset/Dataset_Human_single-cell_recording/11302427/1?file=20031056)

## Workflow

The following steps were performed for the analysis:

1.  **Dataset Selection:**
    * Ensured dataset had clear metadata (electrode placement, recording duration).
    * A smaller dataset was preferred for initial exploration.

2.  **Preprocessing Comparison:**
    * **Combinato:** Used default parameters for filtering and thresholding.
    * **Python:** Customized filter parameters (bandwidth in bandpass filter) and thresholding methods (fixed vs. adaptive).
    * **Comparison:**
        * Signal-to-noise ratio (SNR).
        * Spike detection accuracy and waveform clarity.

3.  **Spike Sorting with Combinato:**
    * Evaluated the quality of spike clustering.
    * Manually refined clusters as needed.
    * Saved clustering outputs (spike times, average waveforms).

4.  **Post-Cluster Analysis with Python:**
    * Basic analysis: raster plots, firing rate histograms, cross-correlograms.
    * Advanced analysis: neural responses to specific stimuli (if applicable).

5.  **RNN/ANN Model:**
    * **Input:** Firing rates binned over a time window (50 ms).
    * **Output:** Behavioral labels or stimulus categories.
    * **Frameworks:** TensorFlow, Scikit-learn.
    * **Example task:** Classification of stimulus conditions based on neural activity.

6.  **SNN Model:**
    * **Frameworks:** Brian2.
    * **Focus:** Simulation of STDP or recurrent activity for memory encoding/recall.
    * **Approach:** Started with a basic network (two neurons) and gradually scaled up.
