# Classification of Insurance Legal Documents Using NLP and Deep Learning Approaches

 ### Abstract

This study explores the use of NLP and deep learning to analyze and classify legal documents, aiming to build an intelligent system that automates legal text organization 
and enhances workflow efficiency. 
The novel approach outlines the motivation, methodology, experiments, and results of the proposed approach, emphasizing the importance of a thorough evaluation and the 
insights gained from the experimentation process.

Keywords: Legal Document Classification (fraud, misrepresentation, non-disclosure, claims procedure/handling, indemnity), NLP, Machine Learning, Data Preprocessing, 
Performance Analysis, Compliance, Feedback. 

### 1.	Introduction
Legal document analysis is an essential aspect of legal practice but typically requires substantial time and human effort. 
This study introduces an innovative approach to automating this process through advanced Natural Language Processing (NLP) and deep learning techniques. 
The motivation arises from the growing volume of legal documents and the need to improve efficiency and accuracy in their management.
Legal practitioners increasingly face large collections of documents such as contracts, case law, legal opinions, and statutes creating a pressing demand for 
automated tools to streamline the review process. Traditional methods often fall short, leading to delays and potential omissions. 
The proposed solution utilizes NLP and deep learning to develop an intelligent system capable of understanding, classifying, 
and extracting meaningful insights from diverse legal texts.

# 2. Proposed Methodology
This section provides a detailed overview of the methodology, emphasizing the practical implementation of the proposed solution. 
It examines the selection of specific NLP techniques and deep learning architectures, along with the rationale behind these choices. 
Additionally, it discusses the preprocessing strategies employed to ensure the model’s adaptability to diverse legal document formats.

### 2.1 Data Collection
To train and evaluate the model, reference is made to the INSURANCE CASES DIGEST VOLUME 1, 2025 obtained from the Insurance Regulatory Authority of Uganda, 
a body instituted with the primary objective of promoting and facilitating the maintenance of a sound, effective, fair, transparent and stable insurance sector in Uganda. 
The Insurance Cases Digest contains a broad collection of legal documents, including court judgments, legal opinions, and statutes. 
The Digest informs readers on contemporary insurance issues, offering insights into the Authority’s mandate, competition and consumer protection law and 
jurisprudence development. 
It serves as a quick reference of landmark cases from courts, the Insurance Appeals Tribunal and the Complaints Bureau that have shaped insurance law and practice. 
Its selection was motivated by the richness and variety of its content, providing a representative sample of the linguistic and structural variations found in legal texts.

### 2.2 Data Cleaning
Prior to model development, the data underwent a thorough cleaning process to ensure its quality, consistency and reliability.

 ##### a. Unique Character Analysis
Analysis of legal texts identified special characters, symbols and formatting elements that lacked semantic value. 
By removing or encoding unique characters, the focus shifted to linguistic content. Examples include links, numbers and miscellaneous symbols. 

### 2.3.Preprocessing for NLP 
To enhance the model's adaptability to various legal document formats, a robust preprocessing pipeline was implemented.

 #### a. Tokenization
 The legal texts were tokenized into words (smaller units) to support NLP analysis, with the tokenisation strategy considering the specialized terms and 
 phrases that carry significant legal meaning. 

 #### b. Stopword Removal
 Common legal stopwords that add little meaning were identified and removed to reduce noise and help the model focus on substantive legal content.

 #### c. Lemmatization
 Lemmatization was applied to reduce legal terms to their base forms, ensuring uniform treatment of different inflections 
 and improving the accuracy of legal language analysis.

# 3. Model Evaluation
The model adopts a systematic approach to model selection using a Logistic Regression classifier. 
A pipeline structure streamlines both preprocessing and modelling processes, yielding a performance score of 87.87%. 
Among the analysed categories, “claims procedure” demonstrated the strongest predictive performance. 
To enhance interpretability, the model leveraged Eli5, LIME, and SHAP, which consistently identified influential features such as claims, payment, payable, delays, 
premium and settlement. These insights indicate that the Digest captured recurring discrepancies in insurers’ claims procedures, particularly cases where premiums had 
been paid but claim settlement was delayed. 
The findings further showed that fraud was the leading contributing factor to these delays, followed by misrepresentation.

# 4. Discussion
 #### 4.1. Precision, Recall, and F1-Score  
Precision: Reflects the accuracy of positive predictions. For instance, the model achieves high precision for 'claims procedure' (0.95), 
indicating that when it predicts this class, it is usually correct. 

However, some classes like ' misrepresentation, fraud & indemnity' (0.00) have a very low precision. 
Recall: Represents the model's ability to capture all positive instances. 

High recall values, such as for 'Miscellaneuous ' (1.00), indicate effective identification of true positives. 
The implication is that the model is over-predicting certain classes while failing to discriminate accurately between closely related legal themes. 
However, classes like 'misrepresentation', ‘indemnity‘ and 'fraud’ have a recall of 0.00, suggesting that the model struggles to identify instances of these classes. 
F1-Score: The harmonic means of precision and recall. It provides a balanced measure of a model's overall performance. 

High F1 scores are observed for ' Miscellaneuous' (0.93) and 'claims procedure' (0.72).
While the model demonstrates high precision and recall for some classes. 
The overall accuracy is 88%, indicating the proportion of correctly classified instances. 

However, the macro and weighted averages for precision, recall, and F1-score suggest that the model's performance greatly varied, 
emphasizing the need for further investigation, especially in addressing class imbalances and improving classification for certain classes. 
The report serves as a valuable tool for understanding the model's strengths and weaknesses, guiding potential refinements for enhanced performance in legal document 
classification. 
