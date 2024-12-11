# Step 1: Aggregation of Tools
Before beginning the project, it will be necessary to set up various accounts, download the required tools, and prepare both the hardware and software environments. These steps ensure a smooth workflow for developing, training, and deploying the ShazAnimal system.

## (1) Create respective accounts:
### Edge Impulse
Edge Impulse is a leading platform for developing, deploying, and optimizing machine learning (ML) models specifically designed for edge devices. It provides tools to simplify the creation of ML models for real-world applications, such as audio, image, and sensor data processing, enabling low-latency and energy-efficient solutions.

Visit Edge Impulse to create a free account. This platform will be used to design, train, and deploy the machine learning model.

Sign-Up Link: https://studio.edgeimpulse.com/signup

Getting Started: https://www.edgeimpulse.com/blog/getting-started-with-edge-impulse/
    
### GitHub
GitHub is a web-based platform that provides version control, collaboration, and project management tools for developers. It is built on top of Git, a widely-used distributed version control system, and offers additional features to facilitate software development, team collaboration, and project organization.

If you don’t already have one, create a GitHub account to manage your project repository and track changes.

Sign-Up Link: https://github.com/join

How-To Use: https://docs.github.com/en/get-started/start-your-journey/hello-world

## (2) Prepare and download software:
### Linux or Linux-Based System
Linux is an open-source operating system kernel that forms the foundation for various operating systems, known as Linux distributions (e.g., Ubuntu, Fedora, Debian). A Linux-based system uses this kernel to provide a flexible, stable, and secure environment for running applications and managing hardware, often preferred for servers, development, and embedded systems.

Ensure you have access to a Linux environment (native or virtual). A Linux-based system simplifies the use of command-line tools is required for this project.

### Git
Git is a distributed version control system that allows multiple developers to track changes, collaborate on, and manage the history of software projects. It enables users to work on different parts of a project simultaneously, merge changes, and revert to previous versions, ensuring a robust workflow and minimizing the risk of data loss or conflicts.

Install Git to clone and manage your GitHub repository. Instructions can be found here.
    
### Edge Impulse CLI
The Edge Impulse CLI (Command Line Interface) is a tool that allows developers to interact with the Edge Impulse platform directly from the terminal. It enables users to streamline tasks such as data collection, model training, and deployment to edge devices without needing to use the web-based interface. The CLI facilitates the creation and management of machine learning projects, uploading sensor data, generating models, and deploying those models to embedded devices, all through command-line commands. This tool is particularly useful for automating workflows, integrating Edge Impulse with other development tools, and working in resource-constrained environments where GUI access may be limited.

Download the Edge Impulse CLI by following the instructions in the Edge Impulse documentation. This tool connects your local development environment to the Edge Impulse platform.

How-To Install: https://docs.edgeimpulse.com/docs/tools/edge-impulse-cli/cli-installation

### Arduino CLI
The Arduino CLI (Command Line Interface) is a tool that allows developers to interact with the Arduino ecosystem via the command line, rather than using the graphical Arduino IDE. It provides functionality for compiling and uploading Arduino sketches (programs) to Arduino boards, managing libraries and board definitions, and performing other tasks related to the development and deployment of Arduino-based projects. The Arduino CLI is particularly useful for automating workflows, integrating with other tools, or working in environments where a graphical user interface is not feasible, such as in continuous integration (CI) systems or embedded development setups.

Install the Arduino CLI to interface with the TinyML board. Instructions are available on the Arduino CLI setup page.

How-To Install: https://arduino.github.io/arduino-cli/0.24/installation/

## (3) Setup hardware:
### Syntiant TinyML Board
Obtain a Syntiant TinyML NDP101 board, which will serve as the deployment hardware for the trained model. Follow the manufacturer’s instructions for setting up and connecting the board.

![image](https://github.com/user-attachments/assets/ff92aed9-8043-4ab8-a8ff-2dbeace2d171)

### USB Cable
Use a compatible USB cable to connect the board to your Linux system for data transfer and testing.
    
### Linux-Enabled Device
Ensure that your Linux-enabled computer or virtual machine is prepared to run the necessary software and interface with the TinyML board.

## (4) Configure the enviornment:
### Install Python
Ensure Python is installed and configure a virtual environment for running scripts.

Link to Download: https://www.python.org/downloads/
    
### Required Libraries
Install any necessary Python packages (e.g., numpy, matplotlib) as specified in the requirements.txt file included in the repository.

*By completing these steps, you’ll have all the tools and accounts needed to proceed with data acquisition, model design, and hardware integration. This setup forms the foundation for the entire project.*

