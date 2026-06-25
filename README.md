# Handwritten OCR using TrOCR

This project implements an end-to-end handwritten OCR system using Microsoft's **TrOCR** model and the **IAM Handwriting Dataset**. The model was fine-tuned on handwritten text and evaluated using standard OCR metrics such as Character Error Rate (CER) and Word Error Rate (WER).

## Dataset

- IAM Handwriting Dataset: https://fki.tic.heia-fr.ch/databases/iam-handwriting-database
- Hugging Face Dataset: https://huggingface.co/datasets/Teklia/IAM-line

### Dataset Statistics

| Split | Samples |
|---------|---------:|
| Train | 6482 |
| Validation | 976 |
| Test | 2915 |

## Model

- Pretrained Model: `microsoft/trocr-small-handwritten`
- Framework: PyTorch + Hugging Face Transformers
- Training Environment: Google Colab (Tesla T4 GPU)

## Training Configuration

- Epochs: 3
- Learning Rate: 5e-5
- Batch Size: 4
- Training Samples: 2000
- Validation Samples: 300

## Results

| Metric | Value |
|----------|----------|
| CER | 0.1456 |
| WER | 0.2675 |
| Character Accuracy | 85.44% |
| Word Accuracy | 73.25% |

## Error Analysis

Common OCR errors observed:

- Character substitutions
- Punctuation mistakes
- Number recognition errors
- Word substitutions
- Repeated text generation

## LLM Post-Processing

LLMs can be used to improve OCR outputs by:

- Correcting spelling mistakes
- Restoring punctuation
- Normalizing text
- Extracting structured information

## How to Run

1. Open `OCR_Project.ipynb` in Google Colab.
2. Enable GPU runtime.
3. Run all cells sequentially.
4. Evaluate the model and test custom handwritten images.

## Conclusion

This project demonstrates a complete OCR pipeline including data auditing, preprocessing, model fine-tuning, evaluation using CER/WER, error analysis, and LLM-assisted OCR correction.
