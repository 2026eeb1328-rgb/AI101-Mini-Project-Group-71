# Mobile Price Classification Using Logistic Regression
## Important Links :
1. Repository link : 
1. Dataset Source : https://github.com/arpita-maji/Mobile-Price-Classification/blob/master/mobile_price_range_data.csv
2. Video link : (youtube link) https://youtu.be/rlJhewVyLwg?si=QPAkMuMRbkrGE8Bj | drive link(in case there is any problem with youtube link) : https://drive.google.com/file/d/1hBF-0pv2UuPBJkrz_nN5fwh2sWEStzCy/view?usp=drive_link
3. PPT link : 
## 1\. Project objective

This project uses **Multiclass logistic Regression** to classify a mobile phone into one of four price categories using its specifications.

| `price_range` | Category |
| :---- | :---- |
| 0 | Low cost |
| 1 | Medium cost |
| 2 | High cost |
| 3 | Very high cost |

This is a **multiclass classification** problem because the target has four possible classes.

## 2\. Team and Member Roles Group 71
| Member | Entry No. |   Name  | Role |
| :---- | :---- |:----|:----|
| 1 | 2026EEB1328| ASHISH KUMAR | **Executive Lead**. Oversaw the entire project and made sure that we strictly follow the guidelines mentioned in the mini-project briefing , done data exploration as well as reviewed code of each member, assigned tasks, and ensured that every part of the project is completed on time. Also supervised the technical works such as maintaining the repository, executing git commands and resolving conflicts, reviewed the overall progress, made sure that coding, documentation, presentation, and video work are properly integrated. Ensured the successful completion of project |
| 2 | 2026AIB1038 | GAVINI JITESH YADAV | **PPT lead**. Prepared the PPT, Actively worked on evaluating the trained machine learning model by examining its predictions and interpreting the output to understand how effectively it classified  phones into their respective price categories based on their specifications. Analysed the predicted price categories, organized the results, and presented the model's outputs in an understandable and meaningful format using appropriate visual representations. Additionally, contributed to improving the quality, readability, and maintainability of the project's source code, particularly in the data exploration and data preprocessing sections. Added meaningful comments and explanations to important code segments to clarify their functionality and improve understanding for other team members and future users.
| 3 | 2026EEB1381 | MRINALIKA SINGH | **Video lead**. Planned the video such that each one of us gets sufficient time to explain our part in project, while strictly following the time limit given to us. Done the processing of video and uploaded it on YouTube for easy access. Started preprocessing of data for training our model. Imported the libraries { Numpy and pandas for data processing, matplotlib and seaborn for graphical visualisation and required  sklearn learn modules for model evaluation |
| 4 | 2026MCB1547 | MEENAKSHI | **Documentation lead**. Maintained the README, ensured that it contains every important information as mentioned in the mini project briefing. Handled the missing values in the training and testing samples by filling it with the median of the data. Using StandardScalar scaled the feature values so that their contribution in the model training is optimised. Using logistic regression from the sklearn trained the model on the training data which comprises 80% of our dataset |


## 3\. Dataset

The dataset is stored in `data/mobile_price.csv`.

- 2,000 rows  
- 20 input features  
- 1 target column: `price_range`    
- Five missing values are present in the feature columns. They are filled using the median of the training data.



## 3\. Project folder structure

```
AI101-Mini-Project-Group-71/
│
|── PPT
|    └── AI101_Group71_Presentation_Final_updated.pptx  
|
├── data/
│   └── mobile_price.csv
│
├── src/
│   ├── data_exploration.ipynb
│   └── data_preprocessing_training_evaluation.ipynb
│
├── README.md
└── requirements.txt
└── .gitignore
```

## 4\. Libraries used

- **Pandas:** read and explore the dataset  
- **NumPy:** numerical operations  
- **Matplotlib:** create graphs  
- **Seaborn:** create the confusion matrix heatmap  
- **Scikit-learn:** split data, scale features, train Logistic Regression and evaluate predictions

## 5. How to run the project

### Step 1 : Clone the Repository
1. Copy the link of the repository which we have submitted in the google form.
2. Open the folder in your desktop where you want to clone the repository.
3. Press 'Shift+ right click' and open gitbash terminal within that folder.
4. Write the command ``` git clone [repo link] ``` press enter
5. Repository in cloned sucessfully.

### Step 2: Open the repository in VS code and Install the required libraries (if not already installed)
In the VS code terminal run :
```bash
pip install -r requirements.txt
```

### Step 3: Explore the dataset

Open the data_exploration.ipynb , select the python kernel and run the cells(you can run all cells at once or run cells one by one.

This displays the dataset information, missing values, target distribution, summary statistics and graphs.

### Step 4: Train and evaluate the model

Similarly open the data_preprocessing_training_evaluation.ipynb and check the preprocessing of the data, training and model evaluation

This program:

1. Reads the dataset.  
2. Separates features (`X`) and target (`y`).  
3. Splits the data into 80% training and 20% testing data.  
4. Fills missing feature values using training-set medians.  
5. Scales the features using `StandardScaler`.  
6. Trains a multiclass Logistic Regression model.  
7. Predicts the classes for the test data.  
8. Calculates evaluation metrics and displays a confusion matrix.





## 6\. Understanding the model

### Features (`X`)

The 20 phone specifications, such as:

- `battery_power`  
- `ram`  
- `px_height`  
- `px_width`  
- `mobile_wt`  
- `int_memory`  
- `four_g`  
- `wifi`

### Target (`y`)

`price_range` is the value the model learns to predict.

### Train-test split

- 80% of the data is used for training.  
- 20% is used for testing.  
- `random_state=42` makes the split reproducible.  
- `stratify=y` maintains approximately the same class proportions in both sets.

### Missing values

The median of each feature is calculated from the training data and used to fill missing values in both training and testing data.

### Feature scaling

`StandardScaler` brings numerical features to a comparable scale. It is fitted on training data only, and the same scaler is used to transform testing data.

### Logistic Regression

`LogisticRegression(max_iter=1000)` learns to assign each phone to one of the four classes. The model predicts the class with the highest estimated probability.

## 7\. Model evaluation

The project calculates:

- **Accuracy:** proportion of all test predictions that are correct.  
- **Precision:** among predictions for a class, the proportion that truly belong to that class.  
- **Recall:** among actual examples of a class, the proportion correctly identified.  
- **F1-score:** harmonic mean of precision and recall.  
- **Classification report:** shows precision, recall, F1-score and support for every class.  
- **Confusion matrix:** compares actual classes (rows) with predicted classes (columns).

The program reports **macro average** and **weighted average**:

- Macro average gives each class equal importance.  
- Weighted average accounts for the number of test examples in each class.

