# Machine-Learning-Models-for-EEG-based-Emotion-Recognition

**Authors**: [Your Name], et al.

## Abstract

The accurate recognition of human emotions is crucial for enhancing human-computer interaction and supporting mental health evaluations. Existing methods such as facial recognition and voice analysis often encounter challenges regarding accuracy and reliability. **Emo-Sense** leverages electroencephalogram (EEG) technology to offer an innovative, non-invasive approach for emotion recognition by analyzing brainwave patterns associated with different emotional states. Using machine learning techniques, this research aims to improve the accuracy and efficiency of emotion detection and introduces a user-friendly web application for real-time emotion assessment.

## 1. Introduction

Human emotions are complex and influence various aspects of daily life, including decision-making and interpersonal interactions. Traditional emotion recognition methods often fall short in accuracy and can be intrusive or biased by personal control. EEG presents a viable alternative due to its direct measurement of brain activity, providing a closer link to subconscious emotional states. This research develops **Emo-Sense**, an EEG-based tool that applies advanced signal processing and machine learning algorithms to classify emotions accurately.

## 2. Methodology

### 2.1 Dataset Collection

The **SJTU Emotion EEG Dataset for Four Emotions (SEED-IV)** was used for emotion recognition. This dataset is a subset of the **SEED** dataset provided by the Center for Brain-like Computing and Machine Intelligence, Shanghai Jiao Tong University. The data were collected across three sessions, with each session containing EEG signals recorded from 15 subjects during emotional stimulus tasks (film clips). The emotions represented in the dataset are:

- **Neutral** (label 0)
- **Sad** (label 1)
- **Fear** (label 2)
- **Happy** (label 3)

The labels for each session are as follows:

- **Session 1**: `[1,2,3,0,2,0,0,1,0,1,2,1,1,1,2,3,2,2,3,3,0,3,0,3]`
- **Session 2**: `[2,1,3,0,0,2,0,2,3,3,2,3,2,0,1,1,2,1,0,3,0,1,3,1]`
- **Session 3**: `[1,2,2,1,3,3,3,1,1,2,1,0,2,3,3,0,2,3,0,0,2,0,1,0]`

The **sliding time window** used for feature extraction was 4 seconds, and the EEG signals were processed to extract relevant features for emotion classification.

For more details on the dataset, visit: [SEED Dataset](http://bcmi.sjtu.edu.cn/~seed/)

### 2.2 Pre-processing

Preprocessing steps included:

- Downsampling the raw EEG data to 200 Hz to reduce computational load.
- Applying a bandpass filter from 1 Hz to 75 Hz to eliminate noise outside the significant frequency range.
- Using **Independent Component Analysis (ICA)** to isolate and remove artifacts caused by eye movements and muscle contractions.

### 2.3 Feature Extraction

From the preprocessed EEG signals, features were extracted, focusing on:

- **Power Spectral Density (PSD)**: Quantifying the power of different frequency bands.
- **Differential Entropy (DE)**: Providing a statistical measure that describes the randomness or complexity within the EEG signals across five bands: delta, theta, alpha, beta, and gamma.

## 3. System Development

### 3.1 Web Application

The **Emo-Sense** web application allows users to upload EEG data files. It processes this data to classify and display the corresponding emotional state. The application features a clean, intuitive interface with real-time data visualization, including graphs of EEG signals and emotion classification results.

### 3.2 Machine Learning Models

We evaluated multiple algorithms, with a focus on:

- **Support Vector Machines (SVM)**: For their effectiveness in high-dimensional spaces.
- **Convolutional Neural Networks (CNN)**: Which are adept at capturing spatial relationships in multidimensional data.
- **K-Nearest Neighbors (KNN)**: A non-parametric method used for classification based on the proximity of the data points.

Models were trained on 70% of the dataset and tested on the remaining 30% to evaluate their performance.

## 4. Results

### 4.1 Model Performance

- The **SVM** model achieved an accuracy of 55%, while the **CNN** model outperformed with an accuracy of approximately 65%. The **KNN** model also showed promising results with an accuracy of 60%, further validating the robustness of the emotion recognition system.

### 4.2 Application Usability

Preliminary testing of the web application showed that users could easily navigate and utilize the tool for both individual and research purposes. Feedback indicated that the real-time processing and visualization capabilities were particularly beneficial.

## 5. Discussion

This research highlights the potential of EEG-based approaches in capturing genuine emotional states, surpassing the capabilities of conventional methods. The integration of machine learning with EEG data analysis has proven to be a robust approach to emotion recognition, with significant implications for adaptive interfaces and clinical practices.

## 6. Conclusion and Future Work

**Emo-Sense** demonstrates a significant step forward in emotion recognition technology. Future enhancements will focus on expanding the dataset with more diverse demographic coverage, improving model accuracy with deeper neural networks, and integrating multimodal data. Real-time monitoring and adaptive response systems in health care and user interface design are prospective applications.

## 7. References

- Wei-Long Zheng, Wei Liu, Yifei Lu, Bao-Liang Lu, and Andrzej Cichocki. **EmotionMeter: A Multimodal Framework for Recognizing Human Emotions**. IEEE Transactions on Cybernetics, 2018.
- [SEED Dataset](http://bcmi.sjtu.edu.cn/~seed/)
