# ⚖️ Optimizing Legal Document Summarization for Enhanced Accessibility in Judicial System

This project presents a complete NLP pipeline to transform complex Indian legal judgments into layperson-friendly summaries. It integrates OCR, rhetorical segmentation, transformer-based summarization (LED), and prompt-based structuring (Meta-LLaMA 8B-Instruct), aiming to bridge the gap between public access and public understanding of court documents.

---

## 🔍 Problem Statement

While Indian court judgments are publicly available through platforms like eCourts, their structure and dense legal language make them difficult for the general public to comprehend. There is a clear gap between accessibility and readability, especially for non-legal professionals such as students, journalists, and civil society researchers.

---

## 🎯 Project Objectives

- Extract text from scanned/digital Indian court judgments using OCR tools.
- Segment legal content into rhetorical sections: Metadata, Facts, Arguments, Decisions.
- Generate high-quality abstractive summaries using the LED model.
- Restructure outputs using Meta-LLaMA into 6 clearly labeled sections:
  - Background of the Case  
  - Key Legal Issues  
  - Arguments from Both Sides  
  - Court’s Decision & Reasoning  
  - Impact & Lessons for the Public  
  - Important Takeaways in Simple Terms
- Evaluate summaries using ROUGE, BLEU, and BERTScore.
- Deploy the tool via a Streamlit interface for real-time use.

---

## 📦 Dataset

- **Source:** Indian eCourts portal (public domain)
- **Size:** ~1,649 PDF judgments (1GB total)
- **Categories:**  
  - Civil (849): land disputes, contracts, defamation, divorce, etc.  
  - Criminal (800): murder, kidnapping, money laundering, etc.  
- **Split:**  
  - Train: 70%  
  - Validation: 15%  
  - Test: 15%  

---

## ⚙️ Tech Stack

| Component         | Tools & Libraries                             |
|------------------|------------------------------------------------|
| Text Extraction   | PyMuPDF, Tesseract OCR                        |
| Preprocessing     | spaCy, NLTK, Regex                            |
| Summarization     | LED (Longformer Encoder-Decoder, HuggingFace) |
| Structuring       | Meta-LLaMA 8B-Instruct                        |
| Evaluation        | ROUGE, BLEU, BERTScore                        |
| Interface         | Streamlit                                     |
| Deployment        | Ngrok (via Google Colab)                      |
| Programming       | Python                                        |

---

## 🧠 Methodology

The project follows a **hybrid CRISP-DM methodology**:

1. **Business Understanding**  
   Bridge the gap between public legal data and non-expert comprehension.

2. **Data Collection & Preparation**  
   - 1,649 court judgments collected from eCourts.  
   - Extracted using PyMuPDF and fallback Tesseract OCR.  
   - Cleaned using regex and NLP libraries.  
   - Segmented into rhetorical structures.

3. **Modeling**  
   - LED (AllenAI) used for abstractive summarization.  
   - Meta-LLaMA 8B-Instruct used for structured generation via custom prompts.

4. **Evaluation**  
   - Evaluated with ROUGE-1, ROUGE-2, ROUGE-L, BLEU, and BERTScore across 16 test samples.  
   - Manual reference summaries used for comparison.

5. **Deployment**  
   - Interface created using Streamlit.  
   - Publicly accessible via Ngrok tunnel in Colab.

---

## 📊 Evaluation Results

| Metric      | Score  |
|-------------|--------|
| ROUGE-L     | 0.32   |
| BLEU        | 0.105  |
| BERTScore   | 0.81   |

These metrics validate that the model-generated summaries maintain semantic and contextual accuracy comparable to human-written summaries.


## 🔮 Future Enhancements
To improve scalability, accessibility, and real-world applicability, the following future enhancements are planned:

🧠 Automated Rhetorical Segmentation
Train a dedicated RSR (Rhetorical Structure Recognition) model using annotated Indian court data to replace heuristic-based segmentation with a data-driven approach.

🌐 Multilingual Support
Integrate models like IndicBERT or mBART to handle regional languages (Hindi, Tamil, Kannada, etc.), enabling broader accessibility across India.

⚡ Latency Optimization
Optimize inference time for LED and LLaMA models to support real-time use cases such as courtroom displays, judicial kiosks, and on-the-fly legal consultations.

🖱️ Interactive User Interface
Enhance the Streamlit frontend with section-wise navigation, legal term highlighting, and integrated chatbot support for querying case-specific content.

📄 Document Type Expansion
Extend coverage beyond judgments to include contracts, regulatory filings, arbitration awards, and corporate compliance documents.

🧾 Adaptive Prompting
Tailor prompt instructions dynamically based on the case type (e.g., criminal, civil, family law) to improve contextual formatting and tone of summaries.

🔍 Explainability Integration
Implement attention visualization and rationale tracing to make the model’s decisions transparent and trustworthy for legal professionals.

📱 Offline & Mobile Access
Develop lightweight, mobile-compatible deployments for resource-constrained environments, legal clinics, and rural legal aid centers.

🗳️ Feedback-Driven Fine-Tuning
Enable continuous improvement via user feedback loops, especially from legal practitioners and NGOs working in the justice domain.


