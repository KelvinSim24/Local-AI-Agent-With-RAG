# 🍕 Local-Pizza-RAG: Private AI Agent for Restaurant Intelligence

A high-performance, **100% offline** Retrieval-Augmented Generation (RAG) system. This project utilizes a local LLM stack to transform unstructured pizza restaurant reviews into structured, actionable insights without ever sending data to the cloud.

## 🚀 Key Highlights

- **Privacy-First:** Processes all data locally via Ollama; ideal for sensitive or proprietary datasets.
- **Advanced Synthesis:** Unlike basic keyword search, this agent categorizes sentiments (e.g., "Positive Highlights" vs. "Potential Drawbacks") across multiple documents.
- **Optimized for Hardware:** Specifically tuned to run on medium-level consumer laptops using quantized GGUF models.
- **Semantic Precision:** Powered by the state-of-the-art `qwen3-embedding` for superior context retrieval.

---

## 🛠️ The Stack

- **Orchestration:** [LangChain](https://python.langchain.com/)
- **Brain (LLM):** `gemma4:e4b` (via Ollama)
- **Embeddings:** `qwen3-embedding:4b` (via Ollama)
- **Vector Database:** [ChromaDB](https://www.trychroma.com/) (Local Persistence)
- **Data Processing:** Pandas

---

## 📊 Performance Showcase (Tested Results)

The agent demonstrates high reasoning capabilities by synthesizing mixed reviews into structured summaries.

### Test 1: Complex Ingredient Analysis

**Query:** _"How are the vegan options?"_
**Agent Output:**

> "While some customers report having an incredible vegan experience, praising the use of house-made cashew cheese... other reviews suggest that the quality of vegetable toppings can be highly inconsistent (canned vs. fresh)."

### Test 2: Situational Ambience Reasoning

**Query:** _"How is the ambience?"_
**Agent Output:**

> "The atmosphere is noted as being perfect for watching sports... however, potential visitors should be aware of a serious cleanliness concern mentioned in specific reviews (sticky tables)."

---

## ⚙️ Installation & Setup

### 1. Prerequisites

Ensure you have [Ollama](https://ollama.com/) installed and running.

### 2. Pull the Models

```bash
ollama pull gemma4:e4b
ollama pull qwen3-embedding:4b
```
