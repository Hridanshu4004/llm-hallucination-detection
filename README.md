# LLM Hallucination Detection via Faithfulness Scoring

This project benchmarks hallucination behavior in large language models using
retrieval-augmented generation (RAG) and automatic faithfulness scoring.

---

## 📌 Overview
Large Language Models often hallucinate facts when answering questions.
This project builds an evaluation pipeline to measure whether model outputs
are supported by retrieved evidence.

---

## 🔍 Pipeline
1. Load FEVER dataset
2. Retrieve relevant evidence passages
3. Prompt LLMs using retrieved context
4. Score answers using NLI models
5. Compute semantic similarity
6. Combine into a faithfulness score
7. Compare models using correlation and accuracy

---

## 🧮 Faithfulness Formula

faithfulness =
0.6 × entailment +
0.4 × similarity −
0.3 × contradiction

---

## 🤖 Models Tested
- TinyLlama
- Qwen-1.5-1.8B-Chat

---

## 📚 Dataset
FEVER fact-verification dataset from HuggingFace.

---

## 📊 Results

| Model | Corr(Faithfulness, Label) | Accuracy |
|------|------|------|
| TinyLlama | 0.46 | 0.80 |
| Qwen | 0.59 | 0.80 |

---

## 🧪 Threshold Optimization
We sweep decision thresholds over the faithfulness score and select the cutoff
that maximizes hallucination-detection accuracy.

---

## ⚠️ Limitations
- Small evaluation sample
- Simple retriever
- Single dataset
- Open-source models only

---

## 🚀 Future Work
- Test larger proprietary models
- Use learned verifiers
- Multi-hop retrieval
- Calibration curves
- Larger datasets

---

## ▶️ How to Run

Install dependencies:

pip install -r requirements.txt

Open notebooks in this order:

02_build_retriever.ipynb  
03_generate_answers.ipynb  
4_hallucination_scoring.ipynb  

---

## 👤 Author
Hridanshu
