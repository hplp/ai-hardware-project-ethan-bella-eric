# Step 2: Data Acquisition and Research

## Research:
- The first step in building a robust bioacoustic classification system is to identify the specific animals you want to classify. For this project, we focused on four animal categories: cats, cows, dogs, and frogs. These animals were chosen based on their distinct sound patterns and availability of audio data.

## Data Aquisition
The second step is collecting high-quality audio files for each animal. A larger dataset with diverse examples is crucial for improving the model's accuracy. Key considerations include:
- File Format: We prioritized .wav files for their uncompressed and lossless nature, ensuring maximum sound quality for accurate feature extraction.
- Source: Public datasets are an invaluable resource. We used Kaggle.com, a leading platform for datasets and machine learning projects. Kaggle provided access to well-labeled datasets containing audio files of the animals we wanted to classify, shown below:
  
- ![image](https://github.com/user-attachments/assets/e3f4cb41-d31b-4d79-85b1-039c448acf60)

## Audio File Collection
Through Kaggle, we downloaded datasets containing sounds for each of our target animals:
- Cats: Audio samples of meows, purrs, and other cat sounds.
- Cows: Samples of moos and similar vocalizations.
- Dogs: Audio files capturing barks, growls, and whines.
- Frogs: Croaks and other frog-specific sounds.
- These audio files were organized into folders based on the animal category and uploaded to Edge Impulse Studio for preprocessing and training.
