# Caribbean Voices ASR - Zindi Hackathon

**Team:** diTranscribers | **Authors:** Douglas Byfield, Tia Salmon

---

## Overview

Fine-tuned Whisper Large-v3 with LoRA for Caribbean-accented English ASR.

| Metric | Score |
|--------|-------|
| Public WER | 0.034076303 |
| Private WER | 0.034229624 |

---

## Model

| Component | Value |
|-----------|-------|
| Base Model | openai/whisper-large-v3 |
| Method | LoRA (r=64, alpha=128) |
| Target Modules | q_proj, k_proj, v_proj, o_proj |

---

## Files

```
├── Caribbean_Voices_ASR_Zindi.ipynb   # Notebook
├── requirements.txt                    # Dependencies
├── README.md                           # This file
└── FinalModel/                         # LoRA adapter
    ├── adapter_config.json
    ├── adapter_model.safetensors
    └── training_args.bin
```

---

## How to Run

1. Open notebook in **Google Colab** (GPU required)
2. Upload `FinalModel/` to `/content/FinalModel`
3. Put `Audio.zip` and `Test.csv` in Google Drive at `/content/drive/MyDrive/ZindiHackathon/`
4. Run **Section 1** (Setup)
5. Skip **Section 2** (Training - commented out)
6. Run **Section 3** (Inference) - ~6 hours on T4
7. Run **Section 4** (Postprocessing)
8. Get `submission.csv` from Google Drive

---

## Requirements

```
transformers>=4.36.0
peft>=0.6.0
torch>=2.0.0
librosa>=0.10.0
pandas>=2.0.0
tqdm>=4.65.0
num2words>=0.5.12
accelerate>=0.24.0
datasets>=2.14.0
scikit-learn>=1.3.0
```

---

## Environment

| Component | Spec |
|-----------|------|
| Platform | Google Colab Pro+ |
| GPU | NVIDIA T4/A100 |
| Python | 3.10 |

---

## Data

Zindi-provided only: Train.csv, Test.csv, Audio.zip  
**No external datasets used.**

---

## Acknowledgements

Thank you so much to Zindi and the competition hosts for this incredible opportunity! This hackathon allowed us to work on a meaningful problem—improving ASR for Caribbean-accented English, which is often underrepresented in mainstream speech recognition systems. We learned a great deal about fine-tuning large speech models and are grateful for the chance to contribute to more inclusive AI technology. We hope our solution helps advance speech recognition for Caribbean communities.

— Team diTranscribers (Douglas & Tia)
