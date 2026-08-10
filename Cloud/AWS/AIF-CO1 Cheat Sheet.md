
# AWS Certified AI Practitioner (AIF-C01) Master Cheat Sheet

## Exam Structure & Domain Weights

- **Total Questions:** 65 (50 scored, 15 unscored experimental) | **Passing Score:** 700 / 1000

- **Question Types:** Multiple choice, multiple response, ordering, matching (No coding or math calculations)


|**Domain**|**Weight**|**Core Focus**|
|---|---|---|
|**Domain 1: Fundamentals of AI and ML**|20%|AI/ML/DL terminology, ML lifecycle, inference types, ML problem mapping|
|**Domain 2: Fundamentals of Generative AI**|24%|Foundation Models (FMs), LLMs, Diffusion, customization tradeoffs|
|**Domain 3: Applications of Foundation Models**|28%|Prompt engineering, RAG, Bedrock ecosystem, evaluation metrics, parameters|
|**Domain 4: Guidelines for Responsible AI**|14%|6 Pillars, bias taxonomy, SageMaker Clarify, Bedrock Guardrails, A2I|
|**Domain 5: Security, Compliance, & Governance**|14%|Shared responsibility, prompt attacks, data privacy, model cards, audit tools|

## Domain 1: Fundamentals of AI and ML (20%)

### Core Taxonomy

- **Artificial Intelligence (AI):** Broad field of computer science creating systems that mimic human intelligence.
    
- **Machine Learning (ML):** Subset of AI where algorithms learn patterns from data without explicit programming.
    
- **Deep Learning (DL):** Subset of ML using multi-layered artificial neural networks (ANNs) for unstructured data (images, audio).
    
- **Generative AI (GenAI):** Subset of DL powered by Foundation Models capable of generating new content (text, code, images).
    
- **Agentic AI:** AI systems capable of autonomous planning, tool usage, and execution across multi-step goals.


### Machine Learning Paradigms

- **Supervised Learning:** Trained on **labeled data** ($X \rightarrow Y$).
    
    - _Regression:_ Predicts continuous numeric values (e.g., house prices).
        
    - _Classification:_ Predicts discrete class labels (e.g., spam vs. non-spam).
    
- **Unsupervised Learning:** Trained on **unlabeled data** to discover hidden patterns.
    
    - _Clustering:_ Groups similar data points together (e.g., customer segmentation via K-Means).
        
    - _Dimensionality Reduction:_ Compresses features while preserving variance (e.g., PCA).
    
- **Reinforcement Learning (RL):** Agent learns optimal decisions through **trial and error** using rewards and penalties.


### Inference Deployment Modes

- **Real-time Inference:** Low-latency, synchronous processing for immediate responses.
    
- **Batch Inference:** High-throughput processing of large datasets on a scheduled basis.
    
- **Asynchronous Inference:** For large payload sizes (up to 1GB) and long processing times (up to 1 hour) with queuing.
    
- **Serverless Inference:** For workloads with unpredictable or intermittent traffic (auto-scales to zero).


## Domain 2: Fundamentals of Generative AI (24%)

### Foundation Models (FMs)

- **Large Language Models (LLMs):** Transformer-based models trained on massive text corpora for generation, reasoning, and translation (e.g., Claude, Llama, Amazon Titan).
    
- **Diffusion Models:** Generative models that create images or video by iteratively removing noise from a random tensor (e.g., Stable Diffusion).
    
- **Multimodal Models:** FMs that ingest and process multiple data modalities simultaneously (text, image, audio, video).


### Model Customization Spectrum

```
[ Low Cost / Low Effort ] ───────────────────────────────────► [ High Cost / High Effort ]

  Prompt Engineering  ──►  RAG (Knowledge Bases)  ──►  Fine-Tuning  ──►  Pre-Training
  (In-context learning)    (Dynamic, private data)   (Task adaptation)   (New domain/lang)
```

- **In-Context Learning (Prompting):** Guiding outputs via prompt text without modifying model weights.
    
- **Retrieval-Augmented Generation (RAG):** Connecting an FM to external vector databases to retrieve private/real-time context.
    
- **Fine-Tuning:** Updating base model weights using a smaller, task-specific **labeled dataset**.
    
- **Continued Pre-Training:** Training an existing FM on massive **unlabeled** domain-specific text (e.g., medical journals).


## Domain 3: Applications of Foundation Models (28%)

### Prompt Engineering Techniques

- **Zero-Shot:** Requesting a task directly with zero examples.
    
- **Few-Shot:** Providing 1–5 input-output examples inside the prompt to establish an output format.
    
- **Chain-of-Thought (CoT):** Adding _"Think step by step"_ to force the model to output intermediate reasoning steps before giving the final answer.
    
- **Prompt Chaining:** Breaking a complex task into sequential sub-prompts where Output 1 becomes Input 2.


### Model Inference Parameters

- **Temperature ($0.0 - 1.0$):** Controls output randomness. Lower ($0.0$) = deterministic/focused; Higher ($1.0$) = creative/random.
    
- **Top-P (Nucleus Sampling):** Samples from the smallest pool of tokens whose cumulative probability exceeds $P$ (e.g., $0.9 = \text{top 90\%}$).
    
- **Top-K:** Restricts token choices to a fixed number ($K$) of the most probable next words.
    
- **Stop Sequences:** Specific string tokens that force the model to immediately cease output generation.


### Evaluation Metrics

- **ROUGE:** Evaluates **summarization** quality by measuring n-gram overlap between generated and reference text.
    
- **BLEU:** Standard metric for **machine translation**, measuring precision of n-grams against human translations.
    
- **BERTScore:** Evaluates **semantic similarity** using vector embeddings rather than exact word matching.
    
- **Perplexity:** Measures a language model's uncertainty when predicting the next word (Lower = Better).


## Domain 4: Guidelines for Responsible AI (14%)

### The 6 Responsible AI Pillars

1. **Fairness:** Treating all demographic groups equitably without systemic disadvantage.
    
2. **Explainability:** Providing human-understandable insights into why a model made a specific prediction.
    
3. **Transparency:** Disclosing to users that they are interacting with an AI system and citing data sources.
    
4. **Privacy & Security:** Safeguarding training and inference data against PII leakage and unauthorized access.
    
5. **Robustness & Reliability:** Ensuring consistent performance and resistance to adversarial inputs.
    
6. **Governance & Accountability:** Maintaining human oversight, audit trails, and legal compliance.


### Taxonomy of Bias

- **Sampling Bias:** Training dataset does not accurately represent the real-world population.
    
- **Measurement Bias:** Selected features or labels are flawed or noisy proxies for the target variable.
    
- **Historical Bias:** Dataset accurately reflects past data, but that data contains societal inequalities.
    
- **Confirmation Bias:** Annotators label data in a way that aligns with pre-existing preconceptions.


### Key Responsible AI Services

- **Amazon SageMaker Clarify:** Detects bias pre-training (e.g., Class Imbalance) and post-training (e.g., DPPL), and provides feature attribution using **SHAP (SHapley Additive exPlanations)**.
    
- **Amazon Bedrock Guardrails:** Enforces safety policies across FMs via denied topics, profanity/word filters, PII redaction, and RAG contextual grounding checks.
    
- **Amazon Augmented AI (A2I):** Implements **Human-in-the-Loop (HITL)** workflows to route low-confidence ML predictions to human reviewers.


## Domain 5: Security, Compliance, and Governance (14%)

### AWS Shared Responsibility Model for AI

```
                        MANAGED AI (e.g., Bedrock)           INFRASTRUCTURE ML (e.g., SageMaker EC2)
                 ┌──────────────────────────────────────┐   ┌──────────────────────────────────────┐
CUSTOMER         │  • IAM Access Policies               │   │  • Guest OS & Application Patching   │
RESPONSIBILITY   │  • Input Data & Prompts              │   │  • VPC & Security Group Rules        │
                 │  • Guardrail Configurations          │   │  • Model Weights & Container Images  │
                 └──────────────────────────────────────┘   └──────────────────────────────────────┘
────────────────────────────────────────────────────────────────────────────────────────────────────
AWS              ┌──────────────────────────────────────┐   ┌──────────────────────────────────────┐
RESPONSIBILITY   │  • Base Model Security & Storage     │   │  • Physical Datacenter Security      │
                 │  • Managed Service Infrastructure    │   │  • Hardware & Hypervisor             │
                 └──────────────────────────────────────┘   └──────────────────────────────────────┘
```

> **Exam Fact:** AWS **never** uses customer inputs or outputs submitted to Amazon Bedrock to train base models or share with third parties.

### Generative AI Security Threats

- **Direct Prompt Injection (Jailbreaking):** Crafting user prompts to override system instructions and safety filters.
    
- **Indirect Prompt Injection:** Embedding malicious instructions inside external content (e.g., PDFs or websites) retrieved by RAG or Agents.
    
- **Data Poisoning:** Injecting bad or backdoor data into fine-tuning datasets to manipulate model behavior.


## Master AWS AI/ML Service Mapping Matrix

|**AWS Service**|**Primary Purpose**|**Exam Keyword Triggers**|
|---|---|---|
|**Amazon Bedrock**|Serverless platform for building GenAI apps using FMs via unified API.|_API access to Claude/Llama/Titan, Knowledge Bases, Agents, Guardrails_|
|**Amazon SageMaker**|End-to-end ML platform for building, training, and deploying custom models.|_Custom ML pipelines, Jupyter notebooks, model training, endpoint hosting_|
|**SageMaker Canvas**|No-code visual interface for building ML models.|_Business analysts, zero coding, drag-and-drop ML, automated forecasting_|
|**SageMaker Data Wrangler**|Visual tool to clean, normalize, and prepare tabular/image data.|_Data preparation, feature engineering, 300+ built-in transforms_|
|**SageMaker Clarify**|Detects dataset/model bias and explains predictions via SHAP.|_Bias detection, pre-training/post-training bias, feature importance_|
|**SageMaker Model Cards**|Centralized documentation for AI model governance and metadata.|_Model nutrition labels, governance documentation, intended use_|
|**SageMaker Model Registry**|Central repository for versioning and approving ML models.|_Model catalog, versioning, deployment approvals (Pending -> Approved)_|
|**Amazon Rekognition**|Computer vision API for image and video analysis.|_Face detection, object tracking, optical character recognition, celebrity recognition_|
|**Amazon Comprehend**|Natural Language Processing (NLP) service for text analysis.|_Sentiment analysis, key phrase extraction, entity recognition, PII detection in text_|
|**Amazon Textract**|Intelligent Document Processing (IDP) beyond standard OCR.|_Extract text/tables/forms from PDFs, scanned documents, invoices_|
|**Amazon Transcribe**|Automatic Speech Recognition (ASR) service.|_Audio-to-text, medical transcription, call center recording analysis_|
|**Amazon Polly**|Text-to-Speech (TTS) service using neural voices.|_Text-to-audio, natural sounding voice generation, SSML support_|
|**Amazon Translate**|Neural machine translation service.|_Language translation, multilingual localization, real-time translation_|
|**Amazon Lex**|Conversational AI framework for building chatbots.|_Voice/text chatbots, conversational interfaces, powers Alexa engine_|
|**Amazon Kendra**|Enterprise search engine powered by ML and natural language.|_Intelligent enterprise search, search across S3/SharePoint/Confluence_|
|**Amazon Personalize**|Real-time personalized recommendation engine.|_Product recommendations, personalized re-ranking, user behavior ML_|
|**Amazon Forecast**|Time-series forecasting service using machine learning.|_Supply chain demand forecasting, financial planning, inventory projection_|
|**Amazon Q**|Generative AI assistant tailored for business and enterprise code.|_Q Business (enterprise search/chat), Q Developer (coding assistance)_|
|**Amazon Augmented AI (A2I)**|Human-in-the-loop workflow management for ML outputs.|_Human review, low confidence score routing, human verification_|
|**Amazon Macie**|Data security service using ML to discover sensitive data in S3.|_PII discovery in S3, data classification, sensitive data alerts_|
|**AWS KMS**|Key Management Service for data-at-rest encryption.|_Encryption keys, CMK, encrypting S3 buckets/SageMaker volumes_|
|**AWS PrivateLink**|Private VPC endpoint connectivity for AWS AI services.|_No public internet exposure, private VPC network traffic_|
|**AWS CloudTrail**|API logging and operational auditing service.|_Who called InvokeModel, API audit history, user activity tracking_|
|**AWS Config**|Continuous resource configuration monitoring and compliance auditing.|_Resource settings auditing, non-compliant resource alerts_|
|**AWS Audit Manager**|Automated compliance evidence gathering against regulatory standards.|_Audit reports, evidence collection, regulatory frameworks (HIPAA/NIST)_|
|**AWS Artifact**|Portal for downloading official AWS compliance and ISO reports.|_AWS audit reports, SOC reports, third-party certification downloads_|