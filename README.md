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

GPU recommended; Apple MPS / CPU also work (slower).

## Physical sticker training

The notebook section **Train for the physical world (EOT)** adds:
- random scale, rotation, brightness/contrast, blur, noise
- total-variation regularizer for printability
- export of a printable PNG under `saved_models/tutorial10/physical_exports/`

Your Porsche sticker lives in `stickers/` for natural-looking constrained patch experiments.

## License / data

TinyImageNet subset follows the [ImageNet license](http://image-net.org/download-faq). Tutorial code originally by Phillip Lippe.
