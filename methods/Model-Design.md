# Step 3: Model Design in Edge Impulse

## Loading Audio Data
After collecting audio data, the next step is to upload the files into Edge Impulse Studio. The platform simplifies the process of designing, training, and deploying machine learning models.
- File Format: Ensure all files are in .wav format to preserve the highest audio quality.
- Navigate to the Data Acquisition tab in Edge Impulse. Use the upload tool to add your categorized audio files for each target animal. Assign labels to each file to differentiate the animal categories.

## Test Split
To evaluate the model's performance accurately, the dataset was split into training and testing subsets using the split shown below:
- Training Set: 82% of the dataset (464 audio files) for training the model.
- Testing Set: 18% of the dataset (99 audio files) for testing the model's generalization ability.
- ![image](https://github.com/user-attachments/assets/9755921d-a53e-478d-b530-2b4b78c3c3b6)

This split ensures the model learns from the majority of the data while being tested on unseen examples for unbiased evaluation.

## Definition of Model Input
How to input

## Development of Processing Blocks
What are processing blocks
Which ones to (we) use

## Definition of Classification Block
How to
