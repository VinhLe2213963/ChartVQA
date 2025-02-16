# UniChart: Enhancing Chart Visual Question Answering (ChartVQA)

## Introduction
Multimodal reasoning, particularly for visual language tasks such as analyzing plots and charts, is a complex challenge. For downstream tasks like Chart Visual Question Answering (ChartVQA), a model must effectively extract relevant information from chart images, organize the data efficiently, and perform reasoning over the extracted content.

Previous studies have introduced end-to-end models for these tasks, such as MATCHA, which achieves only 38.2% accuracy on the ChartQA benchmark. While end-to-end solutions are promising, they often require extensive fine-tuning on task-specific datasets and still struggle with complex reasoning queries.

Recent advancements in Vision-Language Models (VLMs) have improved visual representation techniques, yet integrating core image understanding with semantic reasoning remains a major limitation. In contrast, Large Language Models (LLMs) have demonstrated improved reasoning capabilities through in-context learning techniques such as Chain-of-Thought prompting, task decomposition, and rationale-enhanced fine-tuning.

Inspired by state-of-the-art methods, including Chart-PaLI5B, which currently achieves 81.32% accuracy on Chart-QA benchmarks, this work aims to improve the UniChart model. UniChart follows the same pretraining recipe and architecture as Donut and serves as the foundation for our improvements in ChartVQA.

## Key Enhancements
We introduce three key components to enhance UniChart for ChartVQA:

### 1. **Data Extraction**
- Extracts structured data from charts to generate JSON representations.
- Classifies visual elements (e.g., titles, colors) and reconstructs data tables.
- Inspired by DePlot, this step improves data accuracy, mitigating numerical reasoning errors due to faulty extraction.

### 2. **Data Estimation**
- Trains the model to predict data tables when parts of the chart are missing or occluded.
- Enables robustness in handling incomplete or distorted visual information.

### 3. **Question Answering with Rationale Generation**
- Integrates a Chain-of-Thought-inspired approach to generate both answers and step-by-step rationales.
- Handles both visual (e.g., color identification, trend recognition) and numerical (e.g., comparisons, calculations) reasoning tasks.
- Incorporates parameter-efficient fine-tuning, freezing parameters after the data extraction phase and introducing new parameters for downstream tasks.

## Goals & Contributions
- Improve the accuracy of UniChart on ChartVQA tasks.
- Enhance interpretability through answer explanations and rationale generation.
- Scale model capacity efficiently while keeping trainable parameters consistent.
- Develop a robust system capable of handling incomplete or noisy chart data.


