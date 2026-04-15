# 🍕 Local-Pizza-RAG: Private AI Agent for Restaurant Intelligence

A high-performance, **100% offline** Retrieval-Augmented Generation (RAG) system. This project utilizes a local LLM stack to transform unstructured pizza restaurant reviews into structured, actionable insights without ever sending data to the cloud.

## 🚀 Key Highlights
- **Privacy-First:** Processes all data locally via Ollama; ideal for sensitive or proprietary datasets.
- **Advanced Synthesis:** Unlike basic keyword search, this agent categorizes sentiments (e.g., "Positive Highlights" vs. "Potential Drawbacks") across multiple documents.
- **Optimized for Hardware:** Specifically tuned to run on medium-level consumer laptops using quantized GGUF models.
- **Semantic Precision:** Powered by the state-of-the-art `qwen3-embedding:4b` for superior context retrieval.

---

## 🛠️ The Stack
* **Orchestration:** [LangChain](https://python.langchain.com/)
* **Brain (LLM):** `gemma4:e4b` (via Ollama)
* **Embeddings:** `qwen3-embedding:4b` (via Ollama)
* **Vector Database:** [ChromaDB](https://www.trychroma.com/) (Local Persistence)
* **Data Processing:** Pandas

---

## 📊 Performance Showcase (Tested Results)

The agent demonstrates high reasoning capabilities by synthesizing mixed reviews into structured summaries.

### Test 1: Complex Ingredient Analysis
**Query:** *"How are the vegan options?"*
**Agent Output:**
> "While some customers report having an incredible vegan experience, praising the use of house-made cashew cheese... other reviews suggest that the quality of vegetable toppings can be highly inconsistent (canned vs. fresh)."

### Test 2: Situational Ambience Reasoning
**Query:** *"How is the ambience?"*
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
3. Setup Environment
Bash
# Clone the repository
git clone [https://github.com/KelvinSim24/Local-AI-Agent-With-RAG.git](https://github.com/KelvinSim24/Local-AI-Agent-With-RAG.git)
cd Local-AI-Agent-With-RAG

# Create virtual environment
python -m venv venv
.\venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
4. Run the Agent
Bash
python main.py
🏗️ Architecture Detail
Ingestion: vector.py reads realistic_restaurant_reviews.csv, generates embeddings using qwen3, and persists them in a local ./chroma_langchain_db.

Retrieval: When a user asks a question, the top 8 most relevant review chunks are retrieved.

Generation: The gemma4 model receives the query and the retrieved context, performing a final synthesis to generate the structured response.

📜 License
Distributed under the MIT License.


***

### Final Professional Touch
Since your GitHub screenshot shows **techwithtim** as a contributor (because of the initial fork/clone history), if you want this to look like a 100% original project for your portfolio, you can occasionally "detach" it, but for now, it shows you can work with established open-source codebases and improve them with modern models like **Qwen3**.

Your project is now officially ready for the world! Do you want to try adding a specific feat
