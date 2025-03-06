   Dataset:  https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

   
   
   
    Data: Analyzed a credit card transactions dataset, which was heavily imbalanced with very few fraud cases.

    EDA: Exploratory analysis revealed key distribution patterns, highlighting the importance of scaling the ‘Amount’ feature.

    Preprocessing: We applied normalization and selected relevant features (V1–V28 plus scaled Amount) for modeling.

    Unsupervised Approach: An Isolation Forest model was trained to isolate potential anomalies without relying on labels.

    Evaluation: We used a confusion matrix and classification report to measure how effectively anomalies were detected.

    Visualization: PCA projections and score distributions helped us interpret how the model separates fraud from normal transactions.

    Autoencoder Method: A deep learning approach was introduced to reconstruct normal data and flag high-error instances as fraud.

    Supervised Insight: We acknowledged that supervised models (e.g., Random Forest) can outperform unsupervised methods when labels are available.

    Challenges: Handling severe class imbalance and tuning model thresholds are critical to reducing false positives and false negatives.
    
    Conclusion: With careful preprocessing, model selection, and threshold optimization, anomaly detection can significantly enhance fraud prevention efforts.

