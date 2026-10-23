# Document Question-Answering Assistant

## 1. Project Overview

The Document Question-Answering Assistant is a Python-based application that answers user questions using information extracted from uploaded documents. It retrieves relevant passages from the document and generates answers grounded in the available content.

The system is designed to reduce unsupported answers by returning a fixed message when the requested information cannot be found in the provided document.

## 2. Objectives

- Extract text from PDF, DOCX, and TXT documents.
- Divide document text into manageable passages.
- Retrieve relevant passages using TF-IDF and cosine similarity.
- Answer questions using information available in the document.
- Display supporting passages for transparency.
- Return an exact fallback message for unsupported questions.
- Provide a simple chat interface for interacting with documents.

## 3. Technologies Used

- **Python** – Core programming language
- **Gradio** – Chat interface
- **Scikit-learn** – TF-IDF vectorization and cosine similarity
- **PyPDF2** – PDF text extraction
- **python-docx** – DOCX text extraction
- **NumPy** – Numerical operations

## 4. System Workflow

1. Upload a PDF, DOCX, or TXT document.
2. Extract text from the uploaded document.
3. Split the extracted text into smaller passages.
4. Convert passages into TF-IDF vectors.
5. Compare the user's question with the document passages.
6. Retrieve the most relevant passages.
7. Display an answer with supporting document evidence.
8. Return the fallback message if the answer is not supported by the document.

## 5. Features

- Supports PDF, DOCX, and TXT files.
- Automatically extracts document text.
- Uses text chunking to organize document content.
- Retrieves relevant passages using TF-IDF.
- Displays supporting evidence for answers.
- Includes a user-friendly chat interface.
- Handles unsupported questions using a predefined fallback response.

## 6. Installation

Install Python 3.10 or a compatible version, then install the required libraries:

```bash
pip install gradio numpy scikit-learn PyPDF2 python-docx
```

## 7. How to Run

1. Save the application code as `app.py`.
2. Open a terminal in the project folder.
3. Install the required dependencies.
4. Run the application:

```bash
python app.py
```

5. Open the local URL displayed in the terminal.
6. Upload a document and click the load button.
7. Enter a question related to the document.
8. Review the answer and its supporting passages.

## 8. Sample Questions and Answers

The following examples use the PhishGuard AI project report as the sample document.

| Question | Expected Answer |
|---|---|
| What is the main objective of PhishGuard AI? | To analyze URLs and classify them as legitimate, suspicious, or phishing. |
| Which dataset was used? | PhiUSIIL Phishing URL Dataset. |
| How many records are present in the dataset? | 235,795 records. |
| Which machine learning models were used? | Logistic Regression, Random Forest, and Decision Tree. |
| What is the best value of `n_estimators`? | 150. |
| Who won the FIFA World Cup in 2034? | Information not found in provided document |

*Note: These examples should be checked against the actual application output before submission.*

## 9. Fallback Handling

When the requested information is not available in the uploaded document, the application should return this exact message:

`Information not found in provided document`

This helps prevent the assistant from presenting unsupported information as a fact.

## 10. Limitations

- Answer quality depends on the content and formatting of the uploaded document.
- TF-IDF retrieval relies on textual similarity and may miss relevant passages expressed using different terminology.
- Scanned PDFs may require OCR if they do not contain selectable text.
- The system does not guarantee that every retrieved answer is correct; supporting passages should be reviewed.

## 11. Future Enhancements

- Add semantic embeddings for improved retrieval.
- Support OCR for scanned documents.
- Improve passage ranking and source citations.
- Support multiple documents in a single knowledge base.
- Add conversation history and downloadable answer reports.

## 12. Conclusion

The Document Question-Answering Assistant demonstrates how document text extraction, passage chunking, information retrieval, and a chat interface can be combined to answer questions using a provided document. Its evidence-based retrieval and fallback mechanism aim to make document question-answering more transparent and reliable.
