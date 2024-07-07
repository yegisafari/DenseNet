# DenseNet
DenseNet Implementation and Experiments on CIFAR-10
# DenseNet Implementation and Experiments on CIFAR-10

## Project Overview

This project involves implementing a DenseNet model using Keras' functional API and experimenting with it on the CIFAR-10 dataset. The key steps include defining custom building blocks for the DenseNet model, implementing a compression factor, experimenting with Bottleneck layers, and evaluating the model with and without data augmentation and dropout.

## Steps and Objectives

### 1. Reading the Original DenseNet Paper
The foundational DenseNet paper provides the theoretical background for this implementation. You can read the paper [here](https://arxiv.org/pdf/1608.06993.pdf).

### 2. Custom Building Blocks
Implement the custom building blocks required for a DenseNet model:
- **Composition Function**
- **DenseNet Block**
- **Transition Block**

These will be defined using Keras' functional API.

### 3. Compression Factor
To make the model more compact, implement a compression factor of θ = 0.5 in the transition block, as DenseNets increase the number of feature maps over each block.

### 4. Bottleneck Layers
Experiment with Bottleneck layers as proposed in the DenseNet paper. Note that they may not be necessary for the relatively small CIFAR-10 dataset.

### 5. Network Architecture
Use a network architecture with:
- 3 DenseNet blocks
- A growth rate of k = 12

Process the input images as described in the paper.

### 6. Classifier
For the classifier part of the network, use global averaging pooling followed by a dense output layer, similar to GoogLeNet.

### 7. Experiments
Conduct two sets of experiments as reported in the DenseNet paper:
- Using data augmentation without dropout
- Using dropout (20%) without data augmentation

### 8. Evaluation
Evaluate all models on the test dataset. Determine which version gives the most accurate results and whether your DenseNet model outperforms other models studied in class.

## Repository Structure
- `src/`: Contains the implementation of the DenseNet model and custom building blocks.
- `data/`: Scripts for loading and preprocessing the CIFAR-10 dataset.
- `experiments/`: Notebooks and scripts for running experiments with different configurations.
- `results/`: Logs and evaluation metrics from experiments.

## Usage
1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/densenet-cifar10.git
    cd densenet-cifar10
    ```

2. Install the required dependencies:
    ```sh
    pip install -r requirements.txt
    ```

3. Run the training scripts with your desired configuration:
    ```sh
    python src/train.py --config configs/experiment1.json
    ```

4. Evaluate the models:
    ```sh
    python src/evaluate.py --model_path models/experiment1.h5
    ```

## Results
Details of the experimental results, including accuracy and comparisons with other models, will be documented in the `results/` directory.

## References
- Original DenseNet Paper: [https://arxiv.org/pdf/1608.06993.pdf](https://arxiv.org/pdf/1608.06993.pdf)
