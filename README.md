# InvoiceVault – AI-Powered Invoice Processing System

InvoiceVault is an AI-powered invoice processing and expense management automation system built using **n8n, Ollama (Qwen2.5-VL), Google Drive, and Google Sheets**.

It automatically extracts structured information from invoice images, categorizes expenses, and maintains organized records in Google Sheets. It also separates successfully processed invoices from failed ones using dedicated Google Drive folders.

## Features

- **AI-Powered Data Extraction:** Uses Ollama Qwen2.5-VL to extract structured information from invoice images.
- **Automated Expense Categorization:** Identifies expense categories such as food and miscellaneous.
- **Google Sheets Integration:** Stores extracted invoice information in a structured spreadsheet.
- **Google Drive Integration:** Retrieves invoice images from the Unprocessed folder.
- **File Organization:** Moves successfully processed invoices to the Processed folder and unsuccessful ones to the Error folder.
- **Automated Workflow:** Handles invoice processing with n8n, reducing manual data entry.

## Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation |
| Ollama | Local AI model execution |
| Qwen2.5-VL:7b | Invoice image understanding and data extraction |
| Google Drive | Invoice storage and organization |
| Google Sheets | Extracted invoice data storage |

## Workflow

1. An invoice image is placed in the Google Drive Unprocessed folder.
2. The workflow searches for available files.
3. It checks the supported file extension.
4. The invoice image is downloaded.
5. The image is sent to Ollama for AI-powered data extraction.
6. Extracted invoice information is structured into fields.
7. Expense details are recorded in Google Sheets.
8. Successfully processed files are moved to the Processed folder.
9. Failed files are moved to the Error folder.

## Supported File Formats

- PNG
- JPG
- JPEG

**Note:** PDF files are not supported by the current workflow.

## Setup Requirements

Before running InvoiceVault, ensure you have:

- n8n installed and running.
- Ollama installed and running.
- Qwen2.5-VL:7b model available in Ollama.
- Google Drive credentials configured in n8n.
- Google Sheets credentials configured in n8n.
- Required Google Drive folders created:
  - Unprocessed
  - Processed
  - Error
- A Google Sheets spreadsheet configured to store extracted invoice information.

## How to Use

1. Start n8n and Ollama.
2. Ensure the required Google Drive and Google Sheets credentials are connected.
3. Place a supported invoice image in the Unprocessed folder.
4. Execute or activate the workflow.
5. Check Google Sheets for the extracted invoice information.
6. Verify the file has been moved to the appropriate output folder.

## Project Objective

The objective of InvoiceVault is to demonstrate how AI-powered document understanding and workflow automation can reduce repetitive data entry, organize business expense records, and streamline invoice processing.

## Author

**Rohan Narlawar**

- GitHub: [Rohan-nnnnnn](https://github.com/Rohan-nnnnnn)
- LinkedIn: [linkedin.com/in/rohan-narlawar-149291354](https://www.linkedin.com/in/rohan-narlawar-149291354)
- Email: [rohannarlawar31@gmail.com](mailto:rohannarlawar31@gmail.com)
