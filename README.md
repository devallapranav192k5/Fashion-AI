# ⚡ Fashion-AI

### AI-Powered Virtual Try-On • Computer Vision • Analytics Engine

> An end-to-end AI pipeline combining computer vision preprocessing, deep-learning data preparation, virtual try-on assets, and a RESTful analytics backend for intelligent fashion e-commerce.

---

<p align="center">

  <img src="https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/PyTorch-Deep%20Learning-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-REST%20API-009688?style=for-the-badge&logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/Computer%20Vision-AI-8A2BE2?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Phase%202%20Complete-00C853?style=for-the-badge" />

</p>

---

## 🚀 Overview

**Fashion-AI** is a modular computer-vision and analytics platform designed for AI-powered fashion and virtual try-on applications.

The system transforms raw fashion imagery into AI-ready assets through an automated preprocessing pipeline, while simultaneously providing a RESTful analytics layer for tracking virtual try-on engagement and downstream conversion behavior.

Built as part of an internship project at **Raritone Private Limited**, the project focuses on bridging the gap between:

**Raw Fashion Data → AI Processing → Virtual Try-On → Behavioral Analytics**

---

## 🧠 System Architecture

```text
                         FASHION-AI PIPELINE
                                │
                                ▼
                    ┌─────────────────────┐
                    │    Raw Fashion Data │
                    │       (.jpg)        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Computer Vision     │
                    │ Segmentation        │
                    │                     │
                    │ Background Removal  │
                    │ U²-Net / rembg      │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Processed Assets    │
                    │                     │
                    │ Transparent /       │
                    │ Segmented Images    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Dataset Preparation │
                    │                     │
                    │ Resize              │
                    │ Tensor Conversion   │
                    │ Normalization       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ AI / Model-Ready    │
                    │ Data                │
                    └─────────────────────┘


                               +
                               │
                               ▼

                    ┌─────────────────────┐
                    │  Analytics Engine   │
                    │      FastAPI        │
                    └──────────┬──────────┘
                               │
              ┌────────────────┼────────────────┐
              ▼                ▼                ▼
        Try-On Events     Conversions      Dashboard


✨ Core Capabilities
👕 Computer Vision Pipeline

Automated processing of fashion/product imagery for downstream AI applications.

Background removal
Subject extraction
Image segmentation
Dataset preprocessing
Tensor conversion
Image resizing and normalization
🧠 Deep Learning Preparation

Fashion imagery is transformed into standardized, model-ready representations using PyTorch and Torchvision.

The preprocessing pipeline is designed to make downstream virtual try-on and computer-vision models easier to integrate.

⚡ Analytics API

A lightweight FastAPI backend provides REST endpoints for tracking virtual try-on behavior and conversion metrics.

Current analytics functionality includes:

Virtual try-on event tracking
Product conversion tracking
Aggregated engagement metrics
Conversion-rate calculation
Interactive Swagger API documentation
🧪 Automated Testing

The project includes an integration-testing layer for validating the analytics API and ensuring that core endpoints behave as expected.

🛠️ Tech Stack
Layer	Technology
Language	Python 3.10+
Deep Learning	PyTorch
Computer Vision	rembg / U²-Net
Image Processing	Pillow
Data Processing	Torchvision
Backend	FastAPI
ASGI Server	Uvicorn
API Testing	Requests
Documentation	Swagger / OpenAPI
Version Control	Git + GitHub
📂 Project Structure
Fashion-AI/
│
├── phase2_virtual_tryon/
│   │
│   ├── raw_data/
│   │   └── tee_01.jpg
│   │
│   ├── processed_data/
│   │   └── tee_01_seg.png
│   │
│   ├── ground_truth/
│   │
│   ├── model_ready_data/
│   │
│   ├── analytics_api.py
│   ├── dataset_prep.py
│   ├── segmentation.py
│   ├── test_analytics.py
│   │
│   ├── testing_report.txt
│   ├── DEPLOYMENT_NOTES.md
│   ├── README_Member3_5.md
│   └── PPT_Slide.txt
│
├── requirements.txt
└── .gitignore
⚙️ Getting Started
1. Clone the Repository
git clone https://github.com/devallapranav192k5/Fashion-AI.git
cd Fashion-AI
2. Create a Virtual Environment
Windows
python -m venv venv

Activate it:

.\venv\Scripts\Activate.ps1
macOS / Linux
python3 -m venv venv
source venv/bin/activate
3. Install Dependencies
pip install -r requirements.txt
🔬 Running the Pipeline

Move into the Phase 2 project directory:

cd phase2_virtual_tryon
Step 1 — Image Segmentation

Run:

python segmentation.py

This processes the raw fashion imagery and generates segmented/background-removed assets.

Example:

raw_data/
    tee_01.jpg

        ↓

segmentation.py

        ↓

processed_data/
    tee_01_seg.png
Step 2 — Dataset Preparation

Run:

python dataset_prep.py

This prepares processed images for downstream deep-learning workflows through resizing, tensor conversion, and normalization.

⚡ Launch the Analytics API

From:

phase2_virtual_tryon/

run:

python analytics_api.py

The API will start locally at:

http://127.0.0.1:8000
📖 Interactive API Documentation

Once the server is running, open:

http://127.0.0.1:8000/docs

FastAPI automatically provides an interactive Swagger UI where endpoints can be explored and tested.

📊 API Endpoints
Endpoint	Method	Purpose
/api/v1/analytics/try-on	POST	Record virtual try-on events
/api/v1/analytics/conversion	POST	Track downstream purchases
/api/v1/analytics/dashboard	GET	Retrieve aggregated analytics
🧪 Testing

With the API running in one terminal, open another terminal and activate the virtual environment.

Navigate to:

phase2_virtual_tryon/

Then run:

python test_analytics.py

The integration suite validates the analytics workflow and API responses.

📈 Analytics Flow
User
 │
 ▼
Virtual Try-On
 │
 ▼
POST /analytics/try-on
 │
 ▼
Engagement Recorded
 │
 ▼
Product Interaction
 │
 ▼
POST /analytics/conversion
 │
 ▼
Conversion Recorded
 │
 ▼
GET /analytics/dashboard
 │
 ▼
┌─────────────────────────────┐
│ Total Try-Ons               │
│ Total Conversions           │
│ Conversion Rate             │
│ Engagement Metrics          │
└─────────────────────────────┘
🎯 Project Goals

Fashion-AI is designed around four core objectives:

01 — Automate

Reduce manual effort involved in preparing fashion imagery for AI systems.

02 — Standardize

Convert inconsistent visual inputs into structured, model-ready representations.

03 — Integrate

Provide a clean backend interface for connecting virtual try-on systems with application infrastructure.

04 — Measure

Capture behavioral signals that help understand how users interact with virtual try-on experiences.

🔮 Future Roadmap

The architecture is designed to support future expansion into:

 Full-body virtual try-on inference
 Garment-person image synthesis
 Real-time try-on generation
 GPU-accelerated inference
 Cloud deployment
 Persistent analytics database
 Authentication and user management
 Advanced conversion analytics
 E-commerce platform integration
 Production monitoring
🏗️ Development Philosophy

The project follows a modular pipeline architecture:

DATA
 ↓
PROCESSING
 ↓
MODEL PREPARATION
 ↓
INFERENCE
 ↓
API
 ↓
ANALYTICS

Each layer is independently replaceable, allowing future virtual try-on models or analytics infrastructure to be integrated without redesigning the entire system.

---

## 👨‍💻 Project

**Fashion-AI**

Developed during internship operations at:

**Raritone Private Limited**

Repository:

:contentReference[oaicite:0]{index=0}

<p align="center">

### ⚡ From Fashion Data to AI-Powered Experiences.

**Built with Python • PyTorch • FastAPI • Computer Vision**

</p>---

## 👨‍💻 Project

**Fashion-AI**

Developed during internship operations at:

**Raritone Private Limited**

Repository:

:contentReference[oaicite:0]{index=0}

<p align="center">

### ⚡ From Fashion Data to AI-Powered Experiences.

**Built with Python • PyTorch • FastAPI • Computer Vision**

</p>
