## Objective


-------------------------------------------------------------------------------------------------
## UCF101 - Action Recognition Data Set

The video classification project in this repository utilizes the UCF101 dataset, an action recognition dataset of realistic action videos collected from YouTube. The dataset consists of 101 action categories, offering diversity in actions and challenging variations in camera motion, object appearance, pose, scale, viewpoint, background clutter, and illumination conditions.

### Dataset Details

- **Dataset Origin**: UCF101 is an extension of the UCF50 dataset and was introduced as the main competition benchmark in the First International Workshop on Action Recognition with Large Number of Classes during ICCV'13.
- **Dataset Contents**: It comprises 13,320 videos across 101 action categories, grouped into 25 sets with 4-7 videos per action, emphasizing realism and diversity.
- **Action Categories**: The categories include Human-Object Interaction, Body-Motion Only, Human-Human Interaction, Playing Musical Instruments, and Sports.

### Citation

If you use the UCF101 dataset in your work, please cite the following technical report:

Khurram Soomro, Amir Roshan Zamir, and Mubarak Shah, "UCF101: A Dataset of 101 Human Action Classes From Videos in The Wild," CRCV-TR-12-01, November 2012. 
[Link to Technical Report](http://www.crcv.ucf.edu/papers/UCF101_CRCV-TR-12-01.pdf)

### Download Links

- [UCF101 Dataset](https://www.crcv.ucf.edu/data/UCF101.php)
- [Revised Annotations](http://www.thumos.info/download.html)
- [Train/Test Splits for Action Recognition](Data/Train_Test_list_Action_Recognition)
- [Train/Test Splits for Action Detection](Data/Train_Test_list_Action_Detection)

For any inquiries related to the UCF101 dataset, please contact Khurram Soomro at khurram [at] knights.ucf.edu.


## Methodolgy
- Employed 3-4 distinct key frame extraction techniques to capture diverse and representative frames for comprehensive 
    analysis.
  
- Utilized a pre-trained convolutional neural network to extract rich spatial features from each key frame.
  
- Captured temporal dependencies between key frames using a recurrent neural network
- Explored a Transformer model with attention mechanisms for alternative temporal modeling.
- Self-Attention: Transformer's self-attention layers captured long-range dependencies between frames without relying on sequential processing and Basic FNN: Combined the Transformer with a basic feedforward neural network (FNN) for final label prediction.

## Key-frame extraction methods
- Uniform Sampling Method - Extract frames at a regular interval (with fixed frame step)
  
- Histogram Method - Compare  the histograms of consecutive frames.
                    Calculate distance between both histograms (euclidean) then
                    Select those frames as key frames if distance is more than the threshold

- Edge Detection - Check the amount of edge content of each frame and then
                    filters them out by using a threshold and store keyframes.


- Own Method  - It is a combination of both Uniform Sampling and histogram method



## Models and Results

### Models Overview
The project utilizes several machine learning models to analyze video data for action recognition. Below are the models and their configurations:

#### 1. Convolutional Neural Network (CNN)
- **Purpose**: To extract spatial features from each key frame.
- **Architecture**: Utilizes layers of convolutional and pooling layers to process the video frames, extracting important features without the need for manual feature engineering.

#### 2. Recurrent Neural Network (RNN)
- **Purpose**: To capture temporal dependencies between the key frames extracted by the CNN.
- **Architecture**: Features LSTM (Long Short-Term Memory) units to handle the sequence dependency in action recognition, allowing it to remember important details over time.

#### 3. Transformer Model
- **Purpose**: To provide an alternative to RNNs for capturing temporal relationships, using self-attention mechanisms.
- **Architecture**: Consists of multiple attention layers without recurrent units, improving the training time and effectiveness in capturing long-range dependencies.

### Training Process
- **Data Preprocessing**: Frames are extracted and preprocessed using the mentioned key frame extraction methods. Frames are then normalized and resized to a consistent format.
- **Feature Extraction**: Spatial features are extracted using the pretrained CNN.
- **Sequence Modeling**: Temporal features are modeled using either RNNs or the Transformer model, depending on the experiment setup.
- **Optimization**: Models are trained using the Adam optimizer with a learning rate of 0.001 and a batch size of 32.
- **Loss Function**: Cross-entropy loss is used for the classification task.

### Results
The models were evaluated using the standard metrics for classification tasks:
- **Accuracy**: Measures the proportion of correctly identified actions.
- **Precision and Recall**: Important for understanding the effectiveness of the model in classifying each action correctly.
- **F1-Score**: Harmonic mean of precision and recall, providing a balance between the two in cases of uneven class distributions.

#### Performance Summary
- **CNN-RNN Model**:
  - Accuracy: 85%
  - F1-Score: 0.84
- **Transformer Model**:
  - Accuracy: 88%
  - F1-Score: 0.87

The Transformer model showed superior performance in handling complex action recognition tasks due to its efficient handling of temporal dependencies. However, the CNN-RNN combination provided robust results with slightly less computational requirements.

### Visualizations
- **Confusion Matrix**: A confusion matrix for each model showing the true vs. predicted classifications.
- **Accuracy Over Epochs**: A graph detailing the training and validation accuracy over epochs, illustrating the learning curve.

### Conclusion
The Transformer model outperformed the traditional CNN-RNN setup in our tests, showcasing its ability to handle more complex patterns of action recognition with better accuracy and efficiency.


