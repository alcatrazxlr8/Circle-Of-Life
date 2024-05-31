# Circle Of Life
Developing and analyzing probabilistic models for decision-making in a dynamic environment where an agent pursues a prey while evading a predator.

## Overview

This project, completed as part of the Computer Science course at Rutgers University (Fall 2022), focuses on building a probabilistic model of an environment with uncertainty to inform decision-making. The project involves an agent pursuing a prey while being pursued by a predator. The agent must capture the prey while evading the predator, despite not always knowing their exact locations.

## Project Structure

### 1. Environment

The environment is a graph consisting of 50 nodes, connected in a large circle. Additional edges are added randomly to increase connectivity. The environment supports the movement of three entities: the Agent, the Prey, and the Predator.

### 2. Entities

- **Agent**: Pursues the Prey while evading the Predator. Moves based on specific strategies that account for varying levels of information about the other entities.
- **Prey**: Moves randomly to neighboring nodes or stays in its current node.
- **Predator**: Moves towards the Agent by selecting the shortest path among neighboring nodes.

### 3. Agent Strategies

#### Complete Information Setting

**Agent 1**: Moves based on the following priority:
   - Closer to the Prey and farther from the Predator.
   - Closer to the Prey and not closer to the Predator.
   - Not farther from the Prey and farther from the Predator.
   - Not farther from the Prey and not closer to the Predator.
   - Farther from the Predator.
   - Not closer to the Predator.
   - Stays still as a last resort.

**Agent 2**: Custom strategy designed to outperform Agent 1.

#### Partial Prey Information Setting

**Agent 3**: Surveys the node with the highest probability of containing the Prey and moves based on updated probabilities.

**Agent 4**: Custom strategy designed to outperform Agent 3.

#### Partial Predator Information Setting

**Agent 5**: Surveys the node with the highest probability of containing the Predator and moves based on updated probabilities.

**Agent 6**: Custom strategy designed to outperform Agent 5.

#### Combined Partial Information Setting

**Agent 7**: Surveys based on the highest probability of the Predator or Prey, updates probabilities, and moves accordingly.

**Agent 8**: Custom strategy designed to outperform Agent 7.

## Analysis

The performance of each agent strategy was analyzed through simulations. Key metrics include:

- Frequency of the Predator catching the Agent.
- Frequency of the Agent catching the Prey.
- Frequency of simulation hangs (no capture past a large time threshold).
- Accuracy of the Agent's knowledge of the Prey's and Predator's locations.

### Additional Analysis Questions

- How should belief update rules be adjusted for scenarios with false negatives in surveys?
- Comparison of Agents 7 and 8 in scenarios with and without belief update rule adjustments.
- Potential development of Agent 9 for improved performance.

## Usage

To run the project, open the provided Jupyter Notebook (`The_Circle_of_Life.ipynb`) in an appropriate environment (e.g., Jupyter Lab, Google Colab). The notebook includes detailed comments and explanations for implementation and experimentation.

### Requirements

- Python 3.x
- Jupyter Notebook
- Required libraries: `numpy`, `matplotlib`, `random`

### Running the Notebook

1. Clone the repository.
   ```bash
   git clone https://github.com/yourusername/The_Circle_of_Life.git
   cd The_Circle_of_Life
   ```
2. Open the Jupyter Notebook.
   ```bash
   jupyter notebook The_Circle_of_Life.ipynb
   ```
3. Follow the instructions in the notebook to run the simulations and analyze the results.

## Conclusion

This project explores the complexities of decision-making in uncertain environments. By comparing different agent strategies, it provides insights into the effectiveness of various probabilistic models and decision-making algorithms.

## Acknowledgements

- Rutgers University, Computer Science Department
- Course Instructor and Teaching Assistants

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
