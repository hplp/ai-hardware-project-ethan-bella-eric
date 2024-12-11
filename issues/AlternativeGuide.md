Prerequisite: 
Besides the Arduino IDE, please make sure that the necessary command-line tools are installed and properly configured within your system's path before moving forward.

1. Arduino CLI: https://arduino.github.io/arduino-cli/0.34/installation/Links to an external site.

(For Windows users it would be easier to download the 64-bit exe and add the file location to path)

2. Edge Impulse CLI: https://docs.edgeimpulse.com/docs/tools/edge-impulse-cli/cli-installationLinks to an external site. 

3. Install Git: https://github.com/git-guides/install-gitLinks to an external site. (It's not a must, but you'll need to run a script to install some libraries. If you can use Git in the terminal, you should be able to run this script easily.)

The Edge Impulse tutorial for hardware deployment is ineffective; instead, please follow the steps in this assignment to deploy successfully.

Part 1: Train a Keyword Spotting model for TinyML Syntiant Board
The SyntiantLinks to an external site. TinyML Board is a tiny development boardLinks to an external site. with a microphone and accelerometer, USB host microcontroller and an always-on Neural Decision Processor™, featuring ultra-low-power consumption, a fully connected neural network architecture, and fully supported by Edge Impulse.

image.png

The board consists of a SAMD21 host processor (same as TinyML Arduino Nano 33 BLE), and a Nerual Decision Processor. It enables voice and sensor applications to operate with very low power consumption, significantly outperforming traditional MCU-based systems. It offers a 20x increase in throughput and a 200x improvement in system efficiency.

Please finish the first part of the assignment before you head to Rice 240 for the deployment.

The training process will be similar to the previous assignment but with different processing blocks used in the impulse design. Please follow this tutorialLinks to an external site. to train a model with at least two keywords other than the original 'go' and 'stop'.  (Try to have similar amount of training data as before to compare Syntiant with Arduino Nano 33 BLE)
For the deployment section in Edge Impulse, please follow this order and build two zip files
Click the deployment option and select Syntiant NDP101 library
Select posterior find parameters, check all the keywords you want and click find parameters.
Build the zip file (project-name-ndp-lib.zip)
Click the deployment option again and select Syntiant TinyML, click build (project-name-ndp.zip)
Extract the zip files, now we have two folders: project-name-ndp-lib and project-name-ndp
Clone the Syntiant firmware: Github RepoLinks to an external site.
Please use the provided repo as the original Syntiant firmware repo is ineffective(for Windows users)... 
If you download the repo instead of git clone make sure you rename the directory back to firmware-syntiant-tinyml.
Then we need to install the libraries, for Windows users simply double-click the update_libraries_windows.bat, for Mac/Linux users please follow the instructions in README.
Copy the header files from project-name-ndp-lib/model-parameters to firmware-syntiant-tinyml/model-parameters (overwrite)
In model_variables.h, comment lines 29-30,  lines 52-59
(#include "edge-impulse-sdk/classifier/ei_model_types.h"

#include "edge-impulse-sdk/classifier/inferencing_engines/engines.h"

const ei_model_performance_calibration_t ei_calibration = {...})

Open firmware-syntiant-tinyml/firmware-syntiant-tinyml.ino in Arudino IDE
Modify the on_classification_changed function to toggle LED for different keywords, here is an example:
void on_classification_changed(const char *event, float confidence, float anomaly_score) {
    // here you can write application code, e.g. to toggle LEDs based on keywords
    if (strcmp(event, "blue") == 0) {
        // Toggle LED
        digitalWrite(LED_BLUE, HIGH);
        digitalWrite(LED_GREEN, LOW);
        digitalWrite(LED_RED, LOW);
    }
    if (strcmp(event, "red") == 0) {
        // Toggle LED
        digitalWrite(LED_RED, HIGH);
        digitalWrite(LED_BLUE, LOW);
        digitalWrite(LED_GREEN, LOW);
    }
}
In Arduino IDE, select Arduino MKRZERO (no need to connect the board yet)
Click sketch=>export compiled binary
Copy the two generated bin files from firmware-syntiant-tinyml/build to project-name-ndp, and rename the files to firmware.ino.bin and firmware.ino.with_bootloader.bin
Copy ei_model.bin and ei_model.synpkg from project-name-ndp-lib to project-name-ndp
Deliverables: 
A screenshot of the accuracy after you train the model. 
Question: 
In a keyword-spotting LED control system, what tasks are typically performed by the host processor, and what tasks are handled by the NPU? Why are microphone and accelerometer sensors connected to the NPU in this system? (More about NPULinks to an external site.)
Part 2: Deployment
We have two Syntiant boards in a box labeled "AI HW" in Rice 240, please finish the deployment there. 

image.png

Please use the sign-up formLinks to an external site. to pick your preferred time.

After finishing Part 1, connect the board to your laptop and run the corresponding script for your OS (e.g. for win users run project-name-ndp/flash_windows.bat) to deploy! (If you observe an error saying it can't find the device at COMx, just try restarting and running the script again.)

This is currently the only method I've tested to guarantee a successful deployment. If you come across a better or more straightforward approach, please do share it with us!

Deliverables: 
Questions:
Share your experience with deploying the model to your device. Were there any technical difficulties or interesting observations during the process? How does the Syntiant board perform the task compared to the Arduino board? 
Please record a video showcasing the keyword-spotting operations with LED control and provide the link to your video in your submission. You could still open Arduino IDE or Putty to observe results from Serial port. 
You should have at least one functioning keyword (capable of turning on the LED). If you encounter issues with certain keywords not working on the board, please provide an explanation for the potential reasons.

Troubleshooting
from board tutorial here https://www.syntiant.com/tinymlLinks to an external site. 

If you get an error "cannot find the board at COMx" when you run the flash script, please follow these steps to fix the issues:
Use this command to check the board's serial port: arduino-cli board list. Usually, two COM ports will show up but only one of them is correct. The flash script used the wrong port so we are going to fix that. (Let's say you find two serial ports of the board, COM8 and COM9, and the flash_script is using COM8 and couldn't find the board. The correct one would be COM9)
Open the script in a text editor and search for "CALL", you should find two lines that start with "CALL". Change the %COM_PORT% in these two lines to the correct port (e.g. COM9). Here's an example: 
(1st call function) CALL arduino-cli upload -p COM9 --fqbn arduino:samd:mkrzero  --input-file firmware.ino.bin

(2nd call function) CALL %NDP_CMD% -s COM9 -Q -a 0x00 -w %BIN_FILE% -v %BIN_FILE%

Save the script and run it again. 
  2.  (Please do not do this! If you are facing such an issue email the TA! ) If you get series of error messages like 0x000000: read 0x04 != expected 0x01, please follow these steps to fix the issues:

For Windows users:
First download and install Putty here: https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.htmlLinks to an external site. 
Open Putty, select the correct serial port and set baud rate to 115200, click openimage.png
Type :F in the window; you will see a message indicating that copying SD to flash has been completed. Note that :F will not be shown in the Tera Term window
Now try flashing the Syntiant TinyML board again. 
