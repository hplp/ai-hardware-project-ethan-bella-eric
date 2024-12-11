# Step 4: Model Training and Testing

## Model Training Parameters
To train the model effectively, we configured the following parameters in Edge Impulse Studio:
- Epochs: The model was trained for 50 epochs, a sufficient number to allow the model to converge without overfitting.
- Learning Rate: We used a learning rate of 0.0005 to allow the model to learn slowely and stablely over the 50 epochs. 
- Batch Size: Default values were used to ensure efficient computation while accommodating the dataset size.
- ![image](https://github.com/user-attachments/assets/84b7dc18-7b9e-4906-bc47-4752767b0095)

## Testing the Model
Once training was completed, the model was tested on the reserved testing subset to evaluate its generalization ability.
- Testing Methodology:
  - Testing data consisted of 99 audio files, 18% of the dataset.
  - Edge Impulse automatically applied the trained model to unseen test samples.
    
- Validation Process:
  - Results were reviewed to identify misclassified samples and patterns in classification errors.
  - The confusion matrix was analyzed to determine how well the model distinguished between classes.
    
- Testing Workflow
  - Navigate to the Model Testing tab in Edge Impulse Studio.
  - Select the testing dataset and verify preprocessing settings.
  - Run the testing process and observe the model's predictions for each class.


