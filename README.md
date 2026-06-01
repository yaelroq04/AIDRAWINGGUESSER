# Real Time Drawing Recognizer
**Oregon Institute of Technology – CST 407: Python For AI**

A real-time drawing recognition app built on the Google Quick, Draw! Dataset.
Draw something in your browser and the model returns its top 3 predictions instantly.

## About This Project

This is my final project for CST 407 at OIT. The goal is to train a Convolutional Neural
Network to recognize hand-drawn sketches in real time using a browser-based canvas interface.
The model is trained on a subset of the Google Quick, Draw! Dataset — over 50 million drawings
collected from an online game where players sketched objects in under 20 seconds.

This repo contains everything: data prep, model training, evaluation, and the interactive demo.

## Project Structure

```
├── data/               # Scripts for downloading and preprocessing .npy files
├── notebooks/          # Exploratory notebooks and training experiments
├── model/              # Saved model weights and architecture definitions
├── demo/               # Browser-based drawing interface
└── report/             # Accuracy curves, confusion matrix, and analysis
```

## Dataset

**Source:** [Google Quick, Draw! Dataset](https://github.com/googlecreativelab/quickdraw-dataset)

Two modifications are made to the original dataset:
- **Category Reduction:** 15–20 categories selected out of 345 to keep training time reasonable
- **Sample Capping:** 10,000 training samples and 2,000 validation samples per category to ensure balance

## Model

The primary model is a Convolutional Neural Network trained on 28×28 grayscale images:

- Input: 28×28×1
- Conv2D (32 filters, 3×3, ReLU) → Conv2D (64 filters, 3×3, ReLU) → Conv2D (128 filters, 3×3, ReLU)
- Flatten → Dense (256, ReLU) → Dropout (0.5)
- Output Dense (softmax over categories)

As a stretch goal, an LSTM variant treating drawings as ordered stroke sequences may also be explored.

## Target Performance

Google's own classifier achieves ~92% top-1 accuracy across all 345 categories.
With only 15–20 categories, this project targets **≥ 90% validation accuracy**.

## Expected Deliverables

- Trained CNN with ≥ 90% validation accuracy
- Interactive browser demo: draw with your mouse, get top 3 predictions in real time
- Analysis report: training/validation curves, confusion matrix, comparison to Google benchmark, and visualized failure cases

## AI Disclosure

I use Claude AI by Anthropic as a **learning tool** in this course. This means I may use AI to:
- Help explain concepts I'm working to understand
- Debug or review my code
- Ask questions as I would a tutor or study partner

AI assistance does **not** replace my own understanding. The goal is to learn Python and AI
concepts more deeply, not to have work done for me. All submitted work reflects my own
comprehension and effort.

## Course Info

**Course:** CST 407 – Python For AI\
**Institution:** Oregon Institute of Technology (OIT)\
**Repo Owner:** [yaelroq04](https://github.com/yaelroq04)
