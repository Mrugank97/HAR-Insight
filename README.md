## HAR-INSIGHT (Human Activity Recognition using Sensor Data)

## Description
Human Activity Recognition (HAR) refers to the capability of machines to identify various activities performed by the users. The knowledge acquired from these recognition systems is integrated into many applications where the associated device uses it to identify actions or gestures and performs predefined tasks in response.

In this project, we will be using a publically available dataset called [UCI-HAR](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8567275). The dataset is available to download [here](https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones). The Dataset contains data for 30 participants . Each participant performed six activities while wearing a Samsung Galaxy S II smartphone on their waist (The video of the participants taking data is also available [here](http://www.youtube.com/watch?v=XOEN9W05_4A)). The smartphone's accelerometer and gyroscope captured 3-axial linear acceleration and 3-axial angular velocity.

## Preprocessing.
We will use the raw accelerometer data within the inertial_signals folder. The provided script, `CombineScript.py`, organizes and sorts accelerometer data, establishing separate classes for each category and compiling participant data into these classes. `MakeDataset.py` script is used to read through all the participant data and create a single dataset. The dataset is then split into train,test and validation set. We focus on the first 10 seconds of activity, translating to the initial 500 data samples due to a sampling rate of 50Hz.

* **Step-1>** Place the `CombineScript.py` and `MakeDataset.py` in the same folder that contains the UCI dataset. Ensure you have moved into the folder before running the scripts. If you are runing the scripts from a different folder, you will have to play around with the paths in the scripts to make it work.
* **Step-2>** Run `CombineScript.py` and provide the paths to test and train folders in UCI dataset. This will create a folder called `Combined` which will contain all the data from all the participants. This is how most of the datasets are organized. You may encounter similar dataset structures in the future.
* **Step-3>** Run `MakeDataset.py` and provide the path to `Combined` folder. This will create a Dataset which will contain the train, test and validation set. You can use this dataset to train your models.

## Project Tasks

1. **Visualization of Activity Waveforms:** Plot waveforms for each activity class to explore differences and similarities among activities. Assess the potential for classification based on these visualizations.

2. **Classification of Static and Dynamic Activities:** Analyze linear acceleration data for each activity to determine if a machine learning model is necessary to differentiate between static (laying, sitting, standing) and dynamic (walking, walking downstairs, walking upstairs) activities. Justify the need for a model based on the data characteristics.

3. **Decision Tree Classification:** Train a Decision Tree classifier using the training set and evaluate its accuracy and confusion matrix performance using the test set.

4. **Decision Tree with Varying Depths:** Train Decision Trees with depths ranging from 2 to 8 and report accuracies and confusion matrices. Investigate changes in accuracy with increasing depth and provide insights into observed results.

5. **PCA Visualization of Total Acceleration:** Apply Principal Component Analysis (PCA) to compress total acceleration time series data into two features. Visualize different activity classes using scatter plots. Additionally, utilize the [TSFEL](https://tsfel.readthedocs.io/en/latest/) ([a featurizer library](https://github.com/fraunhoferportugal/tsfel)) to create features and to extract relevant features and perform PCA to obtain two features.

6. **Decision Tree Classification with Extracted Features using TSFEL:** Use features obtained from `TSFEL` to train a Decision Tree classifier. Report accuracy and confusion matrix results using the test set. Compare the performance with using raw data and assess the effectiveness of featurization.

7. **Comparison of Decision Tree Performance:** Compare Decision Tree performance with varying depths using raw data versus features extracted from TSFEL. Plot and analyze the accuracies obtained to determine the impact of featurization on classification performance.