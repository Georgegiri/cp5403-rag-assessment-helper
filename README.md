# CP5403 RAG Assessment Helper

This repository contains a simple Retrieval-Augmented Generation (RAG) assistant for CP5403 Assessment 2.

The purpose of this project is to help students understand how a basic RAG system works using a small and manageable example.

---

## What this project demonstrates

This project demonstrates the basic RAG pipeline:

```text
Documents
   ↓
Chunks
   ↓
Embeddings
   ↓
Vector search
   ↓
Retrieved evidence
   ↓
Prompt construction
   ↓
LLM answer
```

The key idea is:

```text
Retriever finds the evidence.
Prompt gives the instruction.
LLM writes the answer.
```

---

## Project purpose

The assistant answers student questions about CP5403 Assessment 2 using a small set of assessment-related documents.

Example questions include:

* Can I use GenAI for Assessment 2?
* What should I include in my report?
* How long is the oral presentation?
* What should I include in my reflection?
* What happens if the answer is not in the documents?

---

## Repository structure

```text
cp5403-rag-assessment-helper/
│
├── documents/
│   ├── assessment_brief.txt
│   ├── genai_declaration.txt
│   └── rubric_summary.txt
│
├── notebooks/
│   └── simple_rag_assistant_clean.ipynb
│
├── outputs/
│   └── sample_questions_and_answers.md
│
└── README.md
```

Note: The notebook filename may differ slightly depending on how it was saved.

---

## Documents used

The knowledge base contains three small text documents:

1. `assessment_brief.txt`
   Contains the main Assessment 2 requirements.

2. `genai_declaration.txt`
   Contains guidance on GenAI use and declaration requirements.

3. `rubric_summary.txt`
   Contains a simplified summary of the marking criteria and reflection requirement.

---

## Technologies used

This project uses:

* Google Colab
* Python
* sentence-transformers
* FAISS
* Hugging Face Transformers
* `google/flan-t5-base`

---

## How to run the notebook

1. Open the notebook in the `notebooks` folder.
2. Open it in Google Colab.
3. Run the cells from top to bottom.
4. Test the RAG assistant using the sample questions.
5. Try changing the questions.
6. Review which documents were retrieved.
7. Check whether the answer is supported by the retrieved documents.

---

## How the RAG assistant works

The notebook performs the following steps:

1. Loads the documents.
2. Converts the documents into chunks.
3. Converts each chunk into an embedding vector.
4. Stores the vectors in a FAISS search index.
5. Converts the user question into an embedding.
6. Retrieves the most relevant document chunks.
7. Checks whether the retrieved chunks are relevant enough.
8. Builds a prompt containing:

   * instructions
   * retrieved evidence
   * the user question
9. Sends the prompt to a Hugging Face language model.
10. Generates an answer based on the retrieved documents.

---

## Why the relevance check matters

A RAG system should not answer just because it retrieves something.

Sometimes the closest retrieved documents may still be weak or irrelevant. In this project, a simple distance threshold is used to reduce unsupported answers.

For example, if the user asks:

```text
What is the penalty for late submission?
```

and the documents do not contain late-submission penalty information, the assistant should answer:

```text
The retrieved documents do not provide enough information.
```

This is an important RAG guardrail.

---

## Academic integrity note

This repository is a worked example.

Students may use it to understand the RAG process, but their Assessment 2 submission must use their own:

* target problem
* data sources
* methodology
* implementation
* evaluation
* discussion
* reflection

Students must also acknowledge any use of GenAI tools in accordance with the assessment instructions.

---

## Suggested extension tasks

Students can extend this project by:

1. Replacing the sample documents with their own documents.
2. Adding more documents to the knowledge base.
3. Testing more questions.
4. Improving the prompt.
5. Comparing different embedding models.
6. Comparing different language models.
7. Adding a simple user interface.
8. Creating an evaluation table.
9. Adding document citations to the generated answers.
10. Testing what happens when the answer is not found in the documents.

---

## Key takeaway

A RAG system does not simply ask an LLM a question.

It first retrieves relevant evidence, then asks the LLM to answer using that evidence.

```text
Question → Retrieve evidence → Build prompt → Generate answer
```

This project is intentionally small, but it demonstrates the core architecture used in larger commercial RAG systems.
