# 🔒 RE-DACT System

> **An AI-powered security toolkit for automated PII redaction, featuring encrypted auditing and password-protected, reversible steganography.**

[![Team](https://img.shields.io/badge/Team-ByteCoderz-orange)]()
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

---

## 📺 Project Resources & Demo

**Access the full project presentation and live demonstration video below:**

| 🎥 **Demo Video** | 📑 **Project Presentation** | 💻 **Source Code** |
| :---: | :---: | :---: |
| [**Watch Live Demo**](https://drive.google.com/file/d/1JhgKCBJ5aVPmZ2JA2PfgSEnY18qIh9ZA/view?usp=sharing) | [**View PPT**](https://docs.google.com/presentation/d/1jigGS7taB5cFwlPbrgPa1mrdMILgraN2/edit?usp=sharing&ouid=106052378843726309121&rtpof=true&sd=true) | [**GitHub Repo**](https://github.com/Sujanraj0306/Redact_System_vit_ByteCoderz.git) |

---

### 📸 Demo Preview
*Below is a sample output of the redaction system:*

![Demo Image](https://drive.google.com/uc?export=view&id=1C4TXMmE1eS7VoHVeQ7fPNUiNQk0WOfci)

> 📄 **[Click here to view the Full Demo Document](https://drive.google.com/file/d/1jWPL9cSK1HR2JjImZGIdhnUSRL6YaCtk/view?usp=sharing)**

---
## 📖 Overview

**RE-DACT** is a comprehensive solution designed to address privacy concerns in the age of big data. Sensitive PII (like Aadhaar numbers) is frequently exposed in documents, but standard redaction (black boxes) permanently destroys this data.

**The Solution:** We built an AI tool that automatically detects and masks sensitive information in **Images, Videos, and Audio**, offering a unique feature of **reversible encryption**. This allows authorized users (like auditors) to recover the original data using a password, while keeping it secure from everyone else.

### 🚀 Key Features

* **🔍 Multi-Modal AI Detection:** Intelligently finds faces, text (Names, IDs), and QR codes using `EasyOCR` and `spacy`.
* **🔐 Reversible Redaction:** Unlike standard blurring, our system securely encrypts the redacted region. The original data can be restored with a secret password.
* **🛡️ Encrypted Auditing:** Maintains a tamper-proof `audit_log.json` of all redaction activities for compliance.
* **🎙️ Audio Sanitization:** Utilizes OpenAI's `Whisper` model to detect and beep out sensitive speech.
* **👤 Main Character Identification:** specific identification capabilities (e.g., identifying VIPs in footage).

---

## 🛠️ Tech Stack

* **Frameworks:** PyTorch, Torchvision, Gradio (UI)
* **OCR & Text Analysis:** EasyOCR, Pytesseract, spaCy (`en_core_web_md`)
* **Audio Processing:** OpenAI Whisper, Librosa
* **Computer Vision:** OpenCV, NumPy
* **Document Handling:** PyMuPDF
* **Video Processing:** MoviePy

---

## 🏗️ System Architecture & Workflow

The RE-DACT pipeline follows a secure "Detect-Redact-Encrypt" workflow:

1.  **Ingestion:** The system accepts `.jpg`, `.mp4`, or `.wav` files via the Gradio Interface.
2.  **AI Detection:**
    * **Vision:** YOLO/OpenCV detects faces; EasyOCR extracts text.
    * **Audio:** Whisper transcribes and identifies sensitive keywords.
3.  **Redaction:**
    * Identified Regions of Interest (ROI) are blurred or masked.
4.  **Audit & Encryption:**
    * The original data from the redacted region is hashed and encrypted.
    * An `audit_log.json` is generated containing timestamps, PII types, and encryption tokens (e.g., `gAAAA...`).
5.  **Output:** A sanitized file is produced. This file can be fed back into the system with a password to **reverse** the redaction.

---

## 🌍 Social Impact (SDGs)

This project aligns with the United Nations Sustainable Development Goals:
* **SDG 16 (Peace, Justice & Strong Institutions):** Protects the fundamental right to privacy.
* **SDG 9 (Industry, Innovation & Infrastructure):** Strengthens digital infrastructure against data breaches.
* **SDG 8 (Decent Work & Economic Growth):** Reduces risks of financial fraud and identity theft.

---

## ⚙️ Installation & Setup

**1. Clone the Repository**
```bash
git clone [https://github.com/Sujanraj0306/Redact_System_vit_ByteCoderz.git](https://github.com/Sujanraj0306/Redact_System_vit_ByteCoderz.git)
cd Redact_System_vit_ByteCoderz
