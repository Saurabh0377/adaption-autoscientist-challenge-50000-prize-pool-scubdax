# rural_india_triage_protocols: Rural India Emergency Triage Protocols Dataset

# adaption-autoscientist-challenge-50000-prize-pool-scubdax

**Adaption AutoScientist Challenge x HackIndia 2026 — Healthcare Track**
* **Team:** ScubdaX (HackIndia ID: HI015354)
* **Category:** Healthcare / Emergency Medicine / Clinical Decision Support
* **Dataset Size:** 11,217 instruction-tuning pairs
* **License:** CC-BY-SA 4.0
## The Problem & Solution
General-purpose AI models fail in rural Indian healthcare because they cannot parse the colloquial, mixed-language (Hindi/English) symptomatic reporting used by frontline workers. This failure delays critical triage and medical intervention. 
We solved this by fine-tuning a model via Adaption AutoScientist on our `rural_india_triage_protocols` dataset. The resulting model accurately translates unstructured, culturally specific medical vernacular into standardized clinical assessments, systemic risk calculations, and actionable emergency triage codes.
---
## How We Used Adaption at Every Step
This section documents our end-to-end usage of the Adaption platform for building this dataset and training our healthcare triage model. Every step below was executed on Adaption's infrastructure.
### Step 1: Account Setup & Credit Activation
* Created account at adaptionlabs.ai and activated 1,000 free platform credits.
* Joined the official Discord channel `#autoscient-challenge` for support and office hours.
### Step 2: Dataset Ingestion via Adaptive Data
We used Adaptive Data — Adaption's real-world training data optimization platform — to ingest and structure our raw clinical data.
* Uploaded raw clinical vignettes, patient histories, and field protocol notes in English, Hindi, and Tamil.
* Adaptive Data automatically parsed and normalized the multilingual inputs across 242 supported languages.
* The platform evaluated data quality, flagged inconsistencies, and suggested structural improvements.
* **Result:** Achieved a **21.2% relative improvement** in data quality, pushing our dataset grade to an 'A' (57.7th percentile) on the Adaption dashboard.
### Step 3: Data Adaptation & Augmentation
Using Adaptive Data's optimization engine:
* **Instruction-tuning format generation:** Raw clinical cases were automatically converted into structured instruction / input / output / enhanced_prompt / enhanced_completion pairs.
* **Role-based prompt engineering:** The platform generated expert-level role prompts from minimal seed prompts.
* **Multilingual expansion:** Hindi and Tamil patient quotes were preserved verbatim while clinical reasoning outputs were standardized in English for model consistency.
### Step 4: Model Training with AutoScientist
We ran the AutoScientist training loop to co-optimize our data and training recipe end-to-end.
* **Base model:** `adaption_llama_3.3_70b_instru`
* **Training objective:** Instruction-following with an emphasis on clinical reasoning accuracy.
* **Convergence criteria:** Model was trained until validation loss plateaued and triage classification accuracy exceeded baseline.
* **Features leveraged:** Automated data-recipe co-optimization and real-time convergence monitoring.
### Step 5: Beat the Baseline
AutoScientist evaluated our model against Adaption's held-out test set for the Healthcare category. We achieved significant, measurable performance improvements over the baseline model:
* **76% Overall Win Rate** against the base model.
* **73% Medical Task Win Rate** across all tasks processed in the Medical category.
### Step 6: Open Release
Following the hackathon requirements, we published:
* Model weights on [Hugging Face](#) *(Insert Link)*
* Dataset on [Hugging Face Datasets](https://huggingface.co/datasets/Saurabhkumarozp61/rural_india_triage_protocols) and [Kaggle](https://www.kaggle.com/datasets/saurabhkumaropz61/adaption-rural-india-triage-protocols)
* Model card with full documentation of training parameters, evaluation metrics, and intended use.
### Step 7: Community Engagement
* Shared project on X and LinkedIn, tagging `@adaption_ai` and Adaption.
* *(Include link to your X post here)*
---
## Dataset Overview
`rural_india_triage_protocols` contains 11,217 high-quality medical reasoning pairs covering 14+ critical emergency conditions in rural Indian healthcare settings:

| Condition | Entries |
| :--- | :--- |
| General Medical Q&A | 10,910 |
| Severe Acute Malnutrition (SAM/Kwashiorkor) | 109 |
| Tuberculosis (Pulmonary) | 59 |
| Heat Stroke / Environmental Emergency | 41 |
| Asthma / Respiratory Exacerbation | 19 |
| Obstetric Emergency (Pre-eclampsia/Eclampsia) | 16 |
| Pediatric Pneumonia / Respiratory Distress | 16 |
| Cholera / Severe Dehydration | 11 |
| Rabies / Zoonotic Exposure | 9 |
| Malaria / Protozoal Infection | 7 |
| Dengue / Arboviral Fever | 6 |
| Neonatal Sepsis | 5 |
| Toxicology / Organophosphate Poisoning | 4 |
| Postpartum Hemorrhage (PPH) | 3 |
| Snakebite Envenomation | 3 |
| Neonatal Jaundice / Kernicterus | 2 |

**Languages:** English (10,867), Mixed/Transliterated (327), Hindi (19), Tamil (4)
**Data splits:** Training (90%), Validation (5%), Test (5%)
---
## Citation
```bibtex
@dataset{rural_india_triage_protocols,
  title={Rural India Emergency Triage Protocols (rural_india_triage_protocols): A Multilingual Clinical Decision-Support Dataset},
  author={ScubdaX Team},
  year={2026},
  publisher={Hugging Face / Kaggle},
  howpublished={\url{[https://huggingface.co/datasets/Saurabhkumarozp61/rural_india_triage_protocols](https://huggingface.co/datasets/Saurabhkumarozp61/rural_india_triage_protocols)}, \url{[https://www.kaggle.com/datasets/saurabhkumaropz61/adaption-rural-india-triage-protocols](https://www.kaggle.com/datasets/saurabhkumaropz61/adaption-rural-india-triage-protocols)}}
}


Built with Adaption. Adaptive AI infrastructure for domain-specific model training.
adaptionlabs.ai · @adaption_ai
