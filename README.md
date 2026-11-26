# StyleTTS 2 Fine-Tuning for Custom Voices

An automated Kaggle-ready pipeline for fine-tuning [StyleTTS 2](https://github.com/yl4579/StyleTTS2) on custom datasets. This repository contains the complete workflow to prepare 24kHz audio datasets, handle transcriptions, bypass PyTorch unpickling restrictions, and train a high-quality text-to-speech model.

Currently configured for the VCTK dataset (Speaker `p251` - Indian Accent).

## Features
* **Automated Data Prep:** Extracts, resamples (to 24000 Hz), and splits custom speaker data into train/val sets.
* **Kaggle Optimized:** Built specifically to run on Kaggle's dual T4 GPU environments.
* **Automated Environment Fixes:** Dynamically patches legacy PyTorch `weights_only=False` loading errors and Git LFS dependency issues.
* **Phonemizer Integration:** Uses `espeak-ng` to generate accurate phonetic alignments.

## Repository Structure
* `StyleTTS2_Finetuning.ipynb`: The main Kaggle notebook containing the end-to-end pipeline.
* `requirements.txt`: Python dependencies required for local execution.
* `.gitignore`: Standard Git exclusions for deep learning projects.

## How to Use on Kaggle
1. Open a new Kaggle notebook and import `StyleTTS2_Finetuning.ipynb`.
2. Attach your audio dataset (e.g., VCTK or LibriTTS) to the Kaggle input directory.
3. Update the `SPEAKER_ID` variable in the notebook to match your target speaker.
4. Run all cells. The script will automatically clone the base model, prepare the wavs, and patch necessary `.py` files before training.

## Credits
Based on the original [StyleTTS 2](https://github.com/yl4579/StyleTTS2) architecture by yl4579.
