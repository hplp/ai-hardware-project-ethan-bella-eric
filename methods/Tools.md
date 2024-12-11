# Step 1: Aggregation of Tools
Before beginning the project, you will need to set up the necessary accounts, download required tools, and prepare both the hardware and software environments. These steps ensure a smooth workflow for developing, training, and deploying the ShazAnimal system.

## Accounts to Create
- Edge Impulse Account:
  - Visit Edge Impulse to create a free account. This platform will be used to design, train, and deploy the machine learning model.
  - Link: https://studio.edgeimpulse.com/signup
- GitHub Account:
  - If you don’t already have one, create a GitHub account to manage your project repository and track changes.
  - Link: https://github.com/join

## Software to Download and Install
- Linux or Linux-Based System:
  - Ensure you have access to a Linux environment (native or virtual). A Linux-based system simplifies the use of command-line tools required for this project.
- Git:
  - Install Git to clone and manage your GitHub repository. Instructions can be found here.
- Edge Impulse CLI:
  - Download the Edge Impulse CLI by following the instructions in the Edge Impulse documentation. This tool connects your local development environment to the Edge Impulse platform.
- Arduino CLI:
  - Install the Arduino CLI to interface with the TinyML board. Instructions are available on the Arduino CLI setup page.

## Hardware Setup
- Syntiant TinyML Board:
  - Obtain a Syntiant TinyML NDP101 board, which will serve as the deployment hardware for the trained model. Follow the manufacturer’s instructions for setting up and connecting the board.
  - ![image](https://github.com/user-attachments/assets/ff92aed9-8043-4ab8-a8ff-2dbeace2d171)

- USB Cable:
  - Use a compatible USB cable to connect the board to your Linux system for data transfer and testing.
    
- Linux-Enabled Device:
  - Ensure that your Linux-enabled computer or virtual machine is prepared to run the necessary software and interface with the TinyML board.

## Environment Configuration
- Install Python:
  - Ensure Python is installed and configure a virtual environment for running scripts.
  - Link: https://www.python.org/downloads/
- Required Libraries:
  - Install any necessary Python packages (e.g., numpy, matplotlib) as specified in the requirements.txt file included in the repository.

By completing these steps, you’ll have all the tools and accounts needed to proceed with data acquisition, model design, and hardware integration. This setup forms the foundation for the entire project.

