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
-
-
-
-

## Results and Observation
-


