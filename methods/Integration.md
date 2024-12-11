# Step 5: Integration with Hardware

## Exporting Model Design
1. Go to the deployment tab in Edge Impulse
2. Select the Syntiant TinyML board
3. Configure the posterior parameters
4. Build the model and the .zip file should download on completion. The file contains the compiled model information and the OS-specific flash scripts 

## Establishing a Physical Connection
1. Connect the board to your computer via a data-transfer capable USB cable, it may appear as an Arduino MKRZero device
2. For projects using the IMU, ensure the SD card is inserted (not necessary for this project)
3. Install the Edge-Impulse CLI (https://docs.edgeimpulse.com/docs/tools/edge-impulse-cli/cli-installation)

## **Flashing** the Model
How to flash
