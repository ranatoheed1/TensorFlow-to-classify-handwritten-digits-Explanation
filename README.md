# MNIST Digit Classification with TensorFlow
# Overview
This project implements a simple neural network using TensorFlow to classify handwritten digits from the MNIST dataset. The model is trained on 60,000 training images and evaluated on 10,000 test images, achieving high accuracy. The script also includes a visualization of predicted digits alongside their actual labels.
# Prerequisites

Python 3.10 or higher
Google Colab (or a local Python environment with Jupyter Notebook support)

#Installation

Clone or Download the Repository:If hosted on GitHub, clone the repository:
git clone https://github.com/your-repo/mnist-digit-classification.git

Otherwise, download the script manually.

Install Dependencies:Install the required Python packages using pip:
pip install tensorflow matplotlib numpy



# Usage

Open in Colab:

Upload the script to Google Colab.
Run the script in a Colab cell.


Run the Script:

The script will:
Download and preprocess the MNIST dataset.
Build and train a neural network model.
Evaluate the model on the test set.
Display a 5x5 grid of test images with predicted and actual labels.





# Dependencies

tensorflow: For building, training, and evaluating the neural network.
matplotlib: For visualizing the predicted digits.
numpy: For numerical operations and handling predictions.

Sample Output
Training Output
Epoch 1/5
1875/1875 ━━━━━━━━━━━━━━━━━━━━ 5s 2ms/step - accuracy: 0.8767 - loss: 0.4366
Epoch 2/5
1875/1875 ━━━━━━━━━━━━━━━━━━━━ 3s 2ms/step - accuracy: 0.9633 - loss: 0.1254
Epoch 3/5
1875/1875 ━━━━━━━━━━━━━━━━━━━━ 4s 2ms/step - accuracy: 0.9765 - loss: 0.0787
Epoch 4/5
1875/1875 ━━━━━━━━━━━━━━━━━━━━ 4s 2ms/step - accuracy: 0.9820 - loss: 0.0605
Epoch 5/5
1875/1875 ━━━━━━━━━━━━━━━━━━━━ 3s 2ms/step - accuracy: 0.9859 - loss: 0.0453

Evaluation Output
313/313 ━━━━━━━━━━━━━━━━━━━━ 2s 4ms/step - accuracy: 0.9726 - loss: 0.0942
Test accuracy: 0.9757000207901001

# Visualization
The script generates a 5x5 grid of test images with their predicted and actual labels. Below is a placeholder for the image:

Description: A 5x5 grid of grayscale MNIST digits (28x28 pixels each). Each subplot shows a digit with a title in the format "Predicted: X\nActual: Y", where X is the model's predicted label and Y is the actual label. For example, a subplot might show the digit "7" with the title "Predicted: 7\nActual: 7".
How to Add the Image

After running the script, save the Matplotlib figure as sample_predictions.png:plt.savefig('sample_predictions.png')


Move the image to an images folder in your repository.
Update the README with the correct path to the image.

# Model Architecture
The model is a simple feedforward neural network with the following layers:

Flatten: Converts the 28x28 pixel images into a 1D array of 784 elements.
Dense (128 units, ReLU activation): A fully connected layer with 128 neurons.
Dense (10 units, Softmax activation): Output layer with 10 neurons (one for each digit) and softmax activation for classification.

The model is compiled with:

Optimizer: Adam
Loss Function: Sparse Categorical Crossentropy
Metrics: Accuracy

# Notes

The MNIST dataset is automatically downloaded by TensorFlow from https://storage.googleapis.com/tensorflow/tf-keras-datasets/mnist.npz.
The script normalizes pixel values to the range [0, 1] by dividing by 255.0.
The warning about input_shape in the Flatten layer can be ignored, as the model still functions correctly. To resolve it, you can modify the model to use an Input layer explicitly:model = Sequential([
    tf.keras.Input(shape=(784,)),
    Dense(128, activation='relu'),
    Dense(10, activation='softmax')
])


The model achieves ~97.57% accuracy on the test set after 5 epochs, but you can experiment with more epochs or different architectures to improve performance.

License
This project is licensed under the MIT License.
