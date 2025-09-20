# Bill2Burn 🧾🔥🏃

**Bill2Burn** is a smart fitness assistant that helps you **burn the calories you eat**. 
Upload your food bill, and the system automatically extracts items, calculates the calories, and recommends **personalized exercises with durations** to burn them off.

## 🧩 Problem Statement

Modern lifestyles often lead to excessive calorie intake without awareness of how much exercise is needed to burn it.
While nutrition tracking apps exist, they usually require manual logging of meals, which is tedious and error-prone.

The challenge is to:

- Automatically extract food details from bills/receipts
- Map them to calories using nutrition databases
- Recommend exercises with precise durations to burn those calories

This automation removes friction in calorie tracking and helps users make smarter, healthier lifestyle decisions.

---

## 🧠 Agentic Flow  

Bill2Burn uses an **Adaptive RAG flow** to ensure accurate recommendations:  

1. **Query Analysis** – Determines if retrieval is required  
2. **Retrieve Docs** – Fetches calorie/exercise mappings  
3. **Grade Docs** – Filters and validates useful knowledge  
4. **Generate Answer** – Produces exercise plan  
5. **Hallucination Check** – Verifies factual accuracy  
6. **Rewrite Question if Needed** – Iterates until confident  
7. **Final Recommendation** – Calories + exercise duration

---

## 📊 Flow Diagram  

Here’s the high-level **Adaptive RAG flow** used in the project:  

<img src="https://github.com/Ashutosh2613/bill2burn/blob/main/graph.png" alt="Agentic Flow" width="400"/>

---

## ⚙️ How It Works

### 1. Bill Upload
- User uploads receipt (image/PDF)  
- OCR extracts item names and quantities  

### 2. Calorie Estimation
- Maps each food item to **nutritional database values**  
- Computes per-item and total calorie count

### 3. Embedding document
- Converts food items and calorie data into **vector embeddings**  
- Stores them in a vector database for semantic search and retrieval  

### 4. 🔍 Agentic RAG Pipeline
- Used LangChain and LangGraph for agentic workflow.
- LLama 3.2 (local) is used for generation.

### 5. 🏃 Exercise Recommendation
- Suggests multiple exercises based on user preference (e.g., jogging, cycling, HIIT)  
- Provides **duration (minutes)** to burn the total calories  
