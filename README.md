1.TITLE
Name: Somen Senapati
Program: IITG x Masai – Module III Capstone Project
Dataset: Stanford IMDB Movie Review Dataset

2.PROBLEM STATEMENT
Online reviews contain valuable opinions that influence consumer decisions. However, manually analyzing thousands of reviews is time-consuming. A machine learning model is needed to automatically classify text-based reviews as positive or negative based on sentiment.

3.OBJECTIVE
To preprocess raw movie review text for sentiment analysis  
To extract features using TF-IDF  
To train and compare SVM models with different kernels  
To evaluate performance using standard classification metrics  
To analyze results and identify limitations

4.DATASET
The Stanford IMDB Large Movie Review Dataset was used in this project. It contains 50,000 labeled movie reviews evenly split into training and testing sets. Each review is labeled as either positive or negative, making it suitable for binary sentiment classification.

5.APPORACH
The project follows a classical machine learning pipeline. First, the raw text data is cleaned and preprocessed. Next, TF-IDF is used to convert text into numerical features. Support Vector Machine classifiers with different kernels are then trained and evaluated. Finally, model performance is compared to select the most suitable approach.

6.METHODOLOGY
Data Preprocessing:
Missing values were handled by replacing null entries with empty strings. Text was converted to lowercase, and punctuation and special characters were removed. Stopwords were removed using the NLTK stopword list; however, negation words such as “not”, “no”, and “nor” were intentionally retained, as they play a crucial role in sentiment interpretation. Lemmatization was applied to reduce vocabulary size and improve generalization.

Feature Extraction:
TF-IDF vectorization was applied to convert cleaned text into numerical features. Initially, the TF-IDF vocabulary size was limited to 5,000 features, which provided a strong baseline performance. Subsequently, the feature size was increased to 10,000, resulting in improved classification accuracy from ~0.89 to ~0.91. This indicated that a richer vocabulary helped capture additional sentiment-bearing terms. Therefore, 10,000 TF-IDF features with unigrams and bigrams were selected for the final model.

Model Training:
Support Vector Machines were trained using Linear, Polynomial (degree 3), and RBF kernels. Class weight balancing was applied to improve robustness.



7.RESULTS 
The performance of the Support Vector Machine (SVM) models was evaluated using Accuracy and F1-score on the test dataset.

Model Performance Comparison
Kernel	Accuracy	F1-score
Linear SVM	0.9007	0.90
Polynomial SVM	0.8749	0.87
RBF SVM	0.9054	0.91
Observations

The RBF SVM achieved the highest accuracy and F1-score.

The Linear SVM demonstrated comparable performance with significantly lower computational cost.

The Polynomial SVM showed lower performance, likely due to increased model complexity.

Based on these results, Linear SVM was selected as the final model due to its efficiency and scalability for high-dimensional text data.


8.INSIGHTS
The experimental results indicate that kernel selection plays a significant role in SVM-based sentiment classification. The RBF kernel achieved the highest accuracy and F1-score, demonstrating its ability to model non-linear decision boundaries effectively. However, the Linear SVM delivered comparable performance with substantially lower computational cost, making it more suitable for large-scale text data. The Polynomial kernel showed comparatively lower performance, likely due to increased model complexity, which is less effective for high-dimensional sparse TF-IDF representations. Additionally, increasing the TF-IDF feature size from 5,000 to 10,000 improved model performance, highlighting the importance of adequate vocabulary coverage in capturing sentiment-bearing terms.

9.LIMITATIONS
The TF-IDF representation treats text as a bag of words and does not capture contextual or semantic relationships between words.
The model struggles with sarcasm, irony, and implicit sentiment, as these require deeper linguistic understanding.
Non-linear SVM kernels, particularly the RBF kernel, are computationally expensive when applied to large, high-dimensional text datasets.
The performance of the model depends on manual feature engineering choices such as vocabulary size and stopword selection.
The system supports only binary sentiment classification and does not handle neutral or fine-grained sentiment categories.


10.CONCLUSION
This project demonstrates the effectiveness of Support Vector Machines combined with TF-IDF features for sentiment analysis of movie reviews. Through systematic preprocessing, feature extraction, and kernel-wise evaluation, the models achieved strong classification performance. While the RBF kernel produced the highest accuracy and F1-score, the Linear SVM was selected as the final model due to its comparable performance and superior computational efficiency. Overall, the results confirm that Linear SVM provides a robust and scalable solution for large-scale sentiment classification tasks using traditional machine learning approaches.
