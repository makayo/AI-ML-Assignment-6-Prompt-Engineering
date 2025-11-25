# Prompt Engineering for Performance Improvement
Author: MARK YOSINAO  
Artificial Intelligence — Prompt Engineering, Large Language Models, and Output Evaluation

## Environment
- Python 3.11.3  
- Hugging Face Transformers 4.x  
- Jupyter Notebook (Anaconda environment)  
- Pandas 2.x  

---

## Project Overview
This project demonstrates the practical impact of **prompt engineering** on Large Language Model (LLM) performance.  
The task: extract structured fields (Name, Price, Date) from unstructured product reviews.  

By applying at least three distinct prompt techniques, the project shows how model output quality can be significantly improved. The workflow highlights the progression from a weak baseline to a fully optimized prompt.

---

## Dataset / Input
Instead of a large dataset, the project uses **sample product review text** as input. Example:


The model is asked to extract:
- **Name** → Product name  
- **Price** → Purchase price  
- **Date** → Purchase date  

---

## Workflow Summary
1. **Baseline Prompt**
   - Simple instruction: “Extract the product name, price, and date.”
   - Output: Only product name, incomplete extraction.

2. **Role Prompting**
   - Model instructed to act as a *Senior Data Analyst*.
   - Output: Recognized fields but did not fully extract values.

3. **Output Formatting**
   - Explicit request for JSON format with keys: Name, Price, Date.
   - Output: Structured JSON with name and price, but missing date.

4. **Chain-of-Thought Reasoning**
   - Prompt includes step-by-step reasoning before final answer.
   - Output: Complete JSON with all fields (Name, Price, Date).

5. **Final Optimized Prompt**
   - Combines role prompting, output formatting, and chain-of-thought.
   - Output: Clean, structured, and accurate extraction.

---

## Evaluation
| Prompt Type         | Output Example                                                                 | Accuracy | Format Adherence | Notes                                                                 |
|---------------------|---------------------------------------------------------------------------------|----------|------------------|----------------------------------------------------------------------|
| Baseline            | `Samsung Galaxy S22`                                                           | Low      | Poor             | Only product name, missed price and date                             |
| Role Prompting      | `Samsung Galaxy S22, price, purchase date`                                     | Medium   | Partial          | Recognized fields but didn’t extract values                          |
| Output Formatting   | `Name[Samsung Galaxy S22], Price[799]`                                         | High     | Good             | Captured name and price, but missed date                             |
| Chain-of-Thought    | `{"Name": "Samsung Galaxy S22", "Price": "799", "Date": "March 3, 2023"}`      | Very High| Excellent        | Full structured JSON, reasoning implied                              |
| Final Optimized     | `Name[Samsung Galaxy S22], Price[799], Date[2023-03-03]`                       | Very High| Excellent        | Clean, structured output with all fields                             |

---

## Results
- Baseline prompt produced incomplete extraction.  
- Role prompting improved recognition of fields.  
- Output formatting enforced structure.  
- Chain-of-thought reasoning enabled complete extraction.  
- Final optimized prompt combined all techniques for the best result.  

This progression demonstrates how **prompt engineering directly impacts LLM performance**.

---

