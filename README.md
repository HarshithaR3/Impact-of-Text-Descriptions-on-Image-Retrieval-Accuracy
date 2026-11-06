# Impact of Text Descriptions on Image Retrieval Accuracy

## Overview

This project investigates how the length and quality of text descriptions (captions) influence image-text alignment and image retrieval accuracy. It explores how different levels of descriptive detail affect the ability of a model to retrieve relevant images from natural language queries.

The project integrates vision-language models, generative AI, and image retrieval techniques to evaluate three types of captions: **Short (4–6 words), Medium (8–10 words), and Long (13–15 words).**

An end-to-end pipeline was developed using BLIP, GPT-4, CLIP, and Stable Diffusion to generate captions, evaluate image-text similarity, perform image retrieval, and investigate the impact of caption length on image generation.

## Objectives

- Evaluate how caption length affects image retrieval accuracy.
- Investigate the impact of caption quality, specificity, and descriptive detail on image-text alignment.
- Generate semantically consistent captions of varying lengths.
- Compare retrieval performance using embedding-based similarity and Top-K accuracy.
- Fine-tune generative models to study the influence of caption length on image generation.
- Develop a web-based interface for interactive image generation and evaluation.

## System Architecture

The project consists of four major components:

### 1. Caption Generation – BLIP and GPT-4

- Used the BLIP (`blip-image-captioning-large`) model to generate medium-length captions (8–10 words) from product images.
- Used GPT-4 to transform medium captions into:
  - Short captions (4–6 words).
  - Long captions (13–15 words).
- Maintained semantic consistency across all three caption variations to ensure a fair comparison.

### 2. Image-Text Embedding and Retrieval – CLIP

- Used CLIP (ViT-B/32) to generate image and text embeddings.
- Generated normalized 512-dimensional embeddings for images and their corresponding captions.
- Calculated cosine similarity between image and caption embeddings.
- Evaluated retrieval performance using Top-K accuracy (Top-3, Top-5, Top-10, and Top-20).

### 3. Generative Model Fine-Tuning – Stable Diffusion

- Used Stable Diffusion 2.1 for text-to-image generation.
- Fine-tuned three separate model variants using short, medium, and long caption datasets.
- Generated images using the corresponding fine-tuned models.
- Evaluated image-text alignment using CLIP similarity scores.

### 4. Web-Based Interface

Developed a web interface using HTML, CSS, and JavaScript that allows users to:

- Enter custom text prompts.
- Select between short, medium, and long caption models.
- Generate images using the selected fine-tuned Stable Diffusion model.
- View generated images and their corresponding CLIP similarity scores.

## Workflow

1. Collect and preprocess product and natural images.
2. Generate medium-length captions using BLIP.
3. Generate short and long caption variations using GPT-4.
4. Extract image and text embeddings using CLIP.
5. Calculate cosine similarity and evaluate Top-K retrieval accuracy.
6. Fine-tune separate Stable Diffusion models for each caption length.
7. Generate images using the fine-tuned models.
8. Evaluate generated images using CLIP similarity scores.
9. Visualize and compare results through the web interface.

## Technologies Used

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Image Captioning | BLIP |
| Language Model | GPT-4 |
| Vision-Language Model | CLIP (ViT-B/32) |
| Image Generation | Stable Diffusion 2.1 |
| Deep Learning | PyTorch |
| Model Libraries | Hugging Face Transformers, Diffusers |
| Data Processing | Pandas, NumPy |
| Evaluation | Cosine Similarity, Top-K Accuracy |
| Frontend | HTML, CSS, JavaScript |
| Development Environment | Jupyter Notebook |

## Evaluation Metrics

The project evaluates the system using:

- **Cosine Similarity:** Measures the alignment between image and text embeddings.
- **Top-K Accuracy:** Measures whether the correct corresponding image appears within the top K retrieved results.
- **CLIP Similarity Score:** Evaluates the semantic alignment between generated images and their input text prompts.

Retrieval performance is compared across different caption lengths to understand how descriptive detail influences image retrieval.

## Key Features

- Automated image caption generation.
- GPT-4-based caption length variation.
- Multimodal image-text embedding and similarity evaluation.
- Top-K image retrieval benchmarking.
- Fine-tuning of Stable Diffusion models using different caption lengths.
- Interactive web interface for text-to-image generation and evaluation.

## Results and Analysis

The experiments compare retrieval accuracy across short, medium, and long captions using image-text similarity and Top-K retrieval metrics.

The project also compares image generation results from three independently fine-tuned Stable Diffusion models to investigate the relationship between caption length and generated image alignment.

Detailed experimental results, visualizations, and comparisons will be available in the repository.



