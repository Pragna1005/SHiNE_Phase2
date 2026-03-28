# SHiNe: Semantic Hierarchy Nexus for Open-Vocabulary Object Detection
### Phase 2 — Reproduced the results and Novel Contributions
**CVPR 2024 Highlight** | Liu, Hayes, Ricci, Csurka, Volpi

---

## Demo Video
[YouTube Link](https://youtube.com/YOUR_LINK)

---

## About the Paper
SHiNe addresses vocabulary granularity sensitivity in open-vocabulary
object detection. Existing detectors encode only raw class names —
describing the same object as "Labrador", "Dog", or "Animal" yields
completely different detection scores. SHiNe builds hierarchy-aware
**nexus classifiers** using Is-A sentences, improving up to +31.9%
mAP50 with zero inference overhead.

**Original paper:** [SHiNe CVPR 2024](https://arxiv.org/abs/2405.10053)
**Original code:** [naver/shine](https://github.com/naver/shine)

---

## Our Contributions

| # | Contributions | Description |
|---|---|---|
| 1 | DAG Hierarchy | ALL WordNet paths vs paper's single tree path |
| 2 | Weighted Mean | Leaf-biased aggregation weights |
| 3 | Adaptive Aggregation | Norm-based weights, no tuning needed |
| 4 | Richer LLM Hierarchies | 5-level vs paper's 3-level |
| 5 | COCO128 Detection | Zero-shot bounding box demo |

---

## Results

### Part A — Oxford Flowers-102 (Reproduction)

| Method | Hierarchy | Accuracy | Δ |
|--------|-----------|----------|---|
| Baseline | — | 67.20% | — |
| SHiNe | WordNet Tree | 72.00% | +4.80 |
| SHiNe | LLM (GPT-3.5) | 64.40% | -2.80 |
| **SHiNe (ours)** | **DAG+Weighted** | **72.00%** | **+4.80** |

### Part B — CIFAR-10 (Novel Contribution)

| Method | Hierarchy | Accuracy | Δ |
|--------|-----------|----------|---|
| Baseline | — | 89.70% | — |
| SHiNe | WordNet Tree | 90.40% | +0.70 |
| **SHiNe (ours)** | **DAG+Weighted** | **90.40%** | **+0.70** |
| SHiNe (ours) | LLM 5-level | 86.00% | -3.70 |

---

## How to Run

1. Open the notebook in google colab
2. Set your OpenAI API key in Cell 3 (optional —-needed only for LLM hierarchy)
3. Runtime → Run All

### Option 2 — Local
```bash
git clone https://github.com/YOUR_USERNAME/SHiNe-Phase2
cd SHiNe-Phase2
pip install torch torchvision clip-by-openai nltk openai matplotlib
jupyter notebook notebooks/SHiNe_Phase2_Complete_Final.ipynb
```

---

## Saved Hierarchies
The `hierarchies/` folder contains pre-generated LLM hierarchy JSON files.
The notebook loads these automatically — **no OpenAI API key needed to
reproduce results** unless you want to regenerate them.

---

## Team
| Name | Roll Number |
|------|-------------|
| Pragna Sree Muvva | B23CM1025 |
| Sai Pragathi Lagudu | B23CM1021 |
