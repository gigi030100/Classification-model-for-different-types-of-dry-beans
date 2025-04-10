# Classification-model-for-different-types-of-dry-beans

My project aims to utilise machine learning techniques to predict and classify different types of dry beans. The data used to build the following machine learning models can be downloaded from the link: https://archive.ics.uci.edu/dataset/602/dry+bean+dataset 

<img width="493" alt="Screenshot 2025-04-10 at 15 57 09" src="https://github.com/user-attachments/assets/7e2f6e8d-a990-4c33-82e6-f5a29b99a111" />

## Methodology

### Data pre-processing and preliminary analysis
Data was checked for missing to which we found none. However, 68 duplicated rows were removed to avoid adding extra weights on specific features, thus avoid bias when training our machine learning model. Thus, 13,543 data instances remain. 

Figure 1: Data distribution of each type of dry beans (7 classes in total)

<img width="399" alt="Screenshot 2025-04-10 at 16 05 31" src="https://github.com/user-attachments/assets/29b52ced-a11a-4919-9470-33d6e5985194" />

Figure 1 clearly shows Bombay bean type had the least number of data recorded, limitting its representativeness in the data. Hence, sythentic minority oversampling was used to create new data instances of the bombay bean class using existing data.

Histograms also illustrated the non-normal distribution of each class of dry bean feature. Z-score standardisation was used to normalise data features and improve predictive performances of the machine learning models developed here that are sensitive to different data scales. 

The dry beans "class" column was relabelled via label encoding as ML models require numerical variables. 

### Feature selection
A correlation plot was used to determine highly positive correlation features of the dry beans classes. Fetures that have 0.9 correlation score were removed to minimise model overfitting. 

## Developing Supper Vector Machine model
Dry beans cleaned dataset was split into training and testing set by a ratio of 80:20 respectively. The training set was furter split into training and validation set by a ratio of 90:10 respectively. Thus, we have training, validation, and testing data subsets. Default hyperparameters of the SVM model from the sklearn library was used (see Table 1). 

<img width="492" alt="Screenshot 2025-04-10 at 16 23 48" src="https://github.com/user-attachments/assets/046c93ac-bb62-40c7-ba91-88a52f605fc5" />

### SVM model evaluation
F1 score and the confusion matrix was used to assess predictive performance. 

The performance of the SVM model with default hyperparameter value was evaluated on the validation set first to avoid overfitting. Hyperparameter values were then tuned using the training set to find the optimal combination of hyperparameter values using GridSearchCV with a 10-fold cross validation. Table 3 shows the range of hyperparameter values in the search space. 

Table 3:

<img width="748" alt="Screenshot 2025-04-10 at 16 32 25" src="https://github.com/user-attachments/assets/e511869c-6e02-4655-a2bb-ea04de810c41" />

Upon finding the optimal combination of hyperparameter values, these values were then trained on the a combination of training and validation dataset to ensure new model is trained on unseen data and reduce overfitting. This optimised model was then evaluated on the testing dataset.

## Results
The model exhibited an average f1 score of 0.95


<img width="826" alt="Screenshot 2025-04-10 at 16 35 57" src="https://github.com/user-attachments/assets/d4a13c77-7aaa-473c-866f-9e0151805b51" />






