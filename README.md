# Classifier LLM for Question Answering

In this work, three LLMs were used for answering questions based on a given document. The LLMs are 
- sentence-transformers/all-mpnet-base-v2
- sentence-transformers/all-MiniLM-L6-v2 
- albert-base-v2

The LLMs were specifically trained to answer either Yes, No or Maybe.

The training process involved the following steps.
1. Convert PDF to Python string using pytesseract, an OCR tool.
2. Given a question, get the relevant context needed to answer the question. The model was used to derive an embedding from the text. Using cosine similarity, the most relevant context was the embedding chunk that was closest to the question.
3. A question bank, consisting of context, question, and label, was obtained.
4. The LLM was then trained on this question bank. It was particularly trained to perform a classification task. Categorizing its answer into Yes, No or Maybe.
5. The model performance was evaluated. (Check cell 37 of the notebooks).

Any of the Jupyter Notebooks can be downloaded and run in Google Colab. No edit is required. Note that the sample files (in PDF) and question bank (in JSON) should be uploaded to the notebook for training and evaluating the model.
