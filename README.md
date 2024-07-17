Quizz
Name: Gopi Palepu, Id: 700759819

Description of Steps Leading to Improved Response and Impact on Architecture Behavior
Normalization and One-Hot Encoding:
Normalization: Scaling the pixel values of images to the range [0, 1] helps in faster
convergence and stabilizes the training process.
One-Hot Encoding: Converting class labels to a binary class matrix (one-hot encoding) is
crucial for categorical cross-entropy loss to work correctly, as it provides a direct comparison
between the predicted class probabilities and the actual class labels.
CNN Architecture:
The initial architecture with three convolutional layers followed by max-pooling layers was
designed to capture spatial hierarchies in the image data. Increasing the number of filters in
subsequent layers allows the model to learn more complex patterns.
Dropout Layer: Adding a dropout layer helps in regularizing the model and preventing overfitting
by randomly setting a fraction of input units to 0 during training.
Hyperparameter Tuning:
Using RandomSearch from keras-tuner to search for the best hyperparameters significantly
improves the model performance. Parameters like the number of filters in convolutional layers,
the number of dense units, dropout rate, and the choice of optimizer were tuned.
The optimal combination of these parameters enhances the model's ability to generalize to
unseen data.
Callback Functions:
ReduceLROnPlateau: This callback reduces the learning rate when a metric has stopped
improving. It helps in fine-tuning the learning process and avoids overshooting the minimum
loss.
EarlyStopping: It stops training when the validation loss stops improving, which prevents
overfitting and saves training time.
ModelCheckpoint: Saves the model with the best validation loss during training. This ensures
that the best model is retained for evaluation.
Evaluation and Visualization:
Confusion Matrix: Provides insights into how well the model is performing on each class,
highlighting misclassified instances.
Training and Validation Plots: Visualization of loss and accuracy during training helps in
diagnosing issues like overfitting or underfitting. It provides a clear picture of the model's
learning progress.
Accuracy Per Class: This bar chart helps in identifying classes where the model is
underperforming. It is essential for further fine-tuning and understanding class-specific
performance.
Misclassified Images: Displaying misclassified images helps in visually inspecting where the
model is making errors. This can give clues on what features might be missing or misinterpreted
by the model
