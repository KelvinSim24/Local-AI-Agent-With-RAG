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
⚙️ Installation & Setup
1. Prerequisites
Ensure you have Ollama installed and running on your machine.

2. Pull the Models
Open your terminal and run:

Bash
ollama pull gemma4:e4b
ollama pull qwen3-embedding:4b
3. Setup Environment
Bash
# Clone the repository
git clone https://github.com/KelvinSim24/Local-AI-Agent-With-RAG.git
cd Local-AI-Agent-With-RAG

# Create and activate virtual environment
python -m venv venv

# On Windows:
.\venv\Scripts\activate

# On Mac/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
4. Run the Agent
Bash
python main.py
🏗️ Architecture Detail
Ingestion: vector.py processes realistic_restaurant_reviews.csv, generates high-dimensional vectors using qwen3-embedding, and persists them in a local chroma_langchain_db folder.

Retrieval: The system uses semantic similarity search to pull the top 8 most relevant context chunks based on the user's natural language query.

Generation: The gemma4 model acts as the reasoning engine, synthesizing the retrieved reviews into a structured, human-readable summary.

📜 License
Distributed under the MIT License.
