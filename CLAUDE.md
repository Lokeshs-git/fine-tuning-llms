# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository contains exercises on LLM fine-tuning techniques. It's a learning-focused codebase for exploring various fine-tuning approaches.

## Development Environment

This is a Jupyter notebook-based project for LLM fine-tuning exercises. Common workflows will involve:

### Running Notebooks
```bash
jupyter notebook
# or
jupyter lab
```

### Installing Dependencies
When notebooks are added, they will typically require:
```bash
pip install -r requirements.txt
# or for specific exercises
pip install transformers datasets torch accelerate peft
```

## Code Organization

As this repository grows, expect the following structure:
- Jupyter notebooks (`.ipynb`) for hands-on fine-tuning exercises
- Python scripts (`.py`) for reusable utilities and training code
- Data directories for datasets used in fine-tuning exercises
- Model checkpoints and experiment outputs (typically git-ignored)

## Fine-Tuning Context

When working with fine-tuning code in this repository:
- **Model loading**: Check for GPU availability and memory constraints
- **Training configurations**: Hyperparameters are typically defined at notebook/script start
- **Dataset handling**: Datasets may be loaded from HuggingFace, local files, or generated
- **Checkpointing**: Fine-tuned models are usually saved to `./models/` or `./checkpoints/`
- **Common libraries**: transformers, datasets, peft (for LoRA/QLoRA), accelerate, bitsandbytes

## Testing Training Code

For notebooks with training loops:
```python
# Test with minimal epochs/steps first
trainer.train(max_steps=10)  # Quick validation

# Full training run
trainer.train()
```

For standalone scripts:
```bash
python train.py --epochs 1 --batch_size 2  # Quick test
python train.py  # Full training with default or configured params
```
