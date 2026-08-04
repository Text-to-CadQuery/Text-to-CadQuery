# Text-to-CadQuery

This repository supports our IEEE T-ASE submission, building on the foundations of **Text2CAD** and **DeepCAD**. It includes data annotation, model training, inference, and evaluation pipelines across six open-source LLMs.

## Repository Structure

- `data_annotation/`  
  Scripts for annotating CAD sequences using Gemini 2.0 Flash on top of the Text2CAD dataset.
  The full annotated dataset is available here: [CadQuery.zip](https://huggingface.co/ricemonster/NeurIPS11092/blob/main/CadQuery.zip)

- `train/`  
  Training scripts for six open-source models (CodeGPT, Gemma, GPT-2, Mistral, Qwen).  
  Finetuned models are available on [HuggingFace](https://huggingface.co/ricemonster).

- `inference/`  
  Step-by-step pipeline for evaluating the finetuned models:
  - `step1_generate_CadQuery`: Use finetuned models to generate CadQuery code from natural language prompts.
  - `step2_clean_run_CadQuery`: Extract valid Python code from model outputs and execute it to generate STL files.
  - `step3_rendering`: Render STL files using Blender.
  - `step4_gemini_eval`: Evaluate rendered 3D models using Gemini 2.0 Flash.
  - `step5_compute_metrics`: Compute quantitative metrics such as Chamfer Distance and other geometric similarity scores.

## Acknowledgements

We gratefully acknowledge the authors of [Text2CAD](https://github.com/SadilKhan/Text2CAD) and [DeepCAD](https://github.com/ChrisWu1997/DeepCAD) for their foundational contributions and datasets.

## References

- [Text2CAD](https://github.com/SadilKhan/Text2CAD)  
  Mohammad Sadil Khan*, Sankalp Sinha*, Talha Uddin Sheikh, Didier Stricker, Sk Aziz Ali, Muhammad Zeshan Afzal  
  *Text2CAD: Generating Sequential CAD Designs from Beginner-to-Expert Level Text Prompts*

- [DeepCAD](https://github.com/ChrisWu1997/DeepCAD)  
  Rundi Wu, Chang Xiao, Changxi Zheng  
  *DeepCAD: A Deep Generative Network for Computer-Aided Design Models*  


