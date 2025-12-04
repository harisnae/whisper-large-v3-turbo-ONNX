# Whisper‑large‑v3‑turbo ONNX Demo (Colab)

[![Open In Colab][colab-badge]][colab-notebook]  

[colab-badge]: https://colab.research.google.com/assets/colab-badge.svg
[colab-notebook]: https://colab.research.google.com/github/harisnae/whisper-large-v3-turbo-ONNX/blob/main/whisper_large_v3_turbo_demo.ipynb
[license-badge]: https://img.shields.io/github/license/harisnae/whisper-large-v3-turbo-ONNX
[license]: https://github.com/harisnae/whisper-large-v3-turbo-ONNX/blob/main/LICENSE
[stars-badge]: https://img.shields.io/github/stars/harisnae/whisper-large-v3-turbo-ONNX?style=social
[repo]: https://github.com/harisnae/whisper-large-v3-turbo-ONNX

---

## Overview

This repository contains a **self‑contained Google Colab notebook** that demonstrates how to:

* Install system and Python dependencies (ffmpeg, Transformers, Optimum, ONNX Runtime, …)
* Download the **ONNX‑exported Whisper large‑v3‑turbo model** from the 🤗 Hub (`onnx-community/whisper-large-v3-turbo-ONNX`).
* Load the model with `optimum.onnxruntime.ORTModelForSpeechSeq2Seq`.
* Run inference on a local or remote audio file.
* Pretty‑print the transcription with automatic line‑wrapping.

The notebook works **out‑of‑the‑box** on a free Colab GPU (or CPU if no GPU is available) and requires **no manual setup** beyond clicking the badge.

---

## Getting Started

### 1. Open the notebook in Colab

Click the badge at the top of this page:

[![Open In Colab][colab-badge]][colab-notebook]

The notebook will open in a new tab.  

**⚡ Important:** the demo notebook is written as a **single‑cell** script.  
Before you start the execution you must place the audio file you want to transcribe in the Colab session storage:

1. In the left sidebar of Colab, click the **Files** tab (the folder‑icon).  
2. Press the **Upload** button and select your `audio.wav` (or any other supported audio file).  
3. Wait for the upload to finish – the file will appear as `/content/audio.wav`.

Once the file is uploaded, run the notebook by selecting **Runtime → Run all** (or press the ▶️ button at the top of the cell).  
All required system‑ and Python‑packages will be installed automatically, the ONNX‑exported Whisper‑large‑v3‑turbo model will be downloaded from the Hugging Face Hub, and the transcription will be performed on the uploaded `audio.wav` file.

### 2. Run locally (optional)

If you prefer to run the notebook on your own machine:

```bash
# Clone the repo
git clone https://github.com/harisnae/whisper-large-v3-turbo-ONNX.git
cd whisper-large-v3-turbo-ONNX

# (Optional) create a virtual environment
python -m venv .venv && source .venv/bin/activate

# Install the exact same dependencies
pip install -r requirements.txt   # (you can create this file from the notebook's pip block)

# Launch Jupyter
jupyter notebook whisper_large_v3_turbo_demo.ipynb
