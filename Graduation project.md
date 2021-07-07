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
The data is composed of 664 files in **.edf** format, which contain difitalized signals of EEG, sampled to 256 samples per second and with a sesolution of 16 bits.  The files are grouped on  24 cwhich correspond to 23 pacients: 5 male which ages between 3 to 22 years and 17 women with ages between  1.5 to 19 years. Most of them are pediatric cases.

## Development

  ### Phase 1 - Identification of epileptic spikes using clustering models on EEG data 
    Data processing 
    The characterization of a spike is defined based on the next 4 variables:
      - initial_peak: It makes reference to the positive peak of the spike. 
      - final_peak: It is the negative peak of the spike.
      - width: It measures the duration of the spike.
      - height: It measures the potencial of the positive pike. 
    
    The result of processing the data is a .csv file which contains 3602157 of instances and 4 columns.
    Each instance in this file represents a epileptic spike. Down below it can be see a box diagram of the data. 

![image](https://user-images.githubusercontent.com/47225250/124827785-71814700-df44-11eb-8d0b-2584086dd461.png)

    
    
    
    
      
      
    

