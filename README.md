# local-llm-deployment-llama-cpp
Local LLM deployment using llama.cpp, GGUF and CUDA GPU acceleration.

## Overview

This project demonstrates the deployment and inference of a GGUF-based Large Language Model using **llama.cpp** with **NVIDIA CUDA GPU acceleration**.

The project was developed as part of a Mobile App Development course assignment focused on deploying an AI model that can run locally without depending on an online AI API.

## Technologies Used

* llama.cpp
* GGUF
* CUDA
* NVIDIA GPU
* Linux
* TinyLlama
* Kaggle GPU environment for deployment testing

## Model

* **Model:** TinyLlama
* **Format:** GGUF
* **Quantization:** Q4_K - Medium
* **Model size:** approximately 637 MB

The model file itself is not included in this repository because of its large size. The repository contains the deployment commands and documentation needed to reproduce the setup.

## Deployment

The project uses llama.cpp as the local inference runtime.

A CUDA-enabled build was configured and compiled successfully. The resulting `llama-cli` executable was then used to load the TinyLlama GGUF model and generate text.

GPU offloading was enabled using:

```bash
-ngl 99
```

## GPU Testing

The deployment was tested in a GPU environment with two NVIDIA Tesla T4 GPUs.

The `nvidia-smi` output showed the `llama-cli` process using GPU memory on both Tesla T4 devices.

## Performance

During testing, the model achieved approximately:

* **Prompt processing:** 757.8 tokens/sec
* **Generation:** 167.1 tokens/sec

Actual performance can vary depending on hardware, model, context size, and configuration.

## Example

### Prompt

```text
Explain artificial intelligence in exactly 3 short, complete sentences.
Use simple English.
```

### Model Output

The model successfully generated a response explaining artificial intelligence in simple English.

## Project Structure

```text
local-llm-deployment-llama-cpp/
│
├── README.md
├── commands/
│   └── deployment-commands.txt
│
└── screenshots/
    ├── cuda-build.png
    ├── model-output.png
    └── gpu-usage.png
```

## Screenshots

### CUDA Build

![CUDA Build](screenshots/cuda-build.png)

### Model Output

![Model Output](screenshots/model-output.png)

### GPU Usage

![GPU Usage](screenshots/gpu-usage.png)

## Offline Capability

The llama.cpp runtime and GGUF model can be stored locally and used for inference without requiring an online AI API.

For this project, Kaggle was used as a GPU-based testing environment. Kaggle itself is a cloud environment, so it should not be considered the final demonstration of a physically offline local machine.

## Learning Outcomes

Through this project, I learned:

* How GGUF models are used with llama.cpp
* How to build llama.cpp with CUDA support
* How to configure GPU acceleration
* How to run an LLM from the command line
* How to monitor GPU utilization using `nvidia-smi`
* How to measure LLM inference performance
* How local LLM inference differs from cloud-based AI services

## Author

**Muhammad Hassaan Raza**

BS Computer Science
University of Chakwal
