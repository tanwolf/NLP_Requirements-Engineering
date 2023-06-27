# Applying NLP in Requirements Engineering: Exploring Data Management Challenges in Azure Data Factory

## Abstract
_This project is a collaboration between an experienced human text data analyst, gpt4, as well as unsupervised and supervised machine learning algorithms. The goal of this project is to find out how these four "collaborators" can find new ways of analyzing and interpreting large amounts of text data. This project employs Natural Language Processing (NLP) to analyze questions and answers from StackOverflow concerning Azure Data Factory (ADF). GPT4 is then prompted to derive functional and non-functional requirements for data management within ADF from the NLP results. GPT4 also identifies categories and keywords representing these requirements._ 

In conclusion the collaboration between the four "collaborators" was successful. It highlighted, however, that an initial human contribution to keyword analysis is key when designing and filtering the data set. Note: Since access to the GPT4 API was not available, ChatGPT Plus was used for reasoning, interpretation and code generation.

Link to flow chart: https://miro.com/app/board/uXjVMIxaFOo=/?share_link_id=288843918581


### Exerpts from the Project:
> **GPT4 Prompt:** Considering the results of the LDA, the Vader Sentiment Analysis and the spaCy extractions as well as the Certified Professional for Requirements Engineering (CPRE) certification: Which functional and non-functional requirements are expressed by the users on StackOverflow concerning Azure Data Factory? List the requirements for each of the LDA Topics.

> **GPT4 Prompt:** For each topic generate keywords which represent functional and non functional requirements. For each keyword summarize which requirement it represents.

> **GPT4 Prompt:** Categorize the requirements for each topic.


### Results:
* Based on the results of the NLP analysis, GPT-4 defined the following functional and non-functional requirements mentioned by ADF users on StackOverflow:
    * Data Identifier Management: Requirement for the efficient handling of customer identifiers in the data pipelines. (Keyword: cust_id)
    * Requirement for managing taxonomy identifiers effectively within the pipelines. (keyword: taxonomie_id)
    * Data Staging: Requirement to handle 'staging' areas or concepts effectively in the data pipelines. (keyword: stg)
    * Message Identifier Management: Requirement for the effective management of message identifiers in the data pipelines. (keyword: msgid)
    * Data Pipeline Operations: Requirement for improved handling and management of the key elements within Azure Data Factory (keywords: data, columns, pipelines, values, tables, activities, files)
* Non-Functional Requirements identified by GPT4 were: 
    * Usability: Requirement for the platform to be user-friendly and easy to use. (keywords: using)
    * Operational Efficiency: Requirement for the platform to efficiently perform basic operations like getting and adding data (keywords: get, add, store)
    * Support and Documentation: Requirement for better support and documentation to aid users in their attempts to use the platform. (keywords: tried, trying)

The keywords assigned to the non-functional requirements can be used as filters for further analysis. This is not true for functional requirements as their keywords were assigned from recognized entities not actual keywords appearing in the question bodies. 

### Findings:
* The most significant impact on identifying relevant topics within questions about Azure Data Factory was achieved through manual comparison of keyword frequency.
* Once a sub-dataset was defined using keywords as filters, the LDA effectively identified the most prominent topic within the dataset.

### Methodology: 
The project leverages SQL queries on StackExchange to gather data. This data is then transformed into pandas dataframes in Python. Through a combination of traditional NLP, quantitative keyword analysis, supervised machine learning and GPT-4 prompts, the project:
    * Generates datasets and sub-datasets that provide insights into requirements for data management and pipeline design in ADF.
    * Establishes topics related to data management and pipeline design in ADF using Latent Dirichlet Allocation (LDA).
    * Identifies pertinent entities, nouns, and verbs within these topics with the aid of spaCy.
    * Gauges sentiments concerning these topics using Vader sentiment analysis.
    * Validates the most significant topic found through unsupervised machine learning (LDA) with supervised machine learning algorithms.
    * Names the most relevant topic ("Data Management in Pipelines") using GPT4 prompts. 
    * Uses GPT-4 prompts to interpret the numeric results of LDA, Vader Sentiment Analysis, and spaCy extractions in terms of requirements engineering for ADF.
    * Prompts GPT4 to categorize and assign a keyword to each requirement.
    * Implements a coherent code architecture using GPT-4 for generating code 

### Conclusion: 
The data analysis has resulted in a final data set where each row is either assigned to the most relevant topic found in the data set or not assigned to any topic. Out of the total 8547 rows, 2097 were assigned to this topic entitled 'Data Management in Pipelines'. The analysis and final data set provide a solid starting point for requirements engineers seeking an overview of user challenges and pain points within Azure Data Factory. The resulting LDA model has been thoroughly tested in numerous variations and is deemed sufficiently accurate for the purposes of this project. However, the training of the unsupervised machine learning models could be further improved. These models currently exhibit slight overfitting while predicting with an accuracy of 87%. 

GPT4 has proven to be a very valuable "coach" and generator for code architecture and code itself. This process was extremely agile and allowed to test out various NLP and machine learning techniques while ultimately settling for the most suitable ones. Using generated code also allowed for more queries to identify relevant keywords for the creation of sub data sets. Identifying the most relevant keywords themselves, however, required an experienced human text data analyst. When interpreting the results of the Latent Dirichilet Allocation, spaCy extractions and Vader Sentiment Analysis GPT4 was able to derive interpretations which would not have been obvious to a single human being alone. GPT4 clearly allows humans to create code architecture outside of their initial knowledge base and to draw conclusions outside of their field of expertise (e.g. specifics on Azure Data Factory). It was the task of the human collaborator, however, to consistently validate the suggested code and approaches of GPT4.

### Limitations:
This project was created for NLP and NLG training purposes. There is room for improvements concerning the virtual environment, the code structure and the directory architecture. Significant improvements could, for example, be made to ensure consistent results from spaCy entity recognition and to enhance the reproducibility of the virtual environment. In addition, the identified requirements have not been validated by further requirements engineering techniques e.g. stakeholder interviews, surveys, and questionanires. Overall, further steps in requirement engineering should be taken from the human perspective: "How to best enable the flow within Azure Data Factory?"   

### Data
**Source:** 
StackOverflow question and answers concerning Azure Data Factory (ADF), lengths: 8547 rows, StackExchange Inc. (2023). StackExchange Data Explorer [SQL query on StackOverflow data]. Available at: https://data.stackexchange.com/stackoverflow/query/new

**Generated Schema:** https://dbdiagram.io/d/6448f5b26b3194705139098b

**Final Data Set:** merged_adf_df_with_lda_topic1.csv

## Most Relevant Notebooks
* 1adf_query_whole_data_set.ipynb (Generates and preprocesses the data from StackOverflow)
* **2adf_query_keyword_filter.ipynb** (Filters final data set, performs NLP and GPT4 operations)
* 01_svm.ipynb (validates most relevant topic found through LDA using Support Vector Machines)
* 02_logistic_regression_count_vectorizer.ipynb (validates most relevant topic found through LDA using Logistic Regression)
* 03_RNN.ipynb (validates most relevant topic found through LDA using RNN)

### Personal Project Background
This project is many things in one: A combination of mixed data analysis methods, content management techniques, NLP and NLG. I could continue the list but most importantly, it is my first ever machine learning project. I incorporated my past experiences in dealing with large bodies of unstructured text data such as finding stories, themes, topics, keywords as well as entities and labels. 

Parts of the research approach of this project go way back to my social science diploma thesis in 2008. Back then I conducted 24 in depths interviews which I manually coded, analyzed and interpreted using microsoft access, pen and paper. Employing a methodology based on grounded theory I derived themes, topics and further insights from the interview transcripts. In 2009 I spent six very intensive months manually coding transcripts of interviews concerning the development of a corporate sustainability strategy. I used Microsoft word for this project. Since 2018 I have intensively worked with keywords, attributes, and data management systems to create e-commerce product and category descriptions. All of this led me to enroll in a data science bootcamp in 2022. My particular interested lies in combining human expertise and mixed methods with classical machine learning and Natural Language Generation.
