## Control Industrial Automation System with Large Language Models
This repository contains detailed information and video demonstration accompanying the paper titled "Control Industrial Automation System with Large Language Models", submitted to IEEE ICRA 2025.

A preprint of this paper is available on arXiv.
> Y. Xia, N. Jazdi, J. Zhang, C. Shah and M. Weyrich, Control Industrial Automation System with Large Language Models, 2024, arXiv preprint.

## Potential Use Case Demonstration:
![30s_GPT4Automation](https://github.com/YuchenXia/GPT4IndustrialAutomation/assets/39265101/b4b700fa-5262-44a3-9fdd-6eb4930dae23)

## Prototypical Implementation in Laboratory Environment
![lab_demo_4_scenes](lab_demo_4_scenes.gif)

Full video: Control Automation System with Large Language Models (2:58) https://youtu.be/GhBoxGfjRIE


## Event-Based Control:
![event_based_control](event_based_control.gif)

## The System Design
![system_design](system_design.gif)

## Model Fine-Tuning:
We apply supervised fine-tuning **(SFT)** to assess how training open-source models on the collected dataset improve the LLM’s performance for this specific downstream task. This training has the potential to enable the customization of a general LLM for intelligent control of specialized automation equipment. For GPT-4o, we use OpenAI’s proprietary fine-tuning API to explore the potential capabilities of LLMs, even though the training methods could be different.

>**Full fine-tuning (SFT):** Llama-3-70B-Instruct, Llama-3-8B-Instruct, Qwen2-7B-Instruct, Mistral-7Bx8-Instruct-v0.2, Mistral-7B-Instruct-v0.2
>
> Epochs: 1; Learning Rate: 1e-5; Batch Size: 16; Training Data Size: 0.2 million tokens

>**LoRA fine-tuning (SFT):** Qwen2-72B-Instruct
>
>LoRA-Rank: 32; LoRA-alpha: 32; Epochs: 1; Learning Rate: 1e-5; Batch Size: 16; Training Token Size: 0.2 million tokens

>**OpenAI’s API fine-tuning:** GPT-4o;
>
>Training Data Size: 0.2 million tokens


## Evaluation Results:
| Evaluation based on 100 test points | GPT-4o | Llama-3-70B-Instruct | Llama-3-8B-Instruct | Qwen2-72B-Instruct | Qwen2-7B-Instruct | Mistral-7Bx8-Instruct-v0.2 | Mistral-7B-Instruct-v0.2 |
|----------------------------------------|--------|----------------------|---------------------|--------------------|-------------------|-----------------------------|--------------------------|
| **Pre-trained (all)**                  | 81% \| 4.7 | 75% \| 4.3           | 37% \| 2.8          | 70% \| 4.0         | 65 \| 3.7         | 29% \| 2.4                  | 45% \| 2.9               |
| **Pre-trained (SOP)**                  | 100% \| 5.0 | 87% \| 4.5           | 53% \| 3.1          | 85% \| 4.5         | 63% \| 3.6        | 34% \| 2.4                  | 37% \| 2.5               |
| **Pre-trained (Unexpected)**           | 41% \| 4.0 | 50% \| 3.8           | 3% \| 2.2           | 38% \| 3.0         | 69% \| 4.0        | 19% \| 2.3                  | 63% \| 3.7               |
| **SFT (all)**                          | 100% \| 5.0 | 95% \| 4.8           | 96% \| 4.9          | * 66% \| 3.9       | 97% \| 4.9        | 45% \| 3.1                  | \*\*N.A.                 |
| **SFT (SOP)**                          | 100% \| 5.0 | 94% \| 4.8           | 99% \| 4.9          | * 82% \| 4.4       | 97% \| 4.9        | 61% \| 3.6                  | \*\*N.A.                 |
| **SFT (Unexpected)**                   | 100% \| 5.0 | 97% \| 4.9           | 91% \| 4.7          | * 31% \| 2.8       | 97% \| 5.0        | 9% \| 2.3                   | \*\*N.A.                 |

Notes:
- Values representation: (accuracy of their generated commands%) \| (averaged reason plausibility 1-5)
- Details of the evaluation data are organized in [evaluation_data.xlsx](evaluation_data.xlsx) 
- \* We ran out of GPU capacity and used LoRA instead of full fine-tuning for the Qwen2-72B model.
- \*\* N.A.: Our full-fine-tuning made Mistral-7B model unstable, and it generated unusable echo texts.


## Technology Readiness Level (TRL)
![nasa_trl_meter](nasa_trl_meter.jpg)

## Other related papers
This research is a continuation of previous works:
> Y. Xia, M. Shenoy, N. Jazdi and M. Weyrich, **Towards autonomous system: flexible modular production system enhanced with large language model agents**, 2023 IEEE 28th International Conference on Emerging Technologies and Factory Automation (ETFA), Sinaia, Romania, 2023, pp. 1-8, doi: [10.1109/ETFA54631.2023.10275362](https://doi.org/10.1109/ETFA54631.2023.10275362). 

For a similar topic on **LLM agent system** and **simulation model**, one of our papers was acknowledged with the **Best Paper Award** at IEEE ETFA 2024, held on September 10-13, 2024 in Padova, Italy.

A preprint of this paper is available on arXiv.
> Y. Xia, D. Dittler, N. Jazdi, H. Chen and M. Weyrich, **LLM experiments with simulation: Large Language Model Multi-Agent System for Process Simulation Parametrization in Digital Twins**, 2024, arXiv preprint, https://doi.org/10.48550/arXiv.2405.18092.

Other similar works can be found at Google Scholar: https://scholar.google.de/citations?user=hi1srxkAAAAJ
