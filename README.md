# NeuroSculptor: A Novel Framework for Neural Network Architecture Design

NeuroSculptor is a TypeScript-based framework designed to facilitate the dynamic construction and manipulation of neural network architectures. It provides a modular and extensible environment for researchers and developers to experiment with novel network topologies, training regimes, and hyperparameter configurations. The core goal of NeuroSculptor is to abstract away the complexities of low-level neural network implementation, enabling users to focus on high-level architectural design and experimentation. By providing a robust foundation built on TypeScript's type safety and modern JavaScript features, NeuroSculptor aims to accelerate the pace of innovation in neural network research and deployment.

This framework distinguishes itself by allowing users to define neural network components as composable building blocks. These building blocks, defined in TypeScript, can be dynamically assembled into complex architectures. This enables a high degree of flexibility in exploring different network structures and allows for the creation of networks that are not easily definable using traditional, static approaches. Furthermore, NeuroSculptor emphasizes modularity, making it easy to extend the framework with custom layers, activation functions, and training algorithms. The framework is particularly well-suited for research projects requiring rapid prototyping and experimentation with unconventional neural network designs.

NeuroSculptor provides a rich set of features, including support for various layer types (convolutional, recurrent, feedforward), activation functions (ReLU, sigmoid, tanh), and optimization algorithms (SGD, Adam, RMSprop). It also includes tools for visualizing network architectures and monitoring training progress. The framework leverages the power of TypeScript to ensure type safety and provides detailed documentation to guide users through the process of designing, training, and deploying neural networks. This robust combination of features and capabilities makes NeuroSculptor a powerful tool for both experienced researchers and newcomers to the field of neural networks.

## Key Features

*   **Composable Layer Architecture:** Define neural network layers as TypeScript classes and compose them into complex architectures. Each layer exposes a well-defined interface for connecting to other layers, ensuring data flow integrity. This is achieved through the `Layer` abstract class and its associated interface `ILayer`.
*   **Dynamic Network Graph Construction:** Dynamically build the network graph at runtime based on user-defined configurations. The `NetworkBuilder` class provides methods for adding layers, connecting them, and specifying the overall network structure.
*   **Custom Layer Support:** Easily extend the framework with custom layers by implementing the `ILayer` interface and providing the necessary forward and backward propagation logic. This allows users to integrate novel layer types into the existing framework.
*   **Flexible Training Regimes:** Support for various optimization algorithms (SGD, Adam, RMSprop) with customizable learning rates, momentum, and other hyperparameters. The `Trainer` class handles the training loop and provides callbacks for monitoring training progress. The use of interfaces like `IOptimizer` allows for easy swapping and addition of new optimization algorithms.
*   **Network Visualization:** Integrated tools for visualizing network architectures and monitoring training progress, allowing users to gain insights into the network's behavior. This functionality leverages libraries like D3.js to render interactive network diagrams.
*   **Type Safety with TypeScript:** Leverage the power of TypeScript to ensure type safety and prevent runtime errors. All core components are written in TypeScript and thoroughly tested. This allows for easier debugging and maintenance.
*   **Modular Design:** A modular architecture that promotes code reusability and extensibility. Core components are decoupled and interact through well-defined interfaces, making it easy to add new features and functionalities.

## Technology Stack

*   **TypeScript:** The primary language for the framework, providing type safety and modern JavaScript features. TypeScript allows for better code organization and maintainability, crucial for a complex project like NeuroSculptor.
*   **Node.js:** The runtime environment for executing the TypeScript code. Node.js provides a robust and scalable platform for running the framework.
*   **npm (Node Package Manager):** Used for managing project dependencies and building the application. npm simplifies the process of installing and updating external libraries.
*   **D3.js (Optional):** Used for network visualization. D3.js provides a powerful and flexible way to create interactive diagrams of neural network architectures. If visualization is not required, this dependency can be omitted.
*   **Jest:** A JavaScript testing framework used for unit testing and integration testing. Jest ensures the correctness and reliability of the framework's components.

## Installation

1.  **Install Node.js and npm:** Ensure that Node.js and npm are installed on your system. You can download them from the official Node.js website: https://nodejs.org/. Minimum required version is Node 16.
2.  **Clone the Repository:** Clone the NeuroSculptor repository from GitHub:

    git clone https://github.com/jjfhwang/NeuroSculptor.git

3.  **Navigate to the Project Directory:** Change your current directory to the NeuroSculptor project directory:

    cd NeuroSculptor

4.  **Install Dependencies:** Install the project dependencies using npm:

    npm install

5.  **Build the Project:** Compile the TypeScript code into JavaScript:

    npm run build

## Configuration

NeuroSculptor relies on environment variables for certain configurations. Create a `.env` file in the project root directory and define the following variables as needed:

*   `NODE_ENV`: Set to `development` or `production` to control the build and logging behavior.
*   `LOG_LEVEL`: Set the logging level (e.g., `debug`, `info`, `warn`, `error`).
*   `NETWORK_CONFIG_PATH`: Path to a JSON file containing network configuration parameters (optional). If omitted, default values are used.

Example `.env` file:

NODE_ENV=development
LOG_LEVEL=debug
NETWORK_CONFIG_PATH=./config/network.json

## Usage

After installation and configuration, you can use NeuroSculptor to design, train, and deploy neural networks. Here's a basic example:

// Import necessary modules
import { NetworkBuilder } from './src/network/NetworkBuilder';
import { DenseLayer } from './src/layers/DenseLayer';
import { Trainer } from './src/training/Trainer';
import { AdamOptimizer } from './src/optimizers/AdamOptimizer';

// Create a network builder
const builder = new NetworkBuilder();

// Add layers to the network
builder.addLayer(new DenseLayer(10, 'relu'));
builder.addLayer(new DenseLayer(5, 'relu'));
builder.addLayer(new DenseLayer(1, 'sigmoid'));

// Build the network
const network = builder.build();

// Create an optimizer
const optimizer = new AdamOptimizer(0.001);

// Create a trainer
const trainer = new Trainer(network, optimizer);

// Train the network
trainer.train(trainingData, labels, epochs);

Detailed API documentation can be found in the `docs/` directory (not included for brevity but would be generated via a tool like TypeDoc).

## Contributing

We welcome contributions to NeuroSculptor! Please follow these guidelines when contributing:

*   Fork the repository and create a branch for your feature or bug fix.
*   Write clear and concise commit messages.
*   Follow the existing coding style and conventions.
*   Write unit tests for your code.
*   Submit a pull request with a detailed description of your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/jjfhwang/NeuroSculptor/blob/main/LICENSE) file for details.

## Acknowledgements

We would like to thank the open-source community for providing the tools and libraries that made NeuroSculptor possible. Specifically, we acknowledge the contributions of the TypeScript, Node.js, and D3.js communities.