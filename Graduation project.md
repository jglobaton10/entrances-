# Predicting epileptic seizures using epileptic spikes characterization and EEG data 

## Objectives

The main objective of the project is to predict epileptic seizures using machine learning techniques from
EEG data that comes from the research done by the Children's Hospital Boston in
patients with epilepsy and the results obtained from the typification of epileptic spikes.
As well as analyzing the influence that have different types of epileptic spikes  
on the prediction of the seizures generated. 

  1. Defining variables that allow to characterize the epileptic spikes and later on cluster them.
  2. Typifying the epileptic spikes using non supervised machine learning with the objective of enriching the EEG data that will be used on the predictive models.
  3. Defining variables that allow to characterize the data in the EEG files to be able to train predictive models.
  4. Analyzing the impact of the epileptic spikes in the prediction of epileptic seizures and interpreting the results.
  5. According to the metrics, evaluating the possibility of using the results on local hospitals.
 
## Requirements and Restrictions 
## Requirements 
  - The program needs to be able to process the 400 .edf files, identify the  spikes in the EEG signals according to an specific characterization and  process the signals to use them to train the predictive models. 
  - Being able to predict epileptic crisis from the processed signals of the EEG and the typifycation of epileptic spikes.
  - The machine learning models used to develop the previous tasks should fully interpretable.
## Restrictions 
  - The time to develop the project is only 4 months and its scope should according to this.  
  - The project will completely developed on Python in Jupyter Notebooks.
  - The only data available comes from the researcg done by the Children's Hospital Boston.  

## Data 
The data is composed of 664 files in **.edf** format, which contain difitalized signals of EEG, sampled to 256 samples per second and with a sesolution of 16 bits.  The files are grouped on  24 cwhich correspond to 23 pacients: 5 male which ages between 3 to 22 years and 17 women with ages between  1.5 to 19 years. Most of them are pediatric cases. Each case contains 9 to 42 files and each files contains 23 EEG signals. Finally,  from 664 only 129 present at least one epileptic crisis. 

## Development

  ### Phase 1 - Identification of epileptic spikes using clustering models on EEG data 
  ### Data processing 
  The characterization of a spike is defined based on the next 4 variables:
  - initial_peak: It makes reference to the positive peak of the spike. 
  - final_peak: It is the negative peak of the spike.
  - width: It measures the duration of the spike.
  - height: It measures the potencial of the positive pike. 
    
  The result of processing the data is a .csv file which contains 3602157 of instances and 4 columns.Each instance in this file represents a epileptic spike. Down below it can be see a box diagram of the data. 

![image](https://user-images.githubusercontent.com/47225250/124827785-71814700-df44-11eb-8d0b-2584086dd461.png)
   All the columns contain outlayers. However, it was decided that they will not be removed because they might have relevancy for predicting the crisis.  
 
 
  ### Training of clustering models 
  Previously to train the models  the data was normalized using  a **MinMaxScaler** from sklearn, which uses the next formula. 
  ![image](https://user-images.githubusercontent.com/47225250/124828427-3f241980-df45-11eb-9643-c022ca6f8bd9.png)

  Based on the state of the art the best model for the clustering spikes was affinity propagation, but the  data set is too large and training that model with a sample of only 500000 instances takes around 5 hours. Therefore, it is used **k-means** and **AgglomerativeClustering**. The models are evaluated using the silhoute coefficient.
![image](https://user-images.githubusercontent.com/47225250/124828822-c40f3300-df45-11eb-97f8-506b45c024fd.png)

  The best result is obtained when the number of clusters is 4. Using this 4 different types of spikes were identify. 
![image](https://user-images.githubusercontent.com/47225250/124829002-0769a180-df46-11eb-9c76-fdd747bbef38.png)

  ### Spikes characterization
  ![image](https://user-images.githubusercontent.com/47225250/124829244-5d3e4980-df46-11eb-8a91-5e25cd39e4dc.png)
  ![image](https://user-images.githubusercontent.com/47225250/124829164-3ed84e00-df46-11eb-9903-2aaf2fc18867.png)
  
  ### Phase 2 - Predicting epileptic crisis using machine learning models for classification
  The goal of this part of the project is being able to predict the different states of an epileptic crisis. With this in mind two different scenarios were stablished. In the fisr the objective variable can take for different values: normal, pre_ictal, ictal and inter_ictal. While in the second the objective variable can only take the values normal and pre_ictal.  The goal of the first scneratio is to evalue the importance of the different variables having the four states. The objective of the second one is to  decide which variables are more relevant when deciding if a pacient is about to have an epileptic crisis.  
  
  ### Data processing 
  
  The characterization of the waves was made based on the next variables:
  - Number of spikes 
  - Potency in the band α
  - Potency in the band δ
  - Potency in the band γ
  - Potency in the band θ
  - Number of peaks 
  - Number of type 1 spikes 
  - Number of type 2 spikes 
  - Number of type 3 spikes 
  - Number of type 4 spikes 
  - label
  
  For this part of the project two algorithms were developed. One of the other will be applied depending wether the file has an epileptic crisis or no.  
  
  Algorithm for files with no epileptic crisis 
  
  ![New Picture (8)](https://user-images.githubusercontent.com/47225250/124832685-05eea800-df4b-11eb-8988-363c69b872ed.png)
  
  Algorithm for files with epileptic crisis 
  
  ![New Picture (7)](https://user-images.githubusercontent.com/47225250/124832672-fcfdd680-df4a-11eb-9744-ad0213912e6f.png)
  
  The result of processing the data is a .csv file with 227167 instances and 11 columns. Each instance corresponds to 5 seconds of digitalized EEG signal. In regards to the labels the instances have the following distribution.
  
  ![image](https://user-images.githubusercontent.com/47225250/124839876-a945ba00-df57-11eb-93de-973dbec4ffdd.png)
  
  ### Training of classification models
  Before of training the models the data was normalize with a MinMaxScaler. Additionally, the data was splitted in train and test with 20% for test.  For this project the models chose were DecissionTreeClassifier and RandomForestClassifier from **sklearn** for both scenarios.  
  
  The parameters that will be tunned with **GridSearchCV** are:
  - criterion
  - splitter
  - max_depth
  - max_features
  - min_sample_split
  - n_stimators: Only for RandomForestClassifier
  The models with the best parameters using the f1_score as evaluation metric are shown down below.
  
  ![image](https://user-images.githubusercontent.com/47225250/124841202-b4e6b000-df5a-11eb-80e7-d665e41f6153.png)
  ![image](https://user-images.githubusercontent.com/47225250/124841272-da73b980-df5a-11eb-9075-195af7b1cf23.png)
  
  Based on these results the best model is RandomForestClassifier in both scenarios. 
  
  ## Results 
  
  ### Scenario 1
  In this scenario the most important feature is the number of spikes of type 1 and n_peaks. 
  ![image](https://user-images.githubusercontent.com/47225250/124841626-acdb4000-df5b-11eb-9cf9-e8963b5c7468.png)
   
  
  ### Scenario 2
  In this case, the most important features are those related with the power in the different bands. In this case the most important is the gamma power.   
  ![image](https://user-images.githubusercontent.com/47225250/124841657-ba90c580-df5b-11eb-9e9e-fc6fb65b89e1.png)
  
The whole document can be seen the following [link](https://drive.google.com/file/d/12vShKLpNOPJgqLowIJrtdsnZZcULjBnp/view?usp=sharing)
    
    
    
    
      
      
    

