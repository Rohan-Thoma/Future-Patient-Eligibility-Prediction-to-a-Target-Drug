# Future-Patient-Eligibility-Prediction-to-a-Target-Drug
Predicting the eligibility of the patient to a particular target-drug given his/her medical history

## 🔶Detailed Blog explaining the whole case study is here:
* https://medium.com/@rohanvailalathoma/predicting-the-eligibility-of-a-patient-to-a-target-drug-in-next-30-days-using-deep-learning-36fc7c51e80d

## ⭐Introduction
The development of drugs is critical in providing therapeutic options for patients suffering from chronic and terminal illnesses. “Target Drug”, in particular, is designed to enhance the patient’s health and well-being without causing dependence on other medications that could potentially lead to severe and life-threatening side effects. These drugs are specifically tailored to treat a particular disease or condition, offering a more focused and effective approach to treatment, while minimizing the risk of harmful reactions.

## 🤖Business problem and constraints
The objective is to develop a predictive model which will predict whether a patient will be eligible*** for "Target Drug" or not in next 30 days. Knowing if the patient is 'eligible or not' will help physician treating the patient make informed decision on the which treatments to give. <br>
** - A patient is considered eligible for a particular drug when they have taken their first prescription for that drug. <br>
* <b> Objective :</b> Here our objective is to predict the percentage(probability) of eligibility of a given patient to TARGET_DRUG as correctly as possible.<br>
* <b> Constraints : </b> There is no strict latency constraints as this is not an immediate requirment like in internet application, but we need the models which are accurate since it is a medical application. The lack of latency constraints allow us to try out more powerful models like deep neural networks.

## 😷Dataset overview
We have the data in the form of below 2 files

1) Train.parquet — Dataset to be used for training

2) Test.parquet — Dataset to be used for testing

### Brief Description of the Dataset
The dataset in question contains a comprehensive collection of electronic health records belonging to patients who have been diagnosed with a specific disease. These health records comprise a detailed log of every aspect of the patients’ medical history, including all diagnoses, symptoms, prescribed drug treatments, and medical tests that they have undergone. Each row represents a healthcare record/medical event for a patient and it includes a timestamp for each entry/event, thereby allowing for a chronological view of the patient’s medical history.

## 💊Notebooks Overview
### 🍕<a href="https://github.com/Rohan-Thoma/Future-Patient-Eligibility-Prediction-to-a-Target-Drug/blob/main/EDA_part_1_Drop-out_rate_analysis.ipynb"> EDA_part_1_Drop-out_rate_analysis.ipynb </a> :
* This notebook contains the Exploratory data analysis PART -1 for drop off analysis.
* Drugs are generally administered/prescribed by the physicians for a certain period of time or they are administered at regular intervals, but for various reasons patients might stop taking the treatment . Consider the following example for better understanding: <br>
“ Let’s say you get a throat infection, the physician prescribes you an antibiotic for 10 days, but you stop taking the treatment after 3 days because of some adverse events.” <br>
In the above example ideal treatment duration is 10 days but patients stopped taking treatment after 3 days due to adverse events. Patients stopping a treatment is called drop-off.
* We want to study drop-off for “Target Drug”, the aim is to generate insights on what events lead to patients stopping on “Target Drug”. <br>
It is given that the ideal treatment duration for “Target Drug” is 1 year, so we come up with analysis showing how drop-off rate is varying as number of patients dropping off each month.

<img width='550' src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*04PaI-1y8hAVJ6EEBKEAUQ.png" >

### 🍕<a href="https://github.com/Rohan-Thoma/Future-Patient-Eligibility-Prediction-to-a-Target-Drug/blob/main/EDA_part_2_Patient_prescription_pattern_analysis_via_clustering.ipynb"> EDA_part_2_Patient_prescription_pattern_analysis_via_clustering.ipynb </a> :
* This notebook contains the code for EDA part-2 analysis for extraction of dominant prescription patterns from the data for deeper insight.
* A drug is generally administered to a patient in certain patterns or in regular intervals of time. <br>
For example Chemotherapy which is drug treatment in case of Cancer is generally given to patients in an interval 3–4 weeks, i.e. every 3–4 weeks patients are administered with the drug. <br>
Similarly to Chemotherapy, “Target Drug” is also administered/prescribed in certain patterns, we want to analyze in what patterns “Target Drug“ is administered/prescribed to patients, there might be multiple patterns in which “Target Drug” is administered/prescribed.

<img width="1000" src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*_TLbpbqKmgKwtCEVMXLZtg.png">

### 🍕<a href="https://github.com/Rohan-Thoma/Future-Patient-Eligibility-Prediction-to-a-Target-Drug/blob/main/Patient_Eligibility_Prediction_in_next_30days.ipynb"> Patient_Eligibility_Prediction_in_next_30days.ipynb </a> :
* This notebook contains the data manipulation for arranging in the required time series format along with usage of various deep learning models like LSTMs.
* 2 new features based in the results of the initial model testing were engineered to improve the score significantly.
* The training data was arranged in such a format so that all the events leading to the target drug before 30 days are only kept for training, since the model cannot know what happened in that period, since we are predicting for the future. This is done to ensure the practical robustness of the model and to avoid typical blunder of data leakage.
* Finally the network architecture designed is given below which gave an F1-score of 0.85 which is decent, and can be improved with inclusion of more features and complex models which is left for the future scope of the work.

### 🍗Final model architecture 

<img width="600" src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*S6QczX-rdg0ekXynau9uig.png">

### 😎🤟🏻Some useful reference links:

1. 🔗Connect with me on 🤝 LinkedIn : https://linkedin.com/in/rohan-vailala-thoma
2. 💼Check out my other case study blogs on 😎🤟🏻: https://medium.com/@rohanvailalathoma

  
  



