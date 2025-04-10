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
