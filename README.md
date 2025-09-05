# 📘 PolicyAlign

## 📌 Overview
An end-to-end system in **BigQuery AI** to detect, compare, and reconcile policy changes across documents.  
The pipeline ensures consistent knowledge management by maintaining a **canonical knowledge base** with AI + human review.

---

## 🚀 Why This Matters
Policies and documents constantly evolve. Without monitoring, subtle changes (e.g., refund timelines, compliance rules) create **knowledge drift** — leading to contradictions, regulatory risks, and poor customer experiences.  

---

## 📂 Project Overview
- Ingest unstructured docs (PDF/TXT/DOCX) from GCS as Object Tables  
- Generate clause-level snippets with `AI.GENERATE`  
- Create embeddings with `ML.GENERATE_EMBEDDING`  
- Detect semantic drift with pairwise `ML.DISTANCE` + `VECTOR_SEARCH`  
- Classify changes & unify clauses using `AI.GENERATE` (Gemini)  
- Approve high-confidence cases → build a canonical knowledge base  

---

## 🏗️ Architecture 
![Architecture Diagram](/Architecture.png)

---

## 📺 Demo Video

🎥 [Watch the Demo on YouTube](https://youtu.be/z2iMFg6dneo?si=NRC3m1EgAvGBcczn)

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

## 📊 Results / Outcomes
- Automated extraction & unification of refund policies  
- Identified **behavioral changes with >90% confidence**  
- Reduced manual review effort by surfacing only drift-heavy clauses  
- Built a canonical, drift-free table for downstream apps  

---

## 🛠️ Tech Stack
- **BigQuery AI** (`AI.GENERATE`, `ML.GENERATE_EMBEDDING`, `VECTOR_SEARCH`)  
- **Gemini 2.5 Flash** (semantic reasoning & clause unification)  
- **Google Cloud Storage** (document source)  
- **BigQuery Object Tables** (multimodal doc ingestion)  

---

## 🔮 Future Improvements
- Multi-lingual policy drift detection  
- Image/PDF multimodal embeddings (e.g., scanned docs)  
- Real-time drift alerts & dashboards  
- Integration with downstream RAG / chatbots for enterprise QA  

---

## ✅ Conclusion
This project showcases how **BigQuery AI + Vector Search + Gemini** can automatically detect **knowledge drift** in policies, recommend unified clauses, and maintain a **living knowledge base** with minimal manual effort.
