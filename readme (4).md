**README**

**An Intelligent Brain MRI Classification System Using CNN and Transfer Learning**

# 1\. Project Name

An Intelligent Brain MRI Classification System Using CNN and Transfer Learning

# 2\. Project Short Description

This project develops a deep-learning-based system for brain MRI tumor classification. It first builds a custom Convolutional Neural Network (CNN) from scratch as a baseline and then extends the system using transfer learning with EfficientNetB0. The transfer-learning model uses pre-trained visual representations, followed by fine-tuning of selected deeper layers to adapt the model to the MRI classification task. The system also supports uploaded-image prediction and displays the predicted class, confidence, and class-wise probabilities.

# 3\. Deep Learning Algorithms Used

-   Custom CNN: A CNN trained from scratch to establish the baseline model and demonstrate fundamental image-feature learning.
-   Transfer Learning with EfficientNetB0: A pre-trained EfficientNetB0 network is used as a feature extractor with its original classification head removed.
-   Fine-Tuning: The last 30 EfficientNetB0 layers are proposed to be unfrozen and trained with a small learning rate of 1e-5, while earlier layers remain frozen.
-   Supporting CNN components: Conv2D, Batch Normalization, ReLU activation, MaxPooling2D, Flatten, Dense layers, Dropout, GlobalAveragePooling2D, and Softmax output.

# 4\. Dataset Features

The project report states that the notebook downloads the dataset through KaggleHub using the identifier “masoudnickparvar/brain-tumor-mri-dataset”. The recorded notebook output contains 5,712 training images and 1,311 testing images across four classes.

Dataset Feature

Value

Training images

5,712

Testing images

1,311

Number of classes

4

Original CNN input size

64 × 64 × 3 RGB

Transfer-learning input size

224 × 224

Batch size

32

Original training

25 epochs

Images are loaded from class-specific folders, where folder names are used as class labels. For uploaded-image prediction, the image is converted to RGB, resized to 224 × 224, converted to a numerical array, given a batch dimension, and processed using the preprocessing expected by EfficientNet.

# 5\. Visualization Explanation

-   Training/validation performance: Accuracy and loss can be used to observe model learning and identify possible overfitting or underfitting.
-   Confusion matrix: Shows how predictions are distributed across the four classes and helps identify which classes are confused with one another.
-   Classification report: Provides class-wise precision, recall, and F1-score for evaluating model performance.
-   Uploaded MRI visualization: The system displays the uploaded MRI image together with the predicted class and confidence.
-   Probability graph: A graph displays the Softmax probability for each of the four classes, making the model's prediction distribution easier to interpret.

The report records approximately 92.75% final validation accuracy and 97.48% training accuracy for the original CNN at epoch 25. The highest visible validation accuracy in the recorded output is approximately 93.29% at epoch 16. Transfer-learning performance should only be reported after the extended model is actually executed.

# 6\. How to Run the Project

-   1\. Install Python and the required deep-learning/data-science libraries used by the notebook/project, such as TensorFlow/Keras, NumPy, Matplotlib, scikit-learn, PIL/Pillow, and KaggleHub.
-   2\. Open the project notebook/code file in Jupyter Notebook, JupyterLab, Google Colab, or another compatible Python environment.
-   3\. Run the dataset-download/access section. The project uses KaggleHub and the dataset identifier “masoudnickparvar/brain-tumor-mri-dataset”.
-   4\. Verify that the Training and Testing folders are available and that the images are organized by class.
-   5\. Run the preprocessing and custom CNN sections to train the baseline model.
-   6\. Run the EfficientNetB0 transfer-learning section. Initially, the pre-trained base is frozen while the new classification head is trained.
-   7\. Run the fine-tuning section to unfreeze the selected deeper layers and train with the smaller learning rate.
-   8\. Run the evaluation section to generate accuracy/loss results, the classification report, and confusion matrix.
-   9\. Run the uploaded-image prediction section, select an MRI image, and view the predicted class, confidence, and probability graph.

# 7\. Model Workflow

-   Dataset access → image loading → resizing/preprocessing → custom CNN baseline → EfficientNetB0 transfer learning → fine-tuning → evaluation → uploaded-image prediction.
-   The custom CNN uses 64 × 64 RGB images, while the proposed EfficientNetB0 transfer-learning pipeline uses 224 × 224 input images.
-   The final prediction uses four Softmax probabilities and selects the class with the highest probability.

# 8\. Important Note

This project is intended for educational and research purposes. The report explicitly states that the system is a classification experiment and not a clinical diagnostic system. A model prediction should therefore not be presented as a medical diagnosis.

# 9\. Author

Mehshar Shahid