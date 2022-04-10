# Documentation:

<b>Installing all requirements </b>
>!pip install spacy transformers sentencepiece datasets scikit-learn pandas

>!python -m spacy download it_core_news_sm en_core_web_sm

<b>How to preprocess the data so it is in the correct format </b>
>**You dont need to call PreProcess seperately. It will be internally called.**
><div>
    
<b>Step 1 (Loading dataset):</b>

    dataDir=''
    #  dataType='full'             use 'full'for train
    #  dataType='mask_subject'     use 'mask_subject','mask_modality', 'mask_time' for test
    dataType='full'
    dataset = load_dataset("GroNLP/ik-nlp-22_pestyle", dataType, data_dir=dataDir)

<b>Step 2 (creating data frame):</b>

    # split='train'    or    split='test' 
    split='train'      
    data = dataset[split]
    new_df = pd.DataFrame(data=data)

<b>Step 3 (PreProcessing):</b>

    if dataType=='mask_subject': 
        nnw=createMaskSubjectDataFrame(new_df)
    elif dataType=='mask_modality':
        nnw=createMaskModalityDataFrame(new_df)
    elif dataType=='mask_time':
        nnw=createMaskTimeDataFrame(new_df)
    elif dataType=='full':
        nnw=createMaindataFrame(new_df) 
    nnw


  </div>
   

How to train the models on the data 

How to use one of your already trained models to predict unseen data 

How to evaluate the output 
