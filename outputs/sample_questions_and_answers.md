# Sample Questions and Answers

This file records sample tests for the simple RAG assistant.

The purpose is to show how we can check whether the assistant retrieves the correct document and gives an answer that is grounded in the retrieved evidence.

---

## Test 1

**Question:** Can I use GenAI for Assessment 2?

**Expected retrieved document:** GenAI Declaration

**Expected answer:** Students may use GenAI tools to assist them in any way. However, any use of generative AI must be appropriately acknowledged. Students must include a Declaration of AI Generated Material.

**Evaluation:** Correct. The answer is grounded in the GenAI Declaration document.

---

## Test 2

**Question:** What should I include in my report?

**Expected retrieved document:** Assessment Brief

**Expected answer:** The report should include an introduction, target problem, choice of data sources, methodology, evaluation, discussion, conclusion and references. Students are also encouraged to develop the application within a GitHub repository.

**Evaluation:** Correct. The answer is grounded in the Assessment Brief document.

---

## Test 3

**Question:** How long is the oral presentation?

**Expected retrieved document:** Assessment Brief

**Expected answer:** The oral presentation should be 15 minutes.

**Evaluation:** Correct. The answer is grounded in the Assessment Brief document.

---

## Test 4

**Question:** What should I include in my reflection?

**Expected retrieved document:** Rubric Summary

**Expected answer:** The final presentation must include a reflection explaining how the student responded to feedback, what changes were made, why those changes were made and how they improved the project.

**Evaluation:** Correct. The answer is grounded in the Rubric Summary document.

---

## Test 5

**Question:** What is the penalty for late submission?

**Expected retrieved document:** No sufficiently relevant document

**Expected answer:** The retrieved documents do not provide enough information.

**Evaluation:** Correct. The current documents do not contain information about late-submission penalties, so the assistant should not invent an answer.

---

# Key lesson

A RAG system should not answer just because it retrieves something.

It should answer only when the retrieved documents provide enough evidence.

If the retrieved documents do not contain the answer, the assistant should say that the documents do not provide enough information.
