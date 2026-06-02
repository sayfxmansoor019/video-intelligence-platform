# 🎥 Video Intelligence Platform

## Problem Statement

Organizations generate large volumes of recorded meetings, interviews, customer interactions, and training sessions. While transcripts capture spoken content, they often fail to provide insight into participant emotions, delivery style, confidence, engagement, and conversational dynamics.

This project addresses that challenge by combining speech recognition, emotion analysis, delivery assessment, reaction annotation, and summarization into a unified video intelligence pipeline that transforms raw recordings into actionable conversational insights.


## 📌 Overview
This project is a Video Intelligence system that processes recorded video calls and produces:
- Timestamped speech transcription
- Emotion analysis from audio
- Delivery nuance analysis (tone, pace, confidence)
- Reaction annotations per transcript segment
- A concise conversation summary

The system is built using Python, Streamlit, and pretrained speech models, and is designed to demonstrate multimodal AI processing of video data.

---

## 🏗️ System Architecture

Video Upload
->
Audio Extraction (MoviePy)
->
Speech Transcription (SpeechBrain ASR)
->
Emotion Analysis (Wav2Vec2 Emotion Model)
->
Delivery Nuance Analysis
->
Reaction Annotation (Text-based)
->
LLM-based Summarization
->
Final JSON Output + Streamlit UI


---

## 🧩 Components Breakdown

### 1. Transcription Module
- Converts extracted audio into timestamped text segments
- Uses pretrained SpeechBrain ASR models

### 2. Emotion Annotation
- Detects emotions from speech audio
- Outputs probability-based emotion labels

### 3. Delivery Nuances
- Analyzes speech pace, pauses, and tone
- Helps understand how something was said, not just what

### 4. Reaction Annotation
- Assigns conversational reactions per transcript segment
- Examples: agreement, hesitation, confidence, uncertainty

### 5. Summarization
- Generates a concise summary of the conversation
- Based on the full transcript text

---

## 🖥️ Tech Stack

- **Python 3.10**
- **Streamlit** – Web UI
- **SpeechBrain** – ASR & Emotion Recognition
- **MoviePy** – Audio extraction from video
- **PyTorch** – Model inference
- **Altair / Pandas** – Data handling

---

## ⚙️ Setup Instructions

### 1. Clone or Download Repository
```bash
git clone <repository-url>
cd video-transcription-metadata-annotation


2. Create Virtual Environment
python -m venv venv
source venv/bin/activate  # macOS/Linux

3. Install Dependencies
pip install -r requirements.txt

4. Run the Application
streamlit run app.py

🚀 Usage Guidelines

Launch the Streamlit app

Upload a video file (.mp4, .mov, .avi)

The system will:

Extract audio

Generate timestamped transcript

Annotate emotions, delivery, and reactions

Produce a summary

Final output is saved as:
outputs/final_output.json


Project Structure:

├── app.py
├── scripts/
│   ├── transcribe_video.py
│   ├── annotate_emotions.py
│   ├── delivery_nuances.py
│   ├── reaction_annotations.py
│   └── summarize_with_llm.py
├── outputs/
├── inputs/
├── README.md
├── .gitignore

Example Output

Timestamped transcript with annotations

Emotion and delivery metadata

Reaction labels

Conversation summary

Structured JSON output
