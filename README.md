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
| Step 5:  [Hardware Integration](methods/Integration-and-Results.md) |
| Step 6:  [Deployment and Live Demo](methods/Deployment.md) |

## Results and Discussion


### Model Performance
(PARAGRAPH)
- Discussion of results
- Performance better? -- Link to explanation of issue/mitigation strat --  [Edge Impulse Issues](issues/Edge-Issues.md)
  
### Hardware Integration
(PARAGRAPH)
- Results/what would have been expected results
- Issues with integration -- Link to explanation of issue/mitigation strat --  [Hardware Integration Issues](issues/Integration-Issues.md)

### Personal Development
(PARAGRAPH)
- Lessons learned/i.e. advice
- Considerations/what we would've done differently

## Expansions
- How the project could be bettered/future...
- Possible inclusions -- Link to other implementations

## Project Deliverables
| Date | Submission |
|:-------------------|:-------------------|
| November 7th, 2024 | [Project Proposal](Project-Proposal.md) |
| November 26th, 2024 | [Milestone 1](Milestone-1.md) |
| December 5th, 2024 |[Final Project Presentation](Final-Project-Presentation.pdf) |
