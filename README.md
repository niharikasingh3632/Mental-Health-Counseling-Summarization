# 🧠 Mental Health Counseling Summarization

This project explores automated summarization of mental health counseling sessions using transformer-based models. With a rising demand for mental health services, counselors often struggle to document and retain key therapeutic insights across sessions. Our approach aims to generate structured and concise summaries from therapy conversations to support clinical decision-making and longitudinal patient care.

---

## 📌 Problem Statement

Mental health counseling plays a vital role in supporting individuals experiencing psychological challenges such as depression, anxiety, trauma, and other disorders. However, as the number of patients grows, counselors face increasing difficulty in keeping track of previous session details and patient progress.

Manual summarization of sessions is time-consuming and prone to error due to the unstructured nature of therapeutic dialogue. This project investigates how automated summarization can assist in capturing critical information such as:

- Patient symptoms and history  
- Emotional state and concerns  
- Therapist interventions and advice  
- Treatment plans and progress markers  

---

## 📚 Dataset

We use the **MEMO** dataset, an augmented collection based on the HOPE dataset. It contains:

- **212 real counseling conversations** (12,900 utterances)
- **4 labeled categories**:  
  - Symptom and History  
  - Patient Discovery  
  - Reflecting  
  - Discussion Filler

The dataset was constructed from publicly available therapy session videos (e.g., YouTube), and annotated by mental health professionals to ensure clinical relevance and accuracy.

---

## 🔧 Methodology

Our summarization pipeline follows a structured multi-step approach focused on speaker-role awareness and domain-specific content filtering.

### 1. Data Preprocessing
- Dialogue turn separation (Therapist vs. Patient)
- Pronoun normalization (e.g., "I" → [Patient])
- Regex-based anonymization of sensitive details

### 2. Emotion & Keyword Tagging
- **Patients**: Emotion scoring using a mental health lexicon with rule-based thresholds (e.g., “hopeless” as high-risk)
- **Therapists**: Keyword detection and regex patterns (e.g., treatment advice, medication terms)

### 3. Summarization Model
- Transformer-based encoder-decoder model (T5, Pegasus)
- Attention mechanisms to focus on emotionally intense and clinically significant sentences
- Post-processing to add contextual phrases (e.g., “Patient expressed…”)

---

## 📊 Evaluation

We evaluate our summarization output using two standard metrics:

- **BLEU**: Measures n-gram overlap with ground truth
- **BERTScore**: Measures semantic similarity using contextual embeddings

### Baseline Results

| Model     | BLEU    | BERTScore |
|-----------|---------|-----------|
| T5-small  | 0.0184  | 0.3388    |
| T5-large  | 0.0029  | 0.5430    |
| Pegasus   | 0.0247  | 0.3015    |

---

## 🚀 Future Work

- Incorporating dialogue structure and turn-taking patterns
- Personalization based on patient profiles
- Exploring retrieval-augmented generation for long-term therapy session tracking

---

## 🤝 Acknowledgements

Thanks to the contributors of the MEMO and HOPE datasets, as well as the mental health professionals involved in annotation and guidance.

---

# Execution Instructions
1. Use the Test.ipynb file for testing the baseline
2. Install the necessary libraries and modules as instructed
3. Change the paths
4. Run the blocks 
