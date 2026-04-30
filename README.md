🧠 Neural Network Digit Recognizer

This project implements a fully connected neural network from scratch (NumPy-based) to recognize handwritten digits. It includes:

Training using Stochastic Gradient Descent (SGD)
Support for Quadratic and Cross-Entropy loss functions
Image preprocessing for custom inputs
A Tkinter GUI to draw digits and predict them in real time
Visualization using Matplotlib
📌 Features
Custom implementation of a feedforward neural network
Backpropagation (manual, no deep learning frameworks)
Two training modes:
Quadratic cost
Cross-entropy cost (with L2 regularization)
Predict digits from:
MNIST dataset
User-provided images
Interactive drawing canvas
Image preprocessing pipeline (resizing, normalization, cropping)
Real-time prediction visualization
🧱 Project Structure
.
├── neural_network.py   # Main class and logic
├── fotos/             # Folder for user images
├── final_weights_*.txt # Saved trained weights
└── README.md
⚙️ Requirements

Install dependencies with:

pip install numpy matplotlib pillow termcolor scikit-learn
🚀 Usage
1. Initialize the Neural Network
nn = Neural_Network([784, 30, 10])
784 → input layer (28x28 pixels)
30 → hidden layer
10 → output layer (digits 0–9)
2. Train the Network
Quadratic Cost:
nn.SGD_quad(X_train, y_train, epochs=10, mini_batch_size=32, eta=0.1)
Cross-Entropy Cost:
nn.SGD_entropy(X_train, y_train, epochs=10, mini_batch_size=32, eta=0.1, lambda_learn=0.01)
3. Evaluate / Predict
prediction, probabilities = nn.prediction(image)
4. Menu Mode (CLI)
nn.menu(X_test, y_test, scaler)

Allows you to:

Predict MNIST samples
Load custom images from /fotos
5. GUI Drawing Mode 🎨
nn.setup_gui()
Draw a digit using your mouse
See live probability bars (0–9)
Clear canvas anytime
🖼️ Image Preprocessing

Custom images go through:

Grayscale conversion
Cropping (detect digit edges)
Resizing to 28×28
Normalization (0–1)
Standardization (via StandardScaler)
🧮 How It Works
Feedforward

Each layer computes:

z = W·a + b
a = sigmoid(z)
Backpropagation
Computes gradients layer by layer
Updates weights using SGD
Supports:
Quadratic loss
Cross-entropy loss (more stable)
💾 Saving Weights

After training, weights and biases are saved to:

final_weights_quad.txt
final_weights_entropy.txt
⚠️ Known Limitations
No GPU acceleration (NumPy only)
Manual preprocessing may fail on very noisy images
GUI uses simple drawing (no smoothing beyond basic logic)
No model loading (only saving implemented)
🛠️ Possible Improvements
Add model loading (joblib or pickle)
Use ReLU instead of sigmoid for hidden layers
Add convolutional layers (CNN)
Improve preprocessing with OpenCV
Export predictions as probabilities in GUI
Add training visualization (loss curves)
👨‍💻 Authors
Janot Vilaró
Alejandro Samaniego
📜 License

This project is for educational purposes. Feel free to modify and extend it.


