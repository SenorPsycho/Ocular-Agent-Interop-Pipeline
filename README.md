EyeAgent-Sync: Agentic Orchestration for Standardized Ophthalmic Reporting

📌 Overview
EyeAgent-Sync is a multi-agent AI pipeline designed to bridge the "Interoperability Gap" in digital ophthalmology. While traditional AI models focus solely on diagnosis, this project introduces an Agentic Layer that automates the collection, validation, and standardization of clinical findings into hospital-ready formats (HL7 FHIR).

In developed healthcare systems like South Korea, the lack of standardization between different imaging hardware (Topcon, Zeiss, etc.) is a major bottleneck. EyeAgent-Sync solves this by orchestrating specialized AI agents to ensure every scan results in a uniform, actionable medical record.

🏗️ System Architecture
The system follows a Three-Agent Orchestration logic:

Agent A (The Vision Specialist): A Deep Learning model (U-Net/ViT) that extracts quantitative features (Optic Disc ratio, Lesion counts) from raw Fundus images.

Agent B (The Knowledge Harmonizer): An LLM-based agent that maps vision findings to international standards (LOINC, SNOMED-CT, and ICD-10).

Agent C (The Clinical Auditor): A logic-check agent that validates the report against medical constraints (e.g., "If CDR > 0.7, flag for Glaucoma review").

🛠️ Technical Stack
Imaging: PyTorch, MONAI (Medical Open Network for AI), OpenCV.

Orchestration: LangChain / LangGraph.

Informatics: HL7 FHIR R4, Python-FHIR-Parser.

Database: Pinecone (Vector storage for clinical embeddings).

Models: * Vision: EfficientNet-B3 (Transfer Learning).

Cognitive: Gemini-1.5-Flash / Llama-3.

📊 Dataset & Methodology
This project utilizes the IDRiD (Indian Diabetic Retinopathy Image Dataset):

Segmentation: Pixel-level annotations for Optic Disc and retinal lesions.

Grading: Disease severity levels (0-4) for clinical validation.

Preprocessing Pipeline:

CLAHE: Contrast Limited Adaptive Histogram Equalization for enhanced vessel visibility.

Circular Cropping: Automated ROI (Region of Interest) extraction centered on the Optic Disc.

🚀 Getting Started
1. Installation
Bash
git clone https://github.com/SenorPsycho/EyeAgent-Sync.git
cd EyeAgent-Sync
pip install -r requirements.txt
2. Run a Standardized Scan
Python
# Coming soon: A single command to process an image and generate a FHIR JSON report
python run_pipeline.py --image data/sample_retina.jpg --output report.json

🎯 Research Goals (M.S. Roadmap)
This project serves as a foundational prototype for my Master's research, focusing on:

Oculomics: Linking retinal biomarkers to systemic cardiovascular health.

Federated Learning: Training across distributed hospital nodes without compromising patient privacy.

Explainable AI (XAI): Generating saliency maps to build clinician trust.
