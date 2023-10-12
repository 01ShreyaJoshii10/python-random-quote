> Objective:  Creating a Question Answering (QA) system that looks up
through provided documents to retrieve or generate accurate, contextually relevant answers to the given questions and Establishing a custom pipeline for generating embeddings and handling QA functionality.

> Libraries used:
Hugging Face Transformers library to load a pre-trained LLM like BERT.
Torch
NumPy
faiss

> General pipeline would include,
1. Collecting the document and the questions together.
2. Selecting an LLM: Many different LLM's such as LLAMA2,
MPT, Mistral, BERT. The "best" choice depends on the specific task requirements, the language(s) involved, and the hardware resources.
3. Here I've used BERT model (which is a Pre-trained model from the Hugging Face Transformers library) considering the hardware resources.
4. Cleaning and Pre-processing the text data for example: tokenization, lowercasing, and removing stop words is done.
5. We will first split the text into tokens, then convert these tokens into numerical embeddings (vectors) that can be used as input to our model.
4. Then comes the part of designing model architecture which should take the document and question embeddings as input and predict the start and end positions of the answer in the document.
5. Question Pre-processing:
Pre-process the questions by tokenizing and formatting them to match the model's input format. Used the model's tokenizer for this.
6. Answer Extraction:
For each question, used the LLM to extract answers from the document. This can be done using a simple extractive QA approach. Tokenized the document and question, then found the answer span that matches the question.
7. Finding of Embedding Size of the model.
8. Used FAISS for Vector Store and Embeddings.
9. Created embeddings for the document and questions
10. Thus, the process of looping through the questions, searching for relevant documents using FAISS, and applying the question-answering model to extract answers is the general pipeline of the task.
