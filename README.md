# rural_india_triage_protocols: Rural India Emergency Triage Protocols Dataset

## Adaption AutoScientist Challenge x HackIndia 2026 — Healthcare Track

**Team:** ScubdaX  
**Category:** Healthcare / Emergency Medicine / Clinical Decision Support  
**Dataset Size:** 11,217 instruction-tuning pairs  
**License:** CC-BY-SA 4.0

---

## How We Used Adaption at Every Step

This section documents our end-to-end usage of the **Adaption** platform for building this dataset and training our healthcare triage model. Every step below was executed on Adaption's infrastructure.

### Step 1: Account Setup & Credit Activation

- Created account at [adaptionlabs.ai](https://adaptionlabs.ai)
- Activated **1,000 free platform credits** provided for the hackathon
- Joined the official Discord channel `#autoscient-challenge` for support and office hours

### Step 2: Dataset Ingestion via Adaptive Data

We used **Adaptive Data** — Adaption's real-world training data optimization platform — to ingest and structure our raw clinical data.

**What we did:**
- Uploaded raw clinical vignettes, patient histories, and field protocol notes in **English, Hindi, and Tamil**
- Adaptive Data automatically parsed and normalized the multilingual inputs across **242 supported languages**
- The platform evaluated data quality, flagged inconsistencies, and suggested structural improvements
- We iteratively refined the dataset using Adaptive Data's feedback loops until all entries met clinical accuracy standards

**Key feature used:** Multimodal input support allowed us to combine text-based patient narratives with structured vital sign data in a single pipeline.

### Step 3: Data Adaptation & Augmentation

Using Adaptive Data's optimization engine:

- **Instruction-tuning format generation:** Raw clinical cases were automatically converted into structured `instruction` / `input` / `output` / `enhanced_prompt` / `enhanced_completion` pairs
- **Role-based prompt engineering:** The platform generated expert-level role prompts (e.g., "Act as an expert toxicologist...") from minimal seed prompts
- **Multilingual expansion:** Hindi and Tamil patient quotes were preserved verbatim while clinical reasoning outputs were standardized in English for model consistency
- **Triage consistency validation:** Adaptive Data cross-checked all triage classifications (RED/YELLOW/GREEN) against WHO/IMNCI protocols

### Step 4: Model Training with AutoScientist

We ran the **AutoScientist training loop** to co-optimize our data and training recipe end-to-end.

**Configuration:**
- **Base model:** Selected from Adaption's model hub (domain-appropriate foundation model)
- **Training objective:** Instruction-following with emphasis on clinical reasoning accuracy
- **Hyperparameter search:** AutoScientist automatically explored learning rates, batch sizes, and LoRA configurations
- **Convergence criteria:** Model was trained until validation loss plateaued and triage classification accuracy exceeded baseline

**AutoScientist features leveraged:**
- Automated data-recipe co-optimization
- Free compute allocation throughout the competition
- Real-time convergence monitoring and early stopping

### Step 5: Baseline Evaluation & Improvement

- AutoScientist evaluated our model against Adaption's **held-out test set** for the Healthcare category
- We achieved **measurable percentage improvement** over the baseline model on:
  - Triage classification accuracy (RED/YELLOW/GREEN)
  - Differential diagnosis correctness
  - Protocol actionability scoring
- Without this improvement, we would not have qualified for prize eligibility

### Step 6: Open Release

Following the hackathon requirements, we published:

- **Model weights** on [Hugging Face](https://huggingface.co/scubdax/rural_india_triage_protocols-model)
- **Dataset** on [Hugging Face Datasets](https://huggingface.co/datasets/scubdax/rural_india_triage_protocols) and [Kaggle](https://kaggle.com/datasets/scubdax/rural_india_triage_protocols)
- **Model card** with full documentation of training parameters, evaluation metrics, and intended use
- **This README** explaining Adaption usage at every step

### Step 7: Community Engagement

- Shared project on LinkedIn and X, tagging `@adaption_ai` and `Adaption`
- Deployed a live demo for interactive triage protocol generation
- Participated in Adaption research team office hours for feedback and iteration

---

## Dataset Overview

rural_india_triage_protocols contains **11,217 high-quality medical reasoning pairs** covering 14+ critical emergency conditions in rural Indian healthcare settings:

| Condition | Entries |
|-----------|---------|
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
  title={Rural India Emergency Triage Protocols (rural_india_triage_protocols): 
         A Multilingual Clinical Decision-Support Dataset},
  author={ScubdaX Team},
  year={2026},
  publisher={Hugging Face / Kaggle},
  howpublished={\url{# rural_india_triage_protocols: Rural India Emergency Triage Protocols Dataset

## Adaption AutoScientist Challenge x HackIndia 2026 — Healthcare Track

**Team:** ScubdaX  
**Category:** Healthcare / Emergency Medicine / Clinical Decision Support  
**Dataset Size:** 11,217 instruction-tuning pairs  
**License:** CC-BY-SA 4.0

---

## How We Used Adaption at Every Step

This section documents our end-to-end usage of the **Adaption** platform for building this dataset and training our healthcare triage model. Every step below was executed on Adaption's infrastructure.

### Step 1: Account Setup & Credit Activation

- Created account at [adaptionlabs.ai](https://adaptionlabs.ai)
- Activated **1,000 free platform credits** provided for the hackathon
- Joined the official Discord channel `#autoscient-challenge` for support and office hours

### Step 2: Dataset Ingestion via Adaptive Data

We used **Adaptive Data** — Adaption's real-world training data optimization platform — to ingest and structure our raw clinical data.

**What we did:**
- Uploaded raw clinical vignettes, patient histories, and field protocol notes in **English, Hindi, and Tamil**
- Adaptive Data automatically parsed and normalized the multilingual inputs across **242 supported languages**
- The platform evaluated data quality, flagged inconsistencies, and suggested structural improvements
- We iteratively refined the dataset using Adaptive Data's feedback loops until all entries met clinical accuracy standards

**Key feature used:** Multimodal input support allowed us to combine text-based patient narratives with structured vital sign data in a single pipeline.

### Step 3: Data Adaptation & Augmentation

Using Adaptive Data's optimization engine:

- **Instruction-tuning format generation:** Raw clinical cases were automatically converted into structured `instruction` / `input` / `output` / `enhanced_prompt` / `enhanced_completion` pairs
- **Role-based prompt engineering:** The platform generated expert-level role prompts (e.g., "Act as an expert toxicologist...") from minimal seed prompts
- **Multilingual expansion:** Hindi and Tamil patient quotes were preserved verbatim while clinical reasoning outputs were standardized in English for model consistency
- **Triage consistency validation:** Adaptive Data cross-checked all triage classifications (RED/YELLOW/GREEN) against WHO/IMNCI protocols

### Step 4: Model Training with AutoScientist

We ran the **AutoScientist training loop** to co-optimize our data and training recipe end-to-end.

**Configuration:**
- **Base model:** Selected from Adaption's model hub (domain-appropriate foundation model)
- **Training objective:** Instruction-following with emphasis on clinical reasoning accuracy
- **Hyperparameter search:** AutoScientist automatically explored learning rates, batch sizes, and LoRA configurations
- **Convergence criteria:** Model was trained until validation loss plateaued and triage classification accuracy exceeded baseline

**AutoScientist features leveraged:**
- Automated data-recipe co-optimization
- Free compute allocation throughout the competition
- Real-time convergence monitoring and early stopping

### Step 5: Baseline Evaluation & Improvement

- AutoScientist evaluated our model against Adaption's **held-out test set** for the Healthcare category
- We achieved **measurable percentage improvement** over the baseline model on:
  - Triage classification accuracy (RED/YELLOW/GREEN)
  - Differential diagnosis correctness
  - Protocol actionability scoring
- Without this improvement, we would not have qualified for prize eligibility

### Step 6: Open Release

Following the hackathon requirements, we published:

- **Model weights** on [Hugging Face](https://huggingface.co/scubdax/rural_india_triage_protocols-model)
- **Dataset** on [Hugging Face Datasets](https://huggingface.co/datasets/scubdax/rural_india_triage_protocols) and [Kaggle](https://kaggle.com/datasets/scubdax/rural_india_triage_protocols)
- **Model card** with full documentation of training parameters, evaluation metrics, and intended use
- **This README** explaining Adaption usage at every step

### Step 7: Community Engagement

- Shared project on LinkedIn and X, tagging `@adaption_ai` and `Adaption`
- Deployed a live demo for interactive triage protocol generation
- Participated in Adaption research team office hours for feedback and iteration

---

## Dataset Overview

rural_india_triage_protocols contains **11,217 high-quality medical reasoning pairs** covering 14+ critical emergency conditions in rural Indian healthcare settings:

| Condition | Entries |
|-----------|---------|
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
@dataset{rural_india_triage_protocols_2026,
  title={Rural India Emergency Triage Protocols (rural_india_triage_protocols): 
         A Multilingual Clinical Decision-Support Dataset},
  author={ScubdaX Team},
  year={2026},
  publisher={Hugging Face / Kaggle},
  howpublished={\url{https://huggingface.co/datasets/scubdax/rural_india_triage_protocols}}
}
```

---

**Built with Adaption.** Adaptive AI infrastructure for domain-specific model training.  
[adaptionlabs.ai](https://adaptionlabs.ai) · [@adaption_ai](https://x.com/adaption_ai)
}}
}
```

---

**Built with Adaption.** Adaptive AI infrastructure for domain-specific model training.  
[adaptionlabs.ai](https://adaptionlabs.ai) · [@adaption_ai](https://x.com/adaption_ai)
