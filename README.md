# Header1 Project: Using NLP for Requirements Engineering for Data Management Software

Source data: Stackoverflow question and answers concerning Azure Data Factory

Link to data source: https://data.stackexchange.com/stackoverflow/query/new

Link to generated schema: https://dbdiagram.io/d/6448f5b26b3194705139098b

## Header2 Abstract

This project is a combination of human analysis, unsupervised and supervised machine learning, as well as the artificial intelligence GPT4. It employs Natural Language Processing (NLP) to analyze questions and answers from StackOverflow concerning Azure Data Factory (ADF). The project's aim is to derive topics and extract functional and non-functional requirements for operating within ADF.

### Header3 Methodology: 
The project leverages SQL queries on StackExchange to gather data. This data is then transformed into pandas dataframes in Python. Through a combination of traditional NLP, quantitative keyword analysis, supervised machine learning and GPT-4 prompts, the project:
    - Generates datasets and sub-datasets that provide insights into requirements for data management and pipeline design in ADF.
    - Establishes topics related to data management and pipeline design in ADF using Latent Dirichlet Allocation (LDA).
    - Identifies pertinent entities, nouns, and verbs within these topics with the aid of spaCy.
    - Gaugee sentiments concerning these topics using Vader sentiment analysis.
    - Validates the most significant topic found through unsupervised machine learning (LDA) with supervised machine learning algorithms.
    - Uses GPT-4 prompts to interpret the numeric results of LDA, Vader Sentiment Analysis, and spaCy extractions in terms of requirements engineering for ADF.
    - Implements a coherent code architecture using GPT-4 prompts for generating code aligned with this architecture


### Header3 Findings:
- The most significant impact on identifying relevant topics within questions about Azure Data Factory was achieved through manual comparison of quantitative keywords.
- Once a sub-dataset was defined using keywords as filters, the LDA effectively identified the most prominent topic within the dataset.
- This topic, named "Data Management in Pipelines" by GPT-4, was validated by various unsupervised machine learning models.
- Based on the results of quantitative NLP analysis, GPT-4 defined the following functional and non-functional requirements mentioned by users on StackOverflow:
- Functional Requirements identified by GPT4: 
    - Data Identifier Management: Requirement for the efficient handling of customer identifiers in the data pipelines.
    - Requirement for managing taxonomy identifiers effectively within the pipelines.
    - Data Staging: Requirement to handle 'staging' areas or concepts effectively in the data pipelines.
    - Message Identifier Management: Requirement for the effective management of message identifiers in the data pipelines.
    - Data Pipeline Operations: Requirement for improved handling and management of the key elements within Azure Data Factory (data, columns, pipelines, values, tables, activities, files)
- Non-Functional Requirements identified by GPT4 were: 
    - Usability: Requirement for the platform to be user-friendly and easy to use.
    - Operational Efficiency: Requirement for the platform to efficiently perform basic operations like getting and adding data
    - Support and Documentation: Requirement for better support and documentation to aid users in their attempts to use the platform.


### Header3 Conclusion: 
The project has provided a solid starting point for requirement engineers seeking an overview of user pain points while working with Azure Data Factory. The dataset that has been generated can be utilized for further investigations.

From a methodological perspective, the objective was to establish a consistent code architecture while exploring 'collaboration' with GPT4. The resulting LDA model has been thoroughly tested in numerous variations and is deemed sufficiently accurate for the purposes of this project. However, the training of unsupervised machine learning models could be further improved. These models currently exhibit slight overfitting and predict with an accuracy of 87%. There is also room for refactoring within the code itself. 


### Header3 Most Relevant Notebooks
01adf_query_whole_data_set.ipynb (Generates the preprocesses the data from Stackoverflow)
02adf_query_keyword_filter.ipynb (Filters the data, performs Latent Dirichilet Allocation)
03_svm.ipynb (validates most relevant topic found through LDA using Support Vector Machines)
04_logistic_regression_count_vectorizer.ipynb (validates most relevant topic found through LDA using Logistic Regression)
05_RNN.ipynb (validates most relevant topic found through LDA using RNN)
