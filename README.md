# Information-Retrieval-Doc
Information Retrieval(IR) System Notes

# 1. Problem Statement: 
User will type Questions/Queries, system has to retrieve related answers to the questions and related paragraphs/sentences with the highlighted answers where the answer was found. Below image gives clear idea.

(Source:https://towardsdatascience.com/how-to-create-your-own-question-answering-system-easily-with-python-2ef8abc8eb5)

# 2. Introduction
Information Retrieval(IR) System: An Information Retrieval System is a network of algorithms which facilitate the search of relevant data/documents as per user requirement. Applications of IR are Search Engine, Image Retrieval, Music Retrieval, News Search, Question Answering System(Our problem statement), etc.

# 3. Document Retrieval
Traditional Approaches: Cosine Similarity and Euclidean Distance calculated between the tf-idf vectors of the query and each document.Is viewed as the matching (relevance) score between them.

# 4. Question-Answer(QA) System
Open-domain QA vs. closed-domain QA
Two different kinds of QAsystems: open-domain QA (ODQA) systems and closed-domain QA (CDQA) systems.
Open-domain systems deal with questions about nearly anything, and can only rely on general ontologies and world knowledge. On the other hand, closed-domain systems deal with questions under a specific domain (for example, medicine or automotive maintenance), and can exploit domain-specific knowledge by using a model that is fitted to a unique-domain database.
CDQA System Architecture:

(Source:https://towardsdatascience.com/how-to-create-your-own-question-answering-system-easily-with-python-2ef8abc8eb5)

The cdQA architecture is based on two main components: the Retriever and the Reader. You can see below a schema of the system mechanism.
Retriever:
When a question is sent to the system, the Retriever selects a list of documents in the database that are the most likely to contain the answer, which creates TF-IDF features based on uni-grams and bi-grams and compute the cosine similarity between the question sentence and each document of the database.
Reader:
After selecting the most probable documents, the system divides each document into paragraphs and send them with the question to the Reader, which is basically a pre-trained Deep Learning model. The model used was the Pytorch version of the well known NLP model BERT, Then, the Reader outputs the most probable answer it can find in each paragraph. After the Reader, there is a final layer in the system that compares the answers by using an internal score function and outputs the most likely one according to the scores.

# 5. References

[1] https://nlp.stanford.edu/IR-book/
[2] https://ciir.cs.umass.edu/downloads/SEIRiP.pdf
[3] http://www.search-engines-book.com/slides/
[4]https://www.hangli-hl.com/uploads/3/4/4/6/34465961/sigir_tutorial.pdf
[5]https://towardsdatascience.com/how-to-create-your-own-question-answering-system-easily-with-python-2ef8abc8eb5
