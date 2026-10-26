# Adversarial Patches (Physical / Sticker)

Notebook and assets for training **adversarial image patches**, including **physical-world EOT** training for printable stickers.

Based on Phillip Lippe’s adversarial-attacks tutorial (modified for Duke AIPI 590 XAI).

## Contents

| Path | Description |
|------|-------------|
| `adversarial_attacks_patches.ipynb` | Main tutorial + physical EOT training |
| `stickers/porsche_gt3rs_sticker.jpg` | Natural-looking sticker for constrained / print experiments |
| `data/TinyImageNet.zip` | Eval/train image set used by the notebook |
| `saved_models/tutorial10/` | Pretrained digital patches + `patch_results.json` |
| `imagenet_classes.txt` | ImageNet class names |

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook adversarial_attacks_patches.ipynb
```

**Recommended:** Google Colab with a **T4 GPU**. Apple MPS / CPU also work (slower).

## Physical sticker training

Upload this repo (including `stickers/porsche_gt3rs_sticker.jpg`) to Colab, then run the section **Train for the physical world (EOT) — Porsche sticker patch**:
- initializes from the Porsche artwork (circular crop + mask)
- EOT: random scale, rotation (±45°), horizontal/vertical flips, brightness/contrast, blur, noise
- content loss keeps it looking like the sticker while becoming adversarial
- exports a printable PNG under `saved_models/tutorial10/physical_exports/`

Tunables in the demo cell: `PHYS_CLASS`, `PHYS_SIZE` (default **1024** for print), `CONTENT_WEIGHT` (look vs attack strength), `PHYS_EPOCHS`, `BATCH_SIZE`.

## License / data

TinyImageNet subset follows the [ImageNet license](http://image-net.org/download-faq). Tutorial code originally by Phillip Lippe.
