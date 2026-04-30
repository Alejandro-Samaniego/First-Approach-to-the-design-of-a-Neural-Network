# 🧠 Neural Network Digit Recognizer

This project implements a fully connected neural network **from scratch (NumPy-based)** to recognize handwritten digits.

## 📌 Features

- Custom feedforward neural network
- Manual backpropagation
- Quadratic and Cross-Entropy loss
- Predict from:
  - MNIST dataset
  - Custom uploaded images
  - Interactive drawing canvas
- Real-time Tkinter GUI
- Image preprocessing pipeline

---

## 🧱 Project Structure

```bash
.
├── our_NN/
├── NN.py
├── run_NN.py
└── README.md
```

---

## ⚙️ Requirements

Install dependencies:

```bash
pip install numpy matplotlib pillow termcolor scikit-learn
```

---

## 🚀 Usage

### Initialize the network

```python
nn = Neural_Network([784, 30, 10])
```

---

### Train with Quadratic Cost

```python
nn.SGD_quad(
    X_train,
    y_train,
    epochs=10,
    mini_batch_size=32,
    eta=0.1
)
```

---

### Train with Cross-Entropy Cost

```python
nn.SGD_entropy(
    X_train,
    y_train,
    epochs=10,
    mini_batch_size=32,
    eta=0.1,
    lambda_learn=0.01
)
```

---

### Predict

```python
prediction, probs = nn.prediction(image)
```

---

### CLI Menu

```python
nn.menu(X_test, y_test, scaler)
```

---

### Launch Drawing GUI

```python
nn.setup_gui()
```

Draw a digit and get live predictions.

---


---


```markdown
## ▶️ Example Script

The file `run_NN.py` provides a complete example of how to use the neural network.

It typically includes:
- Loading and preprocessing data (e.g., MNIST)
- Initializing the network
- Training the model
- Evaluating predictions

If you're unsure where to start, run this file first:

```bash
python run_NN.py

## 🖼️ Image Preprocessing

Custom images are:

1. Converted to grayscale
2. Cropped
3. Resized to 28×28
4. Normalized
5. Standardized

---

## 🧮 Neural Network Math

Forward pass:

```python
z = W·a + b
a = sigmoid(z)
```

Backpropagation computes gradients and updates weights using SGD.

---

## 💾 Saved Weights

Training outputs:

- `final_weights_quad.txt`
- `final_weights_entropy.txt`

---

## ⚠️ Limitations

- NumPy only (CPU)
- No model loading
- Basic GUI smoothing
- Limited preprocessing robustness

---

## 👨‍💻 Authors

- Janot Vilaró
- Alejandro Samaniego

---

## 📜 License

Educational use.
