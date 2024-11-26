# AI Hardware Project Proposal
### ECE 4501 - Fall 2024

## Team Name: 
Who's Calling?

## Team Members:
- Ethan Jenkins
- Bella Heintges
- Eric Sheetz

## Project Title:
Bioacoustic Animal Identification

## Project Description:
We plan to design a compact system capable of identifying local wildlife species by recognizing their vocal calls by leveraging the power of TinyML. This system will be deployed on a microcontroller specifically chosen for its capability to record and process audio data in real-time. By analyzing the audio inputs, our system will be able to detect and classify animal sounds, allowing for efficient and on-site wildlife monitoring.

## Key Objectives:
- Determine ideal hardware, along with an optimized ML network structure. 
- Determine sufficient classification categories to further train the network. 
- Alongside the trained network, use the deployed hardware to correctly identify animals based on their calls.
- Design this system such that it can be utilized hands-on, in various locations.

## Technology Stack:
- Platform: TinyML 
- Software Tools: C/C++
- Hardware Tools: Syntiant TinyML

## Expected Outcomes:
- By the end of the semester we will have a working model that can listen to an animal sound and correctly identify that sound with at least 80% accuracy.
- We will have a model that has been trained to correctly identify these sounds for at least 5 common farm animals.
## Timeline:
 - By 11/8: Select hardware
 - By 11/15: Choose classifications
 - By 11/22: Choose network structure
 - By 11/29: Have network trained
 - By 12/6: Successful test of deployed network



## Milestone 1:
- Have training and testing datasets compiled for our 5 selected animals (sheep, cow, pig, dog, rooster)
- Have began training model in Edge Impulse using Datasets
- Have compiled other animal sound audio files (.wav) to use during testing (lion, monkey, frog, bird)
