# Bipolar LLM Knowledge Graph

This project integrates **Large Language Models (LLMs)** like ChatGPT with a **Knowledge Graph (KG)** for **clinical question answering (QA)** in the context of **bipolar disorder**. It uses structured data extracted from medical literature and applies graph reasoning to improve diagnostic support.

## 🔍 Features

- Cognitive Map Graph construction from medical text (CSV-based)
- Visualization of entity-relation graphs using NetworkX
- Dual QA pipeline:
  - Standard ChatGPT
  - ChatGPT + Knowledge Graph (LangChain GraphQAChain)
- Evaluation of QA with/without graph support using classification metrics

## 🧠 Technologies Used

- Python
- OpenAI GPT-3.5 / GPT-4 via LangChain
- NetworkX, Matplotlib
- Pandas, Scikit-learn
- FAISS (for vector store - optional)
- CSV-based triplet loading and QA data
- LangChain GraphQA

## 📁 File Structure

- `bipolar_disorder_kg_with_llm.py` – Main script to run KG + QA pipeline
- `Converted_Bipolar_Knowledge_Graph.csv` – Triplet data for KG
- `QA_data.csv` – Clinical questions for QA evaluation
- `test_df_*.csv` – Saved results (with and without graph)

## 📊 Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score

## ⚙️ Setup

```bash
pip install -r requirements.txt
```

Make sure to set your OpenAI API key via environment variable:
```bash
export OPENAI_API_KEY=your-key-here
```

## 🚀 Run

```bash
python bipolar_disorder_kg_with_llm.py
```

## 🧪 Output and Results

### 📌 Knowledge Graph Output
- The project generates a **Cognitive Map Graph** from medical data related to bipolar disorder.
- Each triplet extracted (head, relation, tail) is visualized using NetworkX.
- The graph illustrates symptoms, causes, treatments, and linked conditions.

### 🤖 Question Answering (QA)
- The system answers clinical questions twice:
  1. Using **ChatGPT alone**
  2. Using **ChatGPT + Knowledge Graph context**
- Example QA from `QA_data.csv`:
  - **Q:** "Is lithium used in the treatment of bipolar disorder?"
    - **Without Graph:** "Yes, it can be used in some cases."
    - **With Graph:** "Yes, lithium is a commonly prescribed mood stabilizer for bipolar disorder. It helps manage manic episodes."

### 📊 Quantitative Results

| Metric   | Without Graph | With Graph |
|----------|----------------|------------|
| Accuracy | 60%            | 80%        |
| Precision| 64%            | 83%        |
| Recall   | 61%            | 79%        |
| F1 Score | 62%            | 81%        |

> These results demonstrate that the graph-aided approach significantly improves QA performance and clinical relevance.

### 💾 Output Files

- `test_df_wo_graph.csv` – Raw LLM responses without knowledge graph.
- `test_df_w_graph.csv` – LLM responses informed by knowledge graph.
- PNG output of graph visualization saved from NetworkX.

## 📄 License

MIT License