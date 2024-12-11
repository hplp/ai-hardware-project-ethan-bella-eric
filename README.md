#### Final Project: AI Hardware (ECE 4501)

# ShazAnimal: Bioacoustic Animal Identifier
#### Project Group #2: Who's Calling?
#### Contributors: Ethan Jenkins (thw2nv), Eric Sheetz (fsm6wv), Bella Heintges (xvj5pd)
  
### Background
*Have you ever heard an animal sound and wondered what made it?*

The motivation for this project is to demonstrate the feasibility of deploying bioacoustic identification tools that are automated, seamless, and accessible for a wide range of users. By leveraging TinyML, the system aims to deliver efficient processing, showcasing the power of machine learning in resource-constrained environments. This enables the on-site application of audio recognition algorithms, making it a practical solution for diverse use cases. The system has potential applications in education, serving as a tool to teach children elementary concepts about nature and technology, as well as in ecological research, providing a sustainable and practical method for wildlife monitoring.
  
## Objectives
- Develop a machine learning algorithm capable of processing and identifying the animal responsible for a given audio input
- Train the model such that it is capable of classifying the sounds of 4 common animals (dog, cat, frog, cow)
- Develop a trained model able of classifying with at least an 80% accuracy
- Integrate the program with the Syntiant TinyML board, utilizing the built-in microphone, so the system can be used on-site
  
## Necessary Technology
The hardware foundation for this project includes the Syntiant TinyML board, which integrates the NDP101 Neural Decision Processor (NDP). The NDP101 is designed for efficient edge AI applications, leveraging compute-in-memory technology to achieve high parallelism and efficiency. It supports up to 589,000 parameters and delivers low-power, fast inferences on a compact 5mm x 5mm chip, making it ideal for resource-constrained environments. Additionally, the project requires a Linux or Linux-based system enabled device to host the necessary software.

On the software side, the project utilizes tools such as Git for version control, edge-impulse-cli for deploying machine learning models, and arduino-cli for interfacing with the microcontroller. Edge Impulse Studio plays a central role in managing data, training models, and deploying them to the Syntiant NDP101. This robust toolchain ensures seamless integration of machine learning workflows for real-time bioacoustic signal processing.

Below outlines the necessary technology to mimic our system development and deployment:

Hardware:
- Syntiant TinyML Board
- Linux, or Linux-based system enabled device

Software:
- Linux, or Linux-based system
- Package tools (git, edge-impulse-cli, arduino-cli)
- Edge Impulse Studio

## Methodology
To design, train, and deploy the ShazAnimal bioacoustic identification system, we followed a systematic approach that ensures reproducibility and scalability. Each step in the process builds on the previous, guiding the project from data collection to real-world deployment. Below, we outline the key steps in our methodology with links to detailed explanations for each:

| How-To Guide: |
|:-------------------|
| Step 1:  [Aggregation of Tools](methods/Tools.md) |
| Step 2:  [Data Acquisition and Research](methods/Data-Acquisition.md) |
| Step 3:  [Model Design using Edge Impulse](methods/Model-Design.md) |
| Step 4:  [Model Training and Testing](methods/Training-and-Testing.md) |
| Step 5:  [Hardware Integration](methods/Integration.md) |
| Step 6:  [Deployment and Live Demo](methods/Deployment.md) |

## Step 1: Aggregation of Tools
Before beginning the project, it will be necessary to set up various accounts, download the required tools, and prepare both the hardware and software environments. These steps ensure a smooth workflow for developing, training, and deploying the ShazAnimal system.

### (1) Create respective accounts:
#### Edge Impulse
Edge Impulse is a leading platform for developing, deploying, and optimizing machine learning (ML) models specifically designed for edge devices. It provides tools to simplify the creation of ML models for real-world applications, such as audio, image, and sensor data processing, enabling low-latency and energy-efficient solutions.

Visit Edge Impulse to create a free account. This platform will be used to design, train, and deploy the machine learning model.

Sign-Up Link: https://studio.edgeimpulse.com/signup

Getting Started: https://www.edgeimpulse.com/blog/getting-started-with-edge-impulse/
    
#### GitHub
GitHub is a web-based platform that provides version control, collaboration, and project management tools for developers. It is built on top of Git, a widely-used distributed version control system, and offers additional features to facilitate software development, team collaboration, and project organization.

If you don’t already have one, create a GitHub account to manage your project repository and track changes.

Sign-Up Link: https://github.com/join

How-To Use: https://docs.github.com/en/get-started/start-your-journey/hello-world

### (2) Prepare and download software:
#### Linux or Linux-Based System
Linux is an open-source operating system kernel that forms the foundation for various operating systems, known as Linux distributions (e.g., Ubuntu, Fedora, Debian). A Linux-based system uses this kernel to provide a flexible, stable, and secure environment for running applications and managing hardware, often preferred for servers, development, and embedded systems.

Ensure you have access to a Linux environment (native or virtual). A Linux-based system simplifies the use of command-line tools is required for this project.

#### Git
Git is a distributed version control system that allows multiple developers to track changes, collaborate on, and manage the history of software projects. It enables users to work on different parts of a project simultaneously, merge changes, and revert to previous versions, ensuring a robust workflow and minimizing the risk of data loss or conflicts.

Install Git to clone and manage your GitHub repository. Instructions can be found here.
    
#### Edge Impulse CLI
The Edge Impulse CLI (Command Line Interface) is a tool that allows developers to interact with the Edge Impulse platform directly from the terminal. It enables users to streamline tasks such as data collection, model training, and deployment to edge devices without needing to use the web-based interface. The CLI facilitates the creation and management of machine learning projects, uploading sensor data, generating models, and deploying those models to embedded devices, all through command-line commands. This tool is particularly useful for automating workflows, integrating Edge Impulse with other development tools, and working in resource-constrained environments where GUI access may be limited.

Download the Edge Impulse CLI by following the instructions in the Edge Impulse documentation. This tool connects your local development environment to the Edge Impulse platform.

How-To Install: https://docs.edgeimpulse.com/docs/tools/edge-impulse-cli/cli-installation

#### Arduino CLI
The Arduino CLI (Command Line Interface) is a tool that allows developers to interact with the Arduino ecosystem via the command line, rather than using the graphical Arduino IDE. It provides functionality for compiling and uploading Arduino sketches (programs) to Arduino boards, managing libraries and board definitions, and performing other tasks related to the development and deployment of Arduino-based projects. The Arduino CLI is particularly useful for automating workflows, integrating with other tools, or working in environments where a graphical user interface is not feasible, such as in continuous integration (CI) systems or embedded development setups.

Install the Arduino CLI to interface with the TinyML board. Instructions are available on the Arduino CLI setup page.

How-To Install: https://arduino.github.io/arduino-cli/0.24/installation/

### (3) Setup hardware:
#### Syntiant TinyML Board
Obtain a Syntiant TinyML NDP101 board, which will serve as the deployment hardware for the trained model. Follow the manufacturer’s instructions for setting up and connecting the board.

![image](https://github.com/user-attachments/assets/ff92aed9-8043-4ab8-a8ff-2dbeace2d171)

#### USB Cable
Use a compatible USB cable to connect the board to your Linux system for data transfer and testing.
    
#### Linux-Enabled Device
Ensure that your Linux-enabled computer or virtual machine is prepared to run the necessary software and interface with the TinyML board.

### (4) Configure the enviornment:
#### Install Python
Ensure Python is installed and configure a virtual environment for running scripts.

Link to Download: https://www.python.org/downloads/
    
#### Required Libraries
Install any necessary Python packages (e.g., numpy, matplotlib) as specified in the requirements.txt file included in the repository.

*By completing these steps, you’ll have all the tools and accounts needed to proceed with data acquisition, model design, and hardware integration. This setup forms the foundation for the entire project.*

## Step 2: Data Acquisition and Research

#### Research:
- The first step in building a robust bioacoustic classification system is to identify the specific animals you want to classify. For this project, we focused on four animal categories: cats, cows, dogs, and frogs. These animals were chosen based on their distinct sound patterns and availability of audio data.

#### Data Aquisition
The second step is collecting high-quality audio files for each animal. A larger dataset with diverse examples is crucial for improving the model's accuracy. Key considerations include:
- File Format: We prioritized .wav files for their uncompressed and lossless nature, ensuring maximum sound quality for accurate feature extraction.
- Source: Public datasets are an invaluable resource. We used Kaggle.com, a leading platform for datasets and machine learning projects. Kaggle provided access to well-labeled datasets containing audio files of the animals we wanted to classify, shown below:
  
- ![image](https://github.com/user-attachments/assets/e3f4cb41-d31b-4d79-85b1-039c448acf60)

#### Audio File Collection
Through Kaggle, we downloaded datasets containing sounds for each of our target animals:
- Cats: Audio samples of meows, purrs, and other cat sounds.
- Cows: Samples of moos and similar vocalizations.
- Dogs: Audio files capturing barks, growls, and whines.
- Frogs: Croaks and other frog-specific sounds.
- These audio files were organized into folders based on the animal category and uploaded to Edge Impulse Studio for preprocessing and training.

#### Importance of Research and Data Quality
The selection of high-quality audio files and the use of a reputable source like Kaggle ensure that our dataset is robust and capable of supporting accurate classification. Future improvements may involve sourcing additional datasets or recording custom audio to expand the diversity of the samples.

## Step 3: Model Design in Edge Impulse

### Loading Audio Data
After collecting audio data, the next step is to upload the files into Edge Impulse Studio. The platform simplifies the process of designing, training, and deploying machine learning models.
- File Format: Ensure all files are in .wav format to preserve the highest audio quality.
- Navigate to the Data Acquisition tab in Edge Impulse. Use the upload tool to add your categorized audio files for each target animal. Assign labels to each file to differentiate the animal categories.

### Test Split
To evaluate the model's performance accurately, the dataset was split into training and testing subsets using the split shown below:
- Training Set: 82% of the dataset (464 audio files) for training the model.
- Testing Set: 18% of the dataset (99 audio files) for testing the model's generalization ability.
- ![image](https://github.com/user-attachments/assets/9755921d-a53e-478d-b530-2b4b78c3c3b6)

This split ensures the model learns from the majority of the data while being tested on unseen examples for unbiased evaluation.

### Definition of Model Input
The raw audio files were processed into a standardized format for consistent input to the machine learning model.
- Each audio file was segmented into 3-second windows. For files longer than 3 seconds, a 1-second stride was applied to extract additional samples.
- A nominal sampling frequency, common for digital audio, was used across all files. This ensured uniformity and compatibility with Edge Impulse’s processing blocks.
- The raw audio signals were represented as time-series data, ready for further transformation by the processing blocks.
- ![image](https://github.com/user-attachments/assets/b67e2824-9dab-46b1-ba52-656c2ee1a899)


### Development of Processing Blocks
Processing blocks are critical for transforming raw audio signals into features that the learning block can use for classification. We chose to use two different processing blocks, a MFE and a Spectrogram:
- Mel Frequency Energy (MFE):
  - Extracts key features from the audio signal by focusing on frequency ranges relevant to animal vocalizations.
  - Emphasizes the audio characteristics most useful for classification, such as pitch and tonal variations.
  - MFE Settings:
  - ![image](https://github.com/user-attachments/assets/e1c95835-73dc-4e88-9f8e-58ea795fedf9)
  - MFE Results:
  - ![image](https://github.com/user-attachments/assets/1f13955b-186d-45e9-b033-7033a032a97a)
  - ![image](https://github.com/user-attachments/assets/61f46946-6a9c-4d75-8a47-d943029f56cb)

- Spectrogram:
  - Provides a detailed visualization of audio frequencies over time, highlighting changes in frequency patterns.
  - The spectrogram was particularly useful for identifying dynamic features in animal sounds, such as a frog’s croak or a cat’s meow.
  - Spectrogram Settings:
  - ![image](https://github.com/user-attachments/assets/0bf6a5ea-db60-4555-9f2d-e4fb334ac3d3)
  - Spectrogram Results:
  - ![image](https://github.com/user-attachments/assets/04e7201b-e7f6-4940-b16f-064cc48fe2ff)
  - ![image](https://github.com/user-attachments/assets/b23aae83-3dbb-45bb-bc63-79998ae715b5)

By combining these two processing blocks, the model could capture both static and dynamic features, ensuring robust classification.

### Definition of Classification Block
The Classification Learning Block was used to train the model to distinguish between the four animal categories.
- Input Features:
  - The processed outputs from the MFE and Spectrogram blocks (a total of 48,139 features) were fed into the learning block.
  - ![image](https://github.com/user-attachments/assets/4d6f3355-3afc-4a1f-872f-108d6ff460b2)
    
- Algorithm:
  - A lightweight neural network was selected, designed to run efficiently on resource-constrained edge devices like the Syntiant TinyML board.

- Output Classes:
  - The learning block was configured to classify each audio sample into one of the four categories: cat, cow, dog, or frog.
  - ![image](https://github.com/user-attachments/assets/a3e66502-495c-4519-b40f-89f42d7442dd)

This learning block forms the core of the classification system, translating processed audio data into actionable results.

## Step 4: Model Training and Testing

### Model Training Parameters
To train the model effectively, we configured the following parameters in Edge Impulse Studio:
- Epochs: The model was trained for 50 epochs, a sufficient number to allow the model to converge without overfitting.
- Learning Rate: We used a learning rate of 0.0005 to allow the model to learn slowely and stablely over the 50 epochs. 
- Batch Size: Default values were used to ensure efficient computation while accommodating the dataset size.
- ![image](https://github.com/user-attachments/assets/84b7dc18-7b9e-4906-bc47-4752767b0095)

### Testing the Model
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

## Step 5: Integration with Hardware

### Exporting Model Design
1. Go to the deployment tab in the Edge Impulse software
2. Select the Syntiant TinyML board
3. Configure the posterior parameters
4. Build the model; the .zip file should download on completion. The file contains the compiled model information and the OS-specific flash scripts (Linux works best)

### Establishing a Physical Connection and **Flashing** the Model
1. Connect the board to your computer via a data-transfer capable USB cable, it may appear as an Arduino MKRZero device
2. For projects using the IMU, ensure the SD card is inserted (not necessary for this project)
3. Install the Arduino CLI (https://arduino.github.io/arduino-cli/0.24/installation/). A version older than 1.0.0 is necessary to match with the outdated Edge-Impulse CLI
4. Git is also required; the newest version will suffice. Remember to add these tools to the PATH or the necessary folder for Linux OS to ensure they are available. 
5. Install the Edge-Impulse CLI (https://docs.edgeimpulse.com/docs/tools/edge-impulse-cli/cli-installation)
6. Confirm the board is connected. To see connected boards, run _arduino-cli board list_
7. Run the OS-appropriate flash script.

## Step 6: Deployment and Live Demo

### Deployment Process
After the model is flashed to the Syntiant TinyML board, connect using the edge-impulse-daemon which uses a serial connection to the board. The edge-impulse-data-forwarder can also be used to send the data to the Edge Impulse software for further model development. If you are having connectivity or board detection issues but you managed to flash the model, you can specify the COM port to which the daemon serial script will connect with. There may be additional approaches online which utilize the Arduino IDE if you have trouble with both of the guides provided in the integration issues document. 

### Expected Demonstration Results
After the model is flashed on the board and the serial data connection is established for monitoring / data collection, the model will continuously run. Each inference is based on a "live" 3-second audio sample. You can monitor the classification the model gives for each inference using the serial connection, or program the board LEDs for visual signaling. Deployed testing can be executed, whether using digital audio recordings or live animals. The data-forwarder is very useful for testing as you can automatically aggregate the audio samples and classification results in the Edge Impulse software. If the animal noise is coming from a known species, then the accuracy of the deployed model can be calculated. The accuracy of our model was relatively high for the testing done through the Edge Impulse software, so deployed testing would be expected to yield a similar level of accuracy. 


## Results and Discussion

### Model Performance and Results
The model's performance was evaluated using standard machine learning metrics:
- Performance Metrics
  - Training Accuracy: Achieved 86.4%, exceeding the target of 80%.
  - Training Loss: Minimal loss of 0.48, indicating strong convergence.
  - Testing Accuracy: Comparable to training results, confirming the model’s ability to generalize.
  - ![image](https://github.com/user-attachments/assets/f3f97323-dd36-47af-aba2-12b6ecb0a4c5)

- Results Analysis
  - The model demonstrated high accuracy across most classes, with a few misclassifications in clusters where sound characteristics overlapped (e.g., dogs and frogs).
  - Model performance for each audio file:
  - ![image](https://github.com/user-attachments/assets/ff93448f-d9a8-4a08-9b63-4ba051ad7e1c)

- Confusion Matrix:
  - Visualized the distribution of true positives, false positives, and misclassifications across the four animal categories.
  - Showed high precision for cats and dogs, with minor errors in cow and frog classifications due to limited dataset size.
  - ![image](https://github.com/user-attachments/assets/5e31a0a1-7458-43a5-aa1a-befdb741b0b2)




If issues are experienced, or additional documentation is preferred: [Edge Impulse Issues](issues/Edge-Issues.md)
  
## Hardware Integration
After the model is completed, it can be deployed on the edge device. A serial connection is the default way to receive the classification data once the model is flashed, as the board runs inferences continuously. The audio and classification data can also be sent to the Edge Impulse software to be incorporated into model training and testing, or it is simply a convenient way to store the deployed model results. Due to the issues detailed in the integration issues document, we were not able to deploy the model on the chip to run on-board model testing. However, had the model been on the board, we would have been able to find animals and use digital audio playback for testing the model. The device would classify the audio for each 3-second cycle into one of the 4 animal categories. The intention of this project was really a proof-of-concept for this application (the AI bioacoustic ID field seems surprisingly under-developed), since most people already can identify the sounds of cats, dogs, frogs and cows and none of them are rare species. So, it was unfortunate that we were not able to test this model in the field(s); but, we are confident that another approach, with a much more robust dataset, would have the capability to yield impressive results and to possibly change the field of ecologists and species preservationists. 

If issues are experienced, or additional documentation is preferred: [Hardware Integration Issues](issues/Integration-Issues.md)

## Personal Development
Through this project, several key lessons were learned that offer valuable insights for future endeavors. A major takeaway is the significant impact of processing blocks on the model's accuracy; careful selection and optimization of these blocks are crucial. It became evident that relying solely on spectrogram processing is insufficient for accurately classifying audio, highlighting the need to incorporate additional feature extraction techniques. Additionally, the importance of a robust and well-curated dataset for both training and testing processes cannot be overstated, as it directly influences the system’s performance.

Reflecting on the hardware integration process, significant challenges were encountered in establishing reliable communication between the software and the Syntiant board. Addressing these issues required ensuring that relevant tool files were accessible in the Ubuntu environment, reconfiguring the Syntiant link, and exploring device-specific workarounds. This phase highlighted the critical importance of maintaining seamless connections, accurate downloads, and properly configured profiles to enable smooth interaction between hardware and software. These challenges served as a valuable learning experience, emphasizing the need for thorough preparation and adaptability when working with advanced embedded systems.

Despite these hurdles, the project achieved its primary objectives. The system was successfully designed and is capable of accurately classifying animal calls, with defined classes tested and achieving an accuracy rate exceeding 80% with minimal loss. These results affirm the feasibility of using the Syntiant TinyML hardware for edge AI applications and pave the way for future enhancements and impactful real-world implementations.

## Expansions and Improvements
### Improvements for this Design
- Looking forward, there are several ways this project could be improved to enhance its capabilities and scope. One key improvement would be to increase the accuracy of the model by acquiring a larger dataset, with at least 500 audio files per animal to support more robust training. This would not only improve classification accuracy but also enable the addition of more animal classes, improving the system's functionality beyond its current scope. Achieving this improvement would require a targeted effort to locate and incorporate additional audio files from reliable sources.
- For a more realistic on-site implementation,and accuracy improvements, the system could integrate another processing block to streamline the identification process. This might involve combining multiple feature extraction techniques to better handle environmental noise and variability.

### Future Expansions
- This design could be expanded by incorporating a visual aid component—such as a display screen or mobile app integration—could improve user accessibility, making the system more intuitive for a broader audience.
- This system could allso become a valuable educational tool, teaching users to identify and understand animal sounds. It could engage children and adults alike through interactive learning modes, such as sound quizzes, or enhance learning experiences with augmented reality (AR) that pairs animal sounds with visual representations. This would make the system an innovative way to spark curiosity about wildlife and ecosystems.
- In survival scenarios, this design could identify potentially dangerous wildlife based on their vocalizations, helping to alert users in real time to hazards like snakes or large predators. By ensuring offline functionality, the tool could be used in remote areas without internet access, making it a reliable companion for hikers, campers, and other outdoor enthusiasts.
- For scientists and ecologists, this system could streamline biodiversity monitoring and wildlife research. With expanded classifiers and sustainable hardware, it could identify a broader range of species in real time while operating in remote environments. Automated logging of audio data and species detection would make it a powerful tool for conservation efforts and ecological studies.

*These expansions not only align with the project's goals of automation and accessibility but also lay the groundwork for future advancements in edge AI applications*


## Project Deliverables
| Date | Submission |
|:-------------------|:-------------------|
| November 7th, 2024 | [Project Proposal](Project-Proposal.md) |
| November 26th, 2024 | [Milestone 1](Milestone-1.md) |
| December 5th, 2024 |[Final Project Presentation](Final-Project-Presentation.pdf) |




![](.github/logo.png)
