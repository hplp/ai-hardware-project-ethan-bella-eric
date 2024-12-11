# Step 6: Deployment and Live Demo

## Deployment Process
After the model is flashed to the Syntiant TinyML board, connect using the edge-impulse-daemon which uses a serial connection to the board. The edge-impulse-data-forwarder can also be used to send the data to the Edge Impulse software for further model development. If you are having connectivity or board detection issues but you managed to flash the model, you can specify the COM port to which the daemon serial script will connect with. MORE HERE??????????????

## Expected Demonstration Results
What the demo should look like, what inputs, results, etc. expected (bc we didnt pass step before)
^^^ delete ^^^

After the model is flashed on the board and the serial data connection is established for monitoring, the model will continuously run. Each Inference is based on a "live" 1-second audio sample. You can monitor the classification the model gives for each inference using the serial connection, or program the board LEDs for visual signaling. Deployed testing can be executed, whether using digital audio recordings or live animals. The data-forwarder is very useful for testing as you can automatically aggregate the results in the Edge Impulse software. MORE HERE????????
