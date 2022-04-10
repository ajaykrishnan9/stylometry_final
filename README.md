# Documentation:

<b>Installing all requirements </b>
>!pip install spacy transformers sentencepiece datasets scikit-learn pandas

>!python -m spacy download it_core_news_sm en_core_web_sm

<b>How to preprocess the data so it is in the correct format </b>
>**You dont need to call PreProcess seperately. It will be internally called.**
><div>
    
<b>For train data set</b>

    from datasets import load_dataset
    dataDir='dataset/IK_NLP_22_PESTYLE'
    dataset = load_dataset("GroNLP/ik-nlp-22_pestyle", "full", data_dir=dataDir)
    training_whole_dataset = dataset["train"]
    new_df= pd.DataFrame(data=training_whole_dataset)
    #Preprocessing is done during creating below dataframe   
    new_dfMain=createMaindataFrame(new_df)


<b>For mask_subject test data</b>
    
    dataDir='dataset/IK_NLP_22_PESTYLE'
    dataset_test_subject = load_dataset("GroNLP/ik-nlp-22_pestyle", "mask_subject", data_dir=dataDir)
    test_subject = dataset_test_subject["test"]
    test_subject_df = pd.DataFrame(data=test_subject)
    #Preprocessing is done during creating below dataframe 
    test_subject_pre_df=createMaskSubjectDataFrame(test_subject_df)

<b>For mask_modality test data</b>
    
    dataDir='dataset/IK_NLP_22_PESTYLE'
    dataset_test_modality = load_dataset("GroNLP/ik-nlp-22_pestyle", "mask_modality", data_dir=dataDir)
    test_modality = dataset_test_modality["test"]
    test_modality_df = pd.DataFrame(data=test_modality)
    #Preprocessing is done during creating below dataframe 
    test_modality_pre_df=createMaskModalityDataFrame(test_modality_df)

<b>For mask_edit test data</b>
    
    dataDir='dataset/IK_NLP_22_PESTYLE'
    dataset_test_time = load_dataset("GroNLP/ik-nlp-22_pestyle", "mask_time", data_dir=dataDir)
    test_time = dataset_test_time["test"]
    test_time_df = pd.DataFrame(data=test_time)
    #Preprocessing is done during creating below dataframe 
    test_time_pre_df=createMaskTimeDataFrame(test_time_df)
    
    
<b>Models for subject, modality and edit time prediction</b>
    
    Following notebooks are used for prediction of the subject, model and edit time. In all the notebook following steps are done:
    Step 1 - Data is loaded
    Step 2 - Pre-processed according to the problem statement is performed 
    Step 3 - Modeling of the algorithm as well as prediction is done based on the train test split . 
    Step 4 - Finally all the models are evaluated on their respective mask test dataset.
    
    Subject -  "Stylometry_Subject_Prediction" notebook is used for predicting the subject.
    Modality - "Stylometry_Modality_Prediction" notebook is used for modality prediction.
               "Stylometry_Modality_Prediction-Machine_Translation_Combined" notebook is used for modality prediction when machine translations are combined.
    Edit time -"Stylometry_Edit_time_Prediction" - notebook is used for edit time prediction. 
    
<b>Data Analysis</b>  
    
    Technical and Temporal Analysis - "stylometry_technical_temporal_analysis" - notebook is used for this analysis effort.
    Cognitive Analysis - "stylometry_cognitive_analysis" - notebook is used for this analysis effort.

  </div>
   
