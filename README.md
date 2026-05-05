# Sentence Contradiction Classification

**Author**: @Shakil Ahamed  
 

---

## Project Description
This project focuses on developing a machine learning model to classify pairs of sentences into one of three categories: **"Contradiction," "Entailment,"** or **"Neutral"** based on their semantic relationships. The model is trained on a labeled dataset and evaluated using various classification metrics.

---

## Dataset Information
The dataset consists of pairs of sentences labeled with their semantic relationship:
- **train.csv**: Labeled training data with columns `id`, `premise`, `hypothesis`, and `label`.
- **test.csv**: Unlabeled data for prediction.

The labels are:
- `0` = Contradiction (Sentences have opposite meanings)
- `1` = Neutral (Sentences are related but do not imply each other)
- `2` = Entailment (One sentence logically follows from the other)

---

## Project Steps

## 1. Exploratory Data Analysis (EDA)
- **Visualized the distribution of labels**:
  ![Label Distribution](/Distribution%20Labels.png)

- **Analyzed sentence structure (length, word distribution, common words)**:
  ![Word/Sentence Length](/wordLengthDistribution.png)

- **Checked for missing values or outliers**:
No missing values and  outliers found.
---

---

## 2. Text Preprocessing
- **Tokenization**:
![Tokenization](/tokenization.png)

- **Lowercasing**:
![Lowercase](/upercas%20to%20lower%20case.png)

- **Removal of stop words, special characters, and punctuation**:
![RemovalStopword](/remove_specialcharacter.png)

- **Stemming/Lemmatization**:
- Normalized words to their root forms.

- **Most Common Words**:
![MostCommonWord](/top_10MostCommonwordPremis.png)
![WordCount](/wordcount.png)

- **Feature Extraction**:
- Used TF-IDF, Word2Vec, or Transformer embeddings.

---

## 3. Model Creation
#### Baseline Models:
- **Random Forest**:
    ``` 
            precision   recall  f1-score   support
                0.35      0.40      0.38       851
                0.31      0.27      0.29       773
                0.38      0.36      0.37       800
    
    accuracy                        0.35      2424
    macro avg   0.35      0.35      0.35      2424
    weighte_avg 0.35      0.35      0.35      2424

    Accuracy: 0.3486
    ``` 
- **Decision Trees:**
    ```
            precision    recall  f1-score   support

                0.36      0.35      0.35    851
                0.32      0.35      0.33    773
                0.38      0.36      0.37    800

    accuracy                        0.35    2424
    macro avg   0.35      0.35      0.35    2424
    weighte_avg 0.35      0.35      0.35    2424

    Accuracy: 0.3519
    ```
- **XGBoost :**
    ```
    
              precision    recall  f1-score   support

                  0.38      0.53    0.44       851
                  0.34      0.25    0.29       773
                  0.44      0.38    0.41       800

    accuracy                      0.39       2424
    macro avg     0.39    0.39    0.38       2424
    weighted avg  0.39    0.39    0.38       2424

    Accuracy: 0.3899
    ```

### Neural Networks:
- **Custom ANN**:
        ```
        Test Loss: 3.5629
        Test Accuracy: 0.2690
        ```

### Advance Network : LSTM/GRU<br>

- **LSTM Model :**
    ```
    Test Accuracy: 0.3511  
    but this this time Consuming
    ```
- **Custom GRU Model :**
    ```
        Test Loss: 4.976,
        Test Accuracy: 0.3478
    ```
- Transformer-Based Models: Fine-tuned BERT/XLM-R.<br>
    - **Fine-tuned XLM  Model :***
        - I Choose XLM Model Cause This Data set are Multilingual
## 4. **Model Evaluation**
###  Computed accuracy, precision, recall, and F1-score.
   ```
    Accuracy: 0.3486
    Precision: 0.3474
    Recall: 0.3486
    F1-score: 0.3471
   ```
### Plotted a Confusion Matrix.
        ![ConfutionMatrix](/MatrixConfution.png)
### Calculated the Area Under the Receiver Operating Characteristic Curve (AUC-ROC) and
   ```Micro-averaged ROC AUC: 0.4460```
   
- Generated an AUC-ROC curve.
    ![Curve](/ROC-Curbe.png)

## 5. **Model Tuning and Optimization**<br>
### Experimented with different optimizers and activation functions.
- **Optimizer:**
   ```
    
    Adam Accuracy: 0.2586
    SGD Accuracy: 0.3378
    RMSprop Accuracy: 0.2953
   ```
- **Activation Functions:**
    ```
    ReLU Accuracy: 0.2624
    LeakyReLU Accuracy: 0.2809
    tanh Accuracy: 0.2871
   ```
- **Adjusted learning rate, batch size, and number of epochs**.

    ```
        Learning_rate    Batch_Size     Epochs    Test_Loss    Test_Accuracy
            0.0005          32           10        3.0729       0.2727
            0.0005          64           10        3.7990       0.2735
            0.0001          16           20        5.2685       0.2669
         

    ```
- **Used Grid Search or Random Search for hyperparameter tuning**
        
        ```
        Best Accuracy: 0.2776
        Best Parameters: {'learning_rate': 0.001, 'batch_size': 64, 'epochs': 10}
        ```

## Steps to Run the Code
1. Clone the repository:
 ```bash
 
    git clone https://github.com/aidevshakil/SentenceContradictionClassificationProject.git

 ```
2. Navigate to the project directory:
```bash
cd NLP
```

3.Run the training script:
```bash
sentence_Contradiction_Classification.ipynb
```

## 6. Model Evaluation Results
**Best Model:** XGBoost with an accuracy of ```38.99%```

- Confusion Matrix and  results directory.
![confutionMatrix](/MatrixConfution.png)
- AUC-ROC Curve are provided in the
``0.4460``

## 7. Additional Observations
- **Adam Optimizer** with ReLU Activation performed best among optimizers and activation functions.

- **XGBoost** outperformed other baseline models.

- **Transformer-based models** ( XLM) are recommended for multilingual datasets but require significant computational resources.


---
# Contact
For questions or collaborations, feel free to reach out:

**Name:** Shakil Ahamed

**GitHub:** [@Shakil Ahamed](https://github.com/aidevshakil/)




---
### Key Features of the `README.md`:
1. **Structured Sections**: Clear headings and subheadings for easy navigation.
2. **Visuals**: Embedded images for EDA and evaluation results.
3. **Code Snippets**: Properly formatted code blocks for reproducibility.
4. **Results**: Detailed metrics and observations for each model.
5. **Instructions**: Step-by-step guide to run the code.
---

