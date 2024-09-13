# Advanced De-identification of Clinical Texts using Large Language Models

## 📚 Overview

This project explores the use of Large Language Models (LLMs) for de-identifying clinical texts. The system anonymizes personally identifiable information (PII) in medical records by leveraging advanced transformer-based models (e.g., BioBERT) alongside rule-based techniques to enhance the accuracy of the de-identification process.

## Features

- **Transformer-Based Models**: Uses state-of-the-art LLMs like BioBERT for effective entity recognition.
- **Rule-Based De-identification**: Incorporates rule-based approaches for improved recall.
- **Custom De-identification**: Provides options for either redaction or replacement of sensitive data.
- **Risk Assessment**: Evaluates the re-identification risk after de-identification based on the uniqueness of entities.

## 🧠 Dataset Details

The dataset used in this project is provided by the i2b2/UTHealth initiative and managed under the n2c2 challenges hosted by the Department of Biomedical Informatics at Harvard Medical School. Access to this dataset requires approval due to the sensitive nature of the data.

### Accessing the Dataset

1. **Open the [N2C2 NLP portal](https://portal.dbmi.hms.harvard.edu/projects/n2c2-nlp/)**:

    - Create an account and apply for access to the datasets.
    - Once access is granted, download the following datasets from the “2014 De-identification and Heart Disease Risk Factors Challenge” folder:
        - Training Data: PHI Gold Set 1
        - Training Data: PHI Gold Set 2

2. **Combine the datasets**:

    - Copy the contents of `Training Data: PHI Gold Set 2` and paste them into `Training Data: PHI Gold Set 1`.

3. **Copy the consolidated dataset** to `dataset and website\i2b2` in the downloaded GitHub folder.

## 🔄 Reproducing the Experiments

### Requirements

To reproduce the experiments, set up Google Colab with the following libraries:

- `Flask`
- `pandas`
- `matplotlib`
- `stanza`
- `transformers`
- `nltk`
- `-g localtunnel`
- `torch`
- `scikit-learn`
- `tensorflow`
- `tensorflow_hub`
- `sklearn_crfsuite`
- `keras==2.6.0`
- `keras_preprocessing`
- `seqeval`
- `ipykernel`
- `Python 3.7`

This project is intended to run in **Google Colab**, and it is pre-configured to work in that environment. 
  
### Model Training

1. Clone this repository in Google Colab.
   ```bash
   git clone https://github.com/DhivinShaji/Advanced-De-identification-of-Clinical-Texts-using-Large-Language-Models.git
   ```
   
2. Navigate to the project directory.

    ```bash
    cd .\Advanced-De-identification-of-Clinical-Texts-using-Large-Language-Models
    ```
    
2. Open the `training_biobert.ipynb` notebook in Google Colab.

3. Ensure that the Colab runtime is set to Python 3.7.

4. Execute the notebook cells to install dependencies and run the de-identification pipeline.


### 📊 Running the Project

To run this project on **Google Colab**:

1. Clone this repository in Google Colab.
   ```bash
   git clone https://github.com/DhivinShaji/Advanced-De-identification-of-Clinical-Texts-using-Large-Language-Models.git
   ```
   
2. Navigate to the project directory.

    ```bash
    cd .\Advanced-De-identification-of-Clinical-Texts-using-Large-Language-Models
    ```
    
2. Open the `Deidentification_BioBert.ipynb` notebook in Google Colab.

3. Ensure that the Colab runtime is set to Python 3.7.

4. Execute the notebook cells to install dependencies and run the de-identification pipeline.

5. Copy the provided URL and paste it into your web browser.

6. The website will load and can be used to de-identify documents.



### NOTE: 
The only folders/files changed/added to the older MASK version are: 
1. "dataset and website"- where the dataset can be placed and website is built and run on flask servers.
2. "ner_plugins"- "NER_BioBERT.py" file is added
3. "Models"- Once the model is trained, the NER_BioBERT is saved in the Models file
4. In the root folder 4 files were added, "extractcounts.py"(to analyse the entity distribution in the dataset), "name extraction.py"(extract all the names, locations and professions from the dataset to create base dictionaries), requirements.txt (to save all the required packages with their respective versions compatible with Python 3.7.9) and model_performance.py (to create heatmap on the entity level performance of multiple models)
