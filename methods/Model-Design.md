# Step 3: Model Design in Edge Impulse

## Loading Audio Data
After collecting audio data, the next step is to upload the files into Edge Impulse Studio. The platform simplifies the process of designing, training, and deploying machine learning models.
- File Format: Ensure all files are in .wav format to preserve the highest audio quality.

Navigate to the Data Acquisition tab in Edge Impulse. Use the upload tool to add your categorized audio files for each target animal. Assign labels to each file to differentiate the animal categories.

## Test Split
To evaluate the model's performance accurately, the dataset was split into training and testing subsets using the split shown below:
- Training Set: 82% of the dataset (464 audio files) for training the model.
- Testing Set: 18% of the dataset (99 audio files) for testing the model's generalization ability.

![image](https://github.com/user-attachments/assets/9755921d-a53e-478d-b530-2b4b78c3c3b6)

This split ensures the model learns from the majority of the data while being tested on unseen examples for unbiased evaluation.

## Definition of Model Input
The raw audio files were processed into a standardized format for consistent input to the machine learning model.
- Each audio file was segmented into 3-second windows. For files longer than 3 seconds, a 1-second stride was applied to extract additional samples.
- A nominal sampling frequency, common for digital audio, was used across all files. This ensured uniformity and compatibility with Edge Impulse’s processing blocks.
- The raw audio signals were represented as time-series data, ready for further transformation by the processing blocks.

![image](https://github.com/user-attachments/assets/b67e2824-9dab-46b1-ba52-656c2ee1a899)


## Development of Processing Blocks
Processing blocks are critical for transforming raw audio signals into features that the learning block can use for classification. We chose to use two different processing blocks, a MFE and a Spectrogram:

### Mel Frequency Energy (MFE):
- Extracts key features from the audio signal by focusing on frequency ranges relevant to animal vocalizations.
- Emphasizes the audio characteristics most useful for classification, such as pitch and tonal variations.

MFE Settings:
![image](https://github.com/user-attachments/assets/e1c95835-73dc-4e88-9f8e-58ea795fedf9)

MFE Results:
![image](https://github.com/user-attachments/assets/1f13955b-186d-45e9-b033-7033a032a97a)
![image](https://github.com/user-attachments/assets/61f46946-6a9c-4d75-8a47-d943029f56cb)

### Spectrogram:
- Provides a detailed visualization of audio frequencies over time, highlighting changes in frequency patterns.
- The spectrogram was particularly useful for identifying dynamic features in animal sounds, such as a frog’s croak or a cat’s meow.

Spectrogram Settings:
![image](https://github.com/user-attachments/assets/0bf6a5ea-db60-4555-9f2d-e4fb334ac3d3)

Spectrogram Results:
![image](https://github.com/user-attachments/assets/04e7201b-e7f6-4940-b16f-064cc48fe2ff)
![image](https://github.com/user-attachments/assets/b23aae83-3dbb-45bb-bc63-79998ae715b5)

By combining these two processing blocks, the model could capture both static and dynamic features, ensuring robust classification.

## Definition of Classification Block
- The Classification Learning Block was used to train the model to distinguish between the four animal categories.

Input Features:
  - The processed outputs from the MFE and Spectrogram blocks (a total of 48,139 features) were fed into the learning block.
![image](https://github.com/user-attachments/assets/4d6f3355-3afc-4a1f-872f-108d6ff460b2)
    
Algorithm:
- A lightweight neural network was selected, designed to run efficiently on resource-constrained edge devices like the Syntiant TinyML board.

Output Classes:
- The learning block was configured to classify each audio sample into one of the four categories: cat, cow, dog, or frog.
![image](https://github.com/user-attachments/assets/a3e66502-495c-4519-b40f-89f42d7442dd)

This learning block forms the core of the classification system, translating processed audio data into actionable results.
