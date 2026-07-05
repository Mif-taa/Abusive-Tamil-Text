## 📄 CUET_SYNTHETICA@DravidianLangTech 2026
### Multi Architecture Transformer Ensemble for Detecting Abusive Tamil Text Targeting Women

[![Paper](https://img.shields.io/badge/ACL%20Anthology-2026.dravidianlangtech--1.29-blue)](https://doi.org/10.18653/v1/2026.dravidianlangtech-1.29)
[![Workshop](https://img.shields.io/badge/Workshop-DravidianLangTech%40ACL%202026-orange)]()
[![Rank](https://img.shields.io/badge/Rank-4th%20Place-brightgreen)]()

**Authors:** Miftahul Jannat Rishta, Sumaiya Zaman, Shiti Chowdhury, Hasan Murad
**Venue:** Proceedings of the Sixth Workshop on Speech, Vision, and Language Technologies for Dravidian Languages, ACL 2026
**DOI:** [10.18653/v1/2026.dravidianlangtech-1.29](https://doi.org/10.18653/v1/2026.dravidianlangtech-1.29)

#### 🧩 Overview
This work tackles the DravidianLangTech@ACL 2026 shared task on classifying Tamil YouTube comments as **Abusive** or **Non-Abusive**. Instead of relying on a single model, we built a heterogeneous ensemble of **12 transformer classifiers** and combined their outputs through soft-voting.

#### 🏗️ Architecture
- **3 transformer backbones**, each fine-tuned **4 times** with different learning rates → 12 models total
  - **MuRIL** — pretrained on 17 Indian languages + transliterations
  - **IndicBERT v2** — large-scale Indic corpus, 24 languages
  - **XLM-RoBERTa-Large** — 100-language multilingual coverage
- Final prediction = **argmax of averaged softmax probabilities** across all 12 models (soft-voting)

#### 🔧 Pipeline
Raw Data → Label Normalization → Preprocessing (11-step cleaning)
→ Tokenization (model-specific) → Fine-tuning (12 runs)
→ Soft-Voting Ensemble → Final Prediction**Preprocessing** included HTML decoding, URL/email/mention removal, hashtag normalization, punctuation reduction, zero-width character removal, and deduplication (3,652 → 3,251 samples).

#### 📊 Results

| Model | Accuracy | Precision | Recall | Macro F1 |
|---|---|---|---|---|
| MuRIL (best run) | 0.7963 | 0.7975 | 0.7949 | 0.7954 |
| XLM-R-Large (best run) | 0.7919 | 0.7919 | 0.7913 | 0.7915 |
| IndicBERT v2 (best run) | 0.8083 | 0.8096 | 0.8070 | 0.8075 |
| **Final 12-Model Ensemble** | **0.8094** | **0.8106** | **0.8082** | **0.8086** |

🏆 **Result:** Macro F1 = **0.8086**, securing **4th place** in the shared task. The heterogeneous ensemble outperformed every individual model and every single-architecture ensemble, confirming that architectural diversity — not just learning-rate variation — drove the gains.


#### 💻 Code
🔗 [github.com/Mif-taa/Abusive-Tamil-Text](https://github.com/Mif-taa/Abusive-Tamil-Text)

#### 📚 Citation
```bibtex
@inproceedings{rishta2026cuetsynthetica,
  title     = {CUET\_SYNTHETICA@DravidianLangTech 2026: Multi Architecture Transformer Ensemble for Detecting Abusive Tamil Text Targeting Women},
  author    = {Rishta, Miftahul Jannat and Zaman, Sumaiya and Chowdhury, Shiti and Murad, Hasan},
  booktitle = {Proceedings of the Sixth Workshop on Speech, Vision, and Language Technologies for Dravidian Languages},
  year      = {2026},
  publisher = {Association for Computational Linguistics},
  doi       = {10.18653/v1/2026.dravidianlangtech-1.29}
}
```
