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
    new_dfSubjects=createMaskSubjectDataFrame(new_df)


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


  </div>
   

How to train the models on the data 

How to use one of your already trained models to predict unseen data 

How to evaluate the output 
