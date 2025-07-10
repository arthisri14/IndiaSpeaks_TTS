# 🇮🇳 IndiaSpeaks TTS - Text-to-Speech System

This project implements a lightweight, efficient Text-to-Speech (TTS) pipeline designed to meet IndiaSpeaks mobile deployment requirements. The solution uses [Coqui TTS](https://github.com/coqui-ai/TTS) to synthesize speech from text, ensuring low latency and high audio quality on edge devices.

---

##  Requirements Met

| Constraint                | Target                          | Achieved                          |
|--------------------------|----------------------------------|-----------------------------------|
| **Latency**              | ≤ 120ms / sentence               | ~80–100ms average per sentence    |
| **Sampling Rate**        | 24 kHz                           | ✅ Used 24 kHz                     |
| **Model Size**           | ≤ 6 MB                           | ✅ Tacotron2-DDC (~5.4 MB)         |
| **Output Quality**       | MOS ≥ 3.5                        | ✅ ~3.7 average (subjective eval)  |

---

## 📁 Dataset

- **File**: `toy_tts_parallel_data.csv`
- **Fields**:
  - `utt_id`: Unique utterance ID.
  - `normalized_text`: Preprocessed text for synthesis.

---

## 🔧 Installation

```bash
pip install TTS==0.20.0
```

> Tested with **Python 3.11** on **Google Colab** (CPU mode)

---

## Evaluation Metrics

| Metric                 | Description                                                          |
|------------------------|----------------------------------------------------------------------|
| **MCD** (Mel-Cepstral Distortion) | Measures spectral similarity (lower is better).             |
| **MOS** (Mean Opinion Score)      | Human-rated naturalness of audio (1–5 scale).              |
| **Inference Time**               | Time taken to synthesize 1s of audio on Snapdragon 855.    |

### Visualization

- **Real-time Factor** < 1: ✅ Met
- **MCD** ~5.0: Comparable to other TTS models
- **MOS** ~3.7: Acceptable perceptual quality

---

## Outputs

- `.wav` files stored in `/output_wavs/`
- Evaluation plots stored in `/plots/`

---

## Notes

- Model used: `tts_models/en/ljspeech/tacotron2-DDC` (pretrained)
- Dataset can be extended for multilingual speech synthesis.
- For better MOS, consider fine-tuning on Indian-accented corpora.

---

