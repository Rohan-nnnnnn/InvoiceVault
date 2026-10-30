INVOICEVAULT – SETUP GUIDE

Overview

This guide explains how to configure and run InvoiceVault locally using n8n, Ollama, Google Drive, and Google Sheets.

Prerequisites

Install or configure the following:

- n8n
- Ollama
- Qwen2.5-VL:7b vision model
- Google account with access to Google Drive and Google Sheets
- Google Drive credentials configured in n8n
- Google Sheets credentials configured in n8n

1. Configure Ollama

Install and start Ollama on your machine.

Download the required vision model:

ollama pull qwen2.5vl:7b

Verify that the model is available:

ollama list

Ensure Ollama is running and accessible from the environment where n8n executes.

If n8n runs inside Docker, configure the Ollama API URL so the n8n container can reach the host machine.

2. Configure Google Drive

Connect your Google Drive account to n8n using the Google Drive credentials.

Create the following folders in Google Drive:

- Unprocessed
- Processed
- Error

Use these folders for incoming invoice images and the workflow's output organization.

3. Configure Google Sheets

Create a Google Sheets spreadsheet to store extracted invoice information.

Add the required column headers corresponding to the fields extracted by your workflow.

Connect the spreadsheet to n8n using your Google Sheets credentials.

4. Configure the n8n Workflow

Import or open the InvoiceVault workflow in n8n.

Verify the following configurations:

- Google Drive search points to the Unprocessed folder.
- Supported file extensions are PNG, JPG, and JPEG.
- The Download File node retrieves the original invoice image.
- The HTTP Request node connects to the Ollama API.
- The correct Qwen2.5-VL:7b model is selected.
- Extracted invoice fields are mapped to the Google Sheets columns.
- Successful files are moved to Processed.
- Failed files are moved to Error.

5. Run the Workflow

1. Start Ollama.
2. Start n8n.
3. Verify that Google Drive and Google Sheets credentials are connected.
4. Place a supported invoice image in the Unprocessed folder.
5. Execute or activate the workflow.
6. Check Google Sheets for extracted invoice information.
7. Verify that the invoice image reaches the appropriate output folder.

Troubleshooting

Ollama Connection Error

- Confirm Ollama is running.
- Verify the API URL configured in n8n.
- If using Docker, ensure the container can access the host machine.

Invoice Extraction Failure

- Verify that the image is valid and readable.
- Confirm the Qwen2.5-VL:7b model is available.
- Check the HTTP Request node response.

Google Drive Error

- Verify Google Drive credentials.
- Confirm the selected folder and file IDs.
- Ensure the workflow is downloading an image file rather than attempting to export a Google Workspace document.

Google Sheets Error

- Verify Google Sheets credentials.
- Check the spreadsheet ID and sheet selection.
- Confirm that extracted fields match the spreadsheet columns.

Supported File Formats

- PNG
- JPG
- JPEG

PDF files are not supported by the current workflow.

Notes

- Ollama runs the vision model locally.
- Google Drive is used for invoice image storage and organization.
- Google Sheets stores extracted invoice information.
- Actual node settings and credential names may vary depending on the local n8n configuration.
