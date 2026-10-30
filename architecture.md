INVOICEVAULT – SYSTEM ARCHITECTURE

Overview

InvoiceVault is an automated invoice processing system that uses n8n to coordinate file handling, AI-powered data extraction, and expense record storage.

The system integrates Google Drive for invoice management, Ollama with Qwen2.5-VL:7b for image understanding, and Google Sheets for storing extracted invoice information.

System Components

1. Google Drive – Input Storage

Stores incoming invoice images in the Unprocessed folder. Supported formats are PNG, JPG, and JPEG.

2. n8n – Workflow Orchestration

Controls the complete processing pipeline, including file discovery, format validation, downloading, AI extraction, spreadsheet updates, and file organization.

3. Ollama – AI Processing

Runs the Qwen2.5-VL:7b vision model locally to analyze invoice images and extract structured invoice information.

4. Google Sheets – Data Storage

Stores extracted invoice details in a structured spreadsheet for expense tracking and record management.

5. Google Drive – Output Storage

Organizes files based on processing results:
- Processed: Successfully processed invoice images.
- Error: Invoice images that could not be processed successfully.

Processing Flow

1. Invoice images are uploaded to the Google Drive Unprocessed folder.
2. n8n searches for available invoice files.
3. The workflow checks whether each file has a supported image extension.
4. The Download File node retrieves the original image.
5. n8n sends the image to the local Ollama API.
6. Qwen2.5-VL:7b analyzes the image and extracts invoice information.
7. The extracted information is structured into predefined fields.
8. n8n records the extracted information in Google Sheets.
9. The file is moved to the Processed folder after successful processing.
10. Files that encounter processing failures are moved to the Error folder.

Data Flow

Google Drive (Unprocessed)
→ n8n File Processing
→ Ollama Vision Model
→ Structured Invoice Data
→ Google Sheets
→ Google Drive (Processed / Error)

Technology Stack

- Workflow Automation: n8n
- AI Runtime: Ollama
- Vision Model: Qwen2.5-VL:7b
- File Storage: Google Drive
- Structured Data Storage: Google Sheets
- Supported Input: PNG, JPG, JPEG

Architecture Objective

The architecture separates file storage, AI-based extraction, workflow orchestration, and structured data storage. This makes invoice processing easier to manage while reducing repetitive manual data entry.
