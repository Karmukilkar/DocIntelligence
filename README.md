# TenderIQ - Intelligent Document Processing Platform

<div align="center">

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)

An intelligent document processing and knowledge management platform for automated business intelligence extraction and analysis.

</div>

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [API Services](#api-services)
- [Database Schema](#database-schema)
- [Contributing](#contributing)
- [Support](#support)

---

## Overview

TenderIQ is an intelligent document processing platform designed to automate extraction of business intelligence from unstructured documents. Built with Streamlit for the frontend and FastAPI for backend services, it leverages advanced NLP techniques including OCR, embeddings, and semantic search to provide actionable insights.

The system processes various document types, extracts relevant information, and maintains a searchable knowledge base for rapid decision-making and automated analysis.

---

## ✨ Features

- **Document Processing**
  - Multi-format support (PDF, DOCX, JPG, PNG, TIFF)
  - Automatic OCR with multi-language support
  - Batch processing capabilities

- **Knowledge Management**
  - Vector database integration with semantic search
  - Intelligent document chunking and embedding
  - Real-time document indexing

- **Entity Profile Management**
  - Comprehensive entity information database
  - Financial data tracking
  - Certification and compliance management
  - Historical records and documentation
  - Capability and service profiles

- **Intelligent Retrieval**
  - Context-aware document retrieval
  - Eligibility assessment
  - Financial summary generation
  - Certification verification

- **Admin Interface**
  - User-friendly dashboard
  - Document management
  - Profile administration

---

## 🛠️ Tech Stack

### Backend
- **Framework**: FastAPI
- **Database**: SQLAlchemy with SQLite
- **Vector Store**: Chroma
- **NLP**: Embeddings with Hugging Face
- **OCR**: Tesseract

### Frontend
- **Framework**: Streamlit
- **File Processing**: PyPDF2, python-docx, Pillow
- **AI Integration**: OpenAI API compatibility

### Supporting Technologies
- Python 3.9+
- Docker (for containerization)
- Kubernetes (for orchestration)
- OpenTelemetry (for monitoring)

---

## 📋 Prerequisites

Before you begin, ensure you have:

- Python 3.9 or higher
- pip and virtualenv
- Tesseract OCR engine installed on your system
- Sufficient disk space for document storage and vector database
- Environment variables configured (see Configuration section)

### Optional Requirements
- Docker (for containerized deployment)
- Kubernetes (for production deployment)
- OpenAI API key (for advanced features)

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/tenderiq.git
cd tenderiq
```

### 2. Create Virtual Environment

```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Install System Dependencies

#### Tesseract OCR
- **Windows**: Download installer from [Tesseract GitHub](https://github.com/UB-Mannheim/tesseract/wiki)
- **macOS**: `brew install tesseract`
- **Linux**: `sudo apt-get install tesseract-ocr`

---

## ⚙️ Configuration

### Environment Setup

Create a `.env` file in the project root:

```bash
# API Configuration
OPENAI_API_KEY=<your-api-key>
OPENROUTER_API_KEY=<your-api-key>

# Database
DATABASE_PATH=./data/db/tenderiq.db

# Storage
DOCUMENTS_DIR=./data/documents
OCR_OUTPUT_DIR=./data/ocr_output
VECTORSTORE_DIR=./data/vectorstore

# Logging
LOG_LEVEL=INFO
LOG_FILE=./logs/tenderiq.log
```

### Configuration File

Edit `config.yaml` to customize:
- Application settings
- Database paths
- OCR configuration
- Embedding model parameters
- Logging levels
- Storage locations

**Note**: Never commit API keys or sensitive credentials to version control.

---

## 📖 Usage

### Start the Dashboard

```bash
streamlit run app.py
```

The application will be available at `http://localhost:8501`

### API Server

To run the FastAPI backend:

```bash
uvicorn api.routes:app --host 0.0.0.0 --port 8000
```

### Document Processing

1. Navigate to the admin UI
2. Upload documents (PDF, DOCX, images)
3. System automatically processes and indexes documents
4. Access information through the dashboard

### Batch Processing

For processing large document batches:

```python
from api.services.batch_process import process_batch
process_batch(documents_directory)
```

---

## 📁 Project Structure

```
tenderiq/
├── app.py                          # Main Streamlit application
├── config.yaml                     # Configuration file
├── requirements.txt                # Python dependencies
├── README.md                       # This file
│
├── api/
│   ├── models/
│   │   ├── database.py            # SQLAlchemy models
│   │   └── __init__.py
│   │
│   ├── routes/
│   │   ├── __init__.py
│   │   └── [route definitions]
│   │
│   └── services/
│       ├── batch_process.py       # Batch processing service
│       ├── data_entry.py          # Data entry service
│       ├── embedding_service.py   # Embedding generation
│       ├── ocr_service.py         # OCR processing
│       ├── retrieval_service.py   # Document retrieval
│       ├── update_service.py      # Data update service
│       └── __init__.py
│
├── admin_ui/                       # Admin dashboard components
│
├── data/
│   ├── db/                         # Database storage
│   ├── documents/                  # Document storage
│   ├── ocr_output/                 # Processed OCR text
│   └── vectorstore/                # Vector database (Chroma)
│
├── logs/                           # Application logs
│
└── backups/                        # Database backups
```

---

## 🔧 API Services

### Batch Process Service
Handles bulk document processing and indexing.

### Data Entry Service
Manages structured data input and validation.

### Embedding Service
Generates vector embeddings for semantic search.

### OCR Service
Processes images and scanned documents into searchable text.

### Retrieval Service
Executes intelligent document retrieval and context building.

### Update Service
Manages data updates and synchronization.

---

## 🗄️ Database Schema

The system uses SQLAlchemy ORM with the following main entities:

- **EntityProfile**: Core entity information and organizational data
- **FinancialData**: Financial records and performance metrics
- **Certification**: Compliance and certification records
- **ProjectHistory**: Historical project and engagement information
- **CapabilityProfile**: Capabilities and service offerings
- **DocumentMetadata**: Document tracking and audit information

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. Create a feature branch (`git checkout -b feature/AmazingFeature`)
2. Commit changes (`git commit -m 'Add AmazingFeature'`)
3. Push to the branch (`git push origin feature/AmazingFeature`)
4. Open a Pull Request

---

## 📞 Support

For issues, questions, or suggestions:

1. Check existing issues in the repository
2. Create a new issue with detailed description
3. Contact the development team

---

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## ⚠️ Security Notice

- **Never expose API keys** in code or configuration files
- Always use environment variables for sensitive information
- Regularly update dependencies for security patches
- Use `.gitignore` to prevent committing sensitive files
- Rotate credentials periodically

---

## 🔄 Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | 2026-02-17 | Initial release |

---

<div align="center">

**Built with ❤️ for intelligent document processing**

</div>
