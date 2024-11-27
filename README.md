# AI Hardware Project Proposal
### ECE 4501 - Fall 2024

## Team Name: 
Who's Calling?

## Team Members:
- Ethan Jenkins
- Bella Heintges
- Eric Sheetz

## Project Title:
Bioacoustic Animal Identification

## Project Description:
We plan to design a compact system capable of identifying local animal species by recognizing their vocal calls by leveraging the power of TinyML. This system will be deployed on a microcontroller specifically chosen for its capability to record and process audio data in real-time. By analyzing the audio inputs, our system will be able to detect and classify animal sounds, allowing for efficient and on-site wildlife monitoring.

## Key Objectives:
- Determine ideal hardware, along with an optimized ML network structure. 
- Determine sufficient classification categories to further train the network. 
- Alongside the trained network, use the deployed hardware to correctly identify animals based on their calls.
- Design this system such that it can be utilized hands-on, in various locations.

## Technology Stack:
- Platform: TinyML 
- Software Tools: C/C++, Edge Impulse
- Hardware Tools: Syntiant TinyML

## Expected Outcomes:
- By the end of the semester we will have a working model that can listen to an animal sound and correctly identify that sound with at least 80% accuracy.
- We will have a model that has been trained to correctly identify these sounds for at least 5 common farm animals.

## Timeline:
 - By 11/8: Select hardware
 - By 11/15: Choose classifications
 - By 11/22: Choose network structure
 - By 11/29: Have network trained
 - By 12/6: Successful test of deployed network



# Milestone 1:
*Due to hardware challenges with the Syntiant chip, we have not yet deployed our model on the embedded system. However, the model can still be trained and tested using Edge Impulse software. Additionally, we have started planning future classification parameters to achieve higher training accuracy in subsequent iterations.*

## Timeline Update:
- Hardware selected: Syntiant TinyML, using Edge Impulse (C/C++)
- Classifications chosen: Selected 5 animals for initial testing and training {sheep, cow, pig, dog, rooster}
- Data acquired: Testing and training datasets gathered for the 5 selected animals
- Training started: Using *Edge Impulse*, have began training our model using Datasets
- Further testing: Compiled 4 other animal call audio files (.wav) to use during testing {lion, monkey, frog, bird}

## Data Aquisition:
*Preparation of the raw audio data that has been collected and organized for model training, along with the corresponding labels for each animal sound.*

![image](https://github.com/user-attachments/assets/0d94ba61-5a99-4302-973c-db4e6b0c4040)

We have collected 14 minutes and 53 seconds of relevant audio data for use in the testing and training process. These files vary in length, and so far we have compiled 155 files for the training dataset, with the test dataset containing 43 files. Each sample has been labeled according to its classification, corresponding to one of the five selected animals. Currently, our model yields a train/test split of 78%/22%.

## Impulse Design:
*Taking the raw data, impulse processes the signal to extract features and classify new data.*

![image](https://github.com/user-attachments/assets/272dc8c8-48f1-49b8-8c88-287356465e72)

We are in the process of visualizing the processed audio data in three stages: (1) time series data, (2) spectrogram, and (3) classification. The audio is first segmented into 1000ms windows with a 500ms stride, then converted into a spectrogram to extract frequency features. Finally, the classifier uses the spectrogram as input to identify and classify the animal sounds into one of the five selected animals.

## Spectogram Layout:
*Visualizing the audio data, transforming the raw sound waves into frequency-time patterns, helping the model identify key features of the animal calls.*

![image](https://github.com/user-attachments/assets/3d01fa20-b21e-4c97-aee7-34042e5b23cc)

We have configured the spectrogram to use a frame length of 0.5 seconds, with a stride of 0.01 seconds. The FFT (Fast Fourier Transform) is computed over a series of 256 frames, capturing the frequency components of the audio. After processing, we can view a heat-map of the DSP (Digital Signal Processing) results for each spectrogram, along with the extracted features from the raw audio data, which are crucial for our classification process.

## Next Steps:
(1) Expanding the Dataset: Increasing the number of audio samples in both the training and test datasets will help achieve a more balanced split and improve the model's generalization. Ensuring that the dataset includes a variety of sound recordings for each animal will provide more robust data for training and help avoid overfitting.

(2) Revising the Impulse Design: We plan to revist the impulse design, particularly the input features used for classification. Exploring additional preprocessing techniques, such as filtering or normalization, may enhance the quality of the features extracted from the audio and contribute to better classification performance.

(3) Adjusting Spectrogram Settings: We will experiment with different frame lengths and stride values to better capture the frequency characteristics of animal sounds. By fine-tuning these settings, we can optimize the resolution of the spectrogram and potentially improve the model's ability to distinguish between animal calls.

(4) Integrating Hardware with EdgeImpulse: Necessary to configure the Syntiant TinyML hardware to process and classify animal vocal calls using the trained model directly on the embedded device. Leveraging Syntiant's specialized AI accelerator, we will work to achieve real-time, efficient audio processing in a compact, on-site form. 


