## 📄 CUET_SYNTHETICA@DravidianLangTech 2026
### Multi Architecture Transformer Ensemble for Detecting Abusive Tamil Text Targeting Women

**Authors:**
- Miftahul Jannat Rishta
- Sumaiya Zaman
- Shiti Chowdhury
- Hasan Murad

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
