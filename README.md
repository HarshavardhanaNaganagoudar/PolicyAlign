# 📘 PolicyAlign

## 📌 Overview
An end-to-end system in **BigQuery AI** to detect, compare, and reconcile policy changes across documents.  
The pipeline ensures consistent knowledge management by maintaining a **canonical knowledge base** with AI + human review.

---

## ⚡ Features
- Clause extraction with `AI.GENERATE`  
- Semantic similarity using embeddings & vector search  
- AI verdicts on policy differences  
- Human-in-the-loop approval workflow  
- Canonical Knowledge Base (KB) builder  

---

## 🏗️ Architecture 
![Architecture Diagram](/Architecture.png)

---

## 📚 Workflow
1. **Load documents** into BigQuery from Cloud Storage.  
2. **Extract snippets/clauses** with `AI.GENERATE`.  
3. **Generate embeddings** using `ML.GENERATE_EMBEDDING`.  
4. **Find candidate pairs** with semantic similarity search.  
5. **Compare clauses** using Gemini verdicts (`AI.GENERATE`).  
6. **Review changes** and approve high-confidence updates.  
7. **Build canonical KB** for unified policy references.  
8. **Retrieve/query** with vector search for semantic lookups.  

---

## ✅ Conclusion
This project showcases how **BigQuery AI + Vector Search + Gemini** can automatically detect **knowledge drift** in policies, recommend unified clauses, and maintain a **living knowledge base** with minimal manual effort.
