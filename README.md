# Water Surface Segmentation using Fine-tuned SegFormer

## Overview
This project fine-tunes a SegFormer-B2 model to detect and segment water surfaces from CCTV camera footage. Developed as part of an industry-partnered capstone project, the model performs binary pixel-level classification (water / background) and is evaluated within a defined Region of Interest (ROI).

The dataset was self-collected from a real reservoir site — over 1,200 nighttime images with manual binary mask annotations.

## Model
- **Base model:** `nvidia/segformer-b2-finetuned-ade-512-512`
- **Task:** Binary semantic segmentation (water / background)
- **Fine-tuned on:** Self-collected CCTV dataset (1,200+ nighttime images)

## Methodology
1. **Preprocessing** — image resizing, normalization, low-light enhancement (Gamma + CLAHE)
2. **Data Augmentation** — flip, rotate, brightness/contrast, Gaussian noise
3. **Fine-tuning** — replaced classification head (150 → 2 classes), trained with Cross Entropy + Dice Loss
4. **Evaluation** — IoU and BIoU computed within ROI only

## Results
| Metric | Score |
|--------|-------|
| IoU (ROI) | 0.9863 |
| BIoU (ROI) | 0.7328 |

## Contact

Thanatcha Chomnak — [LinkedIn](https://www.linkedin.com/in/thanatcha-chomnak-643761351)

## Acknowledgments

* [SegFormer — HuggingFace](https://huggingface.co/nvidia/segformer-b2-finetuned-ade-512-512)
* [Albumentations](https://albumentations.ai)
* Capstone advisor: Assoc. Prof. Rajalida Lipikorn, Chulalongkorn University

<p align="right">(<a href="#readme-top">back to top</a>)</p>
