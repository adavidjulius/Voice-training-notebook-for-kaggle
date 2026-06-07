# 🎙️ Voice Training Notebook for Kaggle

**JULIUS — RVC v2 Training Notebook (Kaggle Clean Rebuild)**

Mangio-RVC-Fork · OV2Super 40k · fairseq-free feature extraction

---

## ✅ What's Fixed vs Previous Notebook

- fairseq replaced with `contentvec` direct HuBERT extraction (no build errors)
- `pipeline_mp missing thread_n` patched at clone time
- `preprocess.log` pre-created before script runs
- All `/content/` references replaced with `/kaggle/working/`
- `cwd` never becomes invalid (no rmtree of cwd)
- F0 `no-f0-todo` fixed by ensuring correct file layout before extraction
- FAISS, training, packaging all Kaggle-path clean

## ⚙️ Run Order

```
Cell 1 → 2 → 3 → 4 → 5 → 6 → 7 → 8 → 9
```

## 🖥️ Requirements

- GPU: P100 or T4 (enable in Kaggle settings)
- Internet: ON
- Python: 3.10
- PyTorch: 2.3.1 + CUDA 12.1

## 📦 Tech Stack

| Component | Detail |
|---|---|
| Base | Mangio-RVC-Fork |
| Pretrain | OV2Super 40k |
| Feature extraction | contentvec HuBERT (fairseq-free) |
| Sample rate | 40,000 Hz |
| Batch size | 8 |
| Epochs | 200 |
| Index | FAISS IVF |

## 📁 Cell Summary

| Cell | Purpose |
|---|---|
| 1 | Config & directory setup |
| 2 | Install dependencies (fairseq-free) |
| 3 | Clone Mangio-RVC-Fork & patch |
| 4 | Download pretrained weights |
| 5 | Load dataset from Kaggle input |
| 6 | Feature extraction (contentvec HuBERT) |
| 7 | Build FAISS index |
| 8 | Training loop with auto-backup |
| 9 | Package & export model |

---

Made by [David Julius](https://github.com/adavidjulius)
