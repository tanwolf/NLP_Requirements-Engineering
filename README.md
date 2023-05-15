# Using NLP for Requirements Engineering: Identifying Pain Points of Data Management in Azure Data Factory

Source data: Stack Overflow question and answers concerning Azure Data Factory (ADF)

Link to data source: 
Stack Exchange Inc. (2023). Stack Exchange Data Explorer [SQL query on Stack Overflow data]. Available at: https://data.stackexchange.com/stackoverflow/query/new

Link to generated schema: https://dbdiagram.io/d/6448f5b26b3194705139098b

## Abstract
This project is a collaboration between an experienced human text data analyst, gpt4, as well as unsupervised and supervised machine learning algorithms. The goal of this project is to find out how these four "collaborators" can find new ways of analyzing and interpreting large amounts of text data. This project employs Natural Language Processing (NLP) to analyze questions and answers from Stack Overflow concerning Azure Data Factory (ADF). GPT4 is then prompted to derive functional and non-functional requirements for data management within ADF from the NLP results. GPT4 also identifies keywords representing these requirements. These keywords can be used as filters to further analyze the identified requirements.  

> **GPT4 Prompt:** Considering the results of the LDA, the Vader Sentiment Analysis and the spaCy extractions as well as the Certified Professional for Requirements Engineering (CPRE) certification: Which functional and non-functional requirements are expressed by the users on Stack Overflow concerning Azure Data Factory? List the requirements for each of the LDA Topics.

> **GPT4 Prompt:** For each topic generate keywords which represent functional and non functional requirements. For each keyword summarize which requirement it represents.

> **GPT4 Prompt:** Categorize the requirements for each topic.

### Methodology: 
The project leverages SQL queries on StackExchange to gather data. This data is then transformed into pandas dataframes in Python. Through a combination of traditional NLP, quantitative keyword analysis, supervised machine learning and GPT-4 prompts, the project:
    * Generates datasets and sub-datasets that provide insights into requirements for data management and pipeline design in ADF.
    * Establishes topics related to data management and pipeline design in ADF using Latent Dirichlet Allocation (LDA).
    * Identifies pertinent entities, nouns, and verbs within these topics with the aid of spaCy.
    * Gauges sentiments concerning these topics using Vader sentiment analysis.
    * Validates the most significant topic found through unsupervised machine learning (LDA) with supervised machine learning algorithms.
    * Uses GPT-4 prompts to interpret the numeric results of LDA, Vader Sentiment Analysis, and spaCy extractions in terms of requirements engineering for ADF.
    * Implements a coherent code architecture using GPT-4 for generating code 

### Findings:
* The most significant impact on identifying relevant topics within questions about Azure Data Factory was achieved through manual comparison of quantitative keywords.
* Once a sub-dataset was defined using keywords as filters, the LDA effectively identified the most prominent topic within the dataset.
* This topic, named "Data Management in Pipelines" by GPT-4, was validated by various unsupervised machine learning models.
* Based on the results of quantitative NLP analysis, GPT-4 defined the following functional and non-functional requirements mentioned by users on Stack Overflow:
* Functional Requirements identified by GPT4: 
    * Data Identifier Management: Requirement for the efficient handling of customer identifiers in the data pipelines. (Keyword: cust_id)
    * Requirement for managing taxonomy identifiers effectively within the pipelines. (keyword: taxonomie_id)
    * Data Staging: Requirement to handle 'staging' areas or concepts effectively in the data pipelines. (keyword: stg)
    * Message Identifier Management: Requirement for the effective management of message identifiers in the data pipelines. (keyword: msgid)
    * Data Pipeline Operations: Requirement for improved handling and management of the key elements within Azure Data Factory (keywords: data, columns, pipelines, values, tables, activities, files)
* Non-Functional Requirements identified by GPT4 were: 
    * Usability: Requirement for the platform to be user-friendly and easy to use. (keywords: using)
    * Operational Efficiency: Requirement for the platform to efficiently perform basic operations like getting and adding data (keywords: get, add, store)
    * Support and Documentation: Requirement for better support and documentation to aid users in their attempts to use the platform. (keywords: tried, trying)

### Conclusion: 
The data analysis has provided a solid starting point for requirement engineers seeking an overview of user pain points within Azure Data Factory. The resulting LDA model has been thoroughly tested in numerous variations and is deemed sufficiently accurate for the purposes of this project. However, the training of the unsupervised machine learning models could be further improved. These models currently exhibit slight overfitting while predicting with an accuracy of 87%. There is also room for refactoring within the code itself. The identified requirements could also be validated by further requirements Engineering techniques e.g. stakeholder interviews, surveys and questionanires. Overall, further steps in requirement engineering should be taken from the human perspective: "How to best enable the flow within Azure Data Factory?"   

GPT4 proven to be a very valuable "coach" for setting up code architecture and for generating code. This process was extremely agile and allowed to test out various NLP and machine learning techniques while ultimately  settling for those most suitable for this project. Using generated code also allowed for more queries to identify relevant keywords for the creation of sub data sets. Identifying the most relevant keywords themselves, however, required an experienced human text data analyst. When interpreting the results of the Latent Dirichilet Allocation, spaCy extractions and Vader Sentiment Analysis GPT4 was able to derive interpretations which would not have been obvious to a single human being. GPT4 clearly allowed me to operate outside of my initial knowledge base and to draw conclusions outside of my field of expertise (e.g. specifics on Azure Data Factory). The results of this project can easily be transformed into learning material for further learning on NLP and Machine Learning.

# About me

I am a social scientist who graduated in 2008. My diploma thesis included conducting 24 in depths interviews which I manually coded using microsoft access, pen and paper. Using a methodology based on grounded theory I derived themes, topics and further insghts from the interview transcripts. In 2009 I spent six very intensive months manually coding transcripts of interviews concerning the development of a corporate sustainability strategy. I used Microsoft word for this project. Fast forward to 2018-2022 I intensively researched attributes and keywords in order to write product and category descriptions for e-commerce. All of these experiences taught me to find stories, themes, topics, entities, labels and much more in large text bodies or in keyword sets. In 2022 I enrolled in a data science bootcamp laying a foundation for my machine learning journey. I am particularly interested in how to combine human expertise with classical machine learning and Natural Language Generartion. 

### Most Relevant Notebooks
* 01adf_query_whole_data_set.ipynb (Generates the preprocesses the data from Stack Overflow)
* 02adf_query_keyword_filter.ipynb (Filters the data, performs Latent Dirichilet Allocation)
* 03_svm.ipynb (validates most relevant topic found through LDA using Support Vector Machines)
* 04_logistic_regression_count_vectorizer.ipynb (validates most relevant topic found through LDA using Logistic Regression)
* 05_RNN.ipynb (validates most relevant topic found through LDA using RNN)
