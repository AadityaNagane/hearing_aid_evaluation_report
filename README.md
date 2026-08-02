# Omni-Qwen Evaluation Dashboards

This repository hosts the interactive evaluation dashboards for the **Omni-Qwen** project—an end-to-end multimodal speech-to-text architecture. The project aims to eliminate the "intermediate text bottleneck" found in traditional cascaded Automatic Speech Recognition (ASR) pipelines by mapping continuous acoustic representations directly into the Large Language Model (LLM) embedding space.

## 📊 Live Dashboards

You can view the interactive data visualizations directly via GitHub Pages:

* **[ASR Model Comparison](https://AadityaNagane.github.io/omni-qwen-evals/transcription_report.html)**: Evaluates the acoustic accuracy (Word Error Rate) of the Omni Phase 1 models against OpenAI's zero-shot Whisper baselines.
* **[Summarization Evaluation](https://AadityaNagane.github.io/omni-qwen-evals/summarization_report.html)**: Compares the generative fidelity, semantic similarity, and compression rates of the end-to-end Omni-Qwen architecture against traditional cascaded pipelines (BERT, FLAN-T5, Qwen).

## 🧠 Project Architecture

The Omni-Qwen framework consists of three primary pillars:
1. **Audio Encoder**: Pre-trained OpenAI `whisper-base` ($d_{enc} = 512$).
2. **Speech Projector**: A custom multi-layer perceptron (MLP) that temporally downsamples and projects the acoustic features.
3. **Causal LLM Decoder**: `Qwen2.5-0.5B-Instruct` ($d_{llm} = 896$), trained using Parameter-Efficient Fine-Tuning (PEFT) via Low-Rank Adaptation (LoRA).

## 📈 Datasets Used

The models were evaluated across a diverse suite of speech datasets to test varying acoustic conditions:
* **LibriSpeech**: Clean, well-articulated audiobook narration.
* **Common Voice**: Crowdsourced, multilingual read speech with varying microphone quality.
* **Switchboard**: Spontaneous, narrow-bandwidth telephone conversations heavily laden with disfluencies.
* **AMI Meeting Corpus**: Multi-speaker room recordings with overlapping speech and far-field microphones.
* **TED-LIUM**: Prepared public speaking and lectures.

## 💻 Hardware Profile

All local inferences and evaluations featured in these reports were conducted on consumer-grade hardware to validate the model's edge-deployment viability:
* **System**: HP Victus Gaming Laptop (15-fa2xxx)
* **CPU**: Intel® Core™ i5-14450HX (10 Cores, 16 Threads)
* **RAM**: 24.0 GB
* **GPU**: NVIDIA GeForce RTX 3050 (6GB VRAM)

## 📁 Repository Structure

* `transcription_report.html` - Interactive charts and tables detailing Word Error Rate (WER) and latency metrics.
* `summarization_report.html` - Interactive charts, scatter plots, and tables detailing ROUGE scores, semantic similarity, and text compression rates.

---
**Author:** Aditya Nagane  
