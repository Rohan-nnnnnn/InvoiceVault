INVOICEVAULT – TEST RESULTS

Overview

This document describes the test scenarios used to evaluate InvoiceVault's invoice processing workflow, AI extraction, Google Sheets integration, and Google Drive file organization.

Test Environment

- Workflow Automation: n8n
- AI Runtime: Ollama
- Vision Model: Qwen2.5-VL:7b
- File Storage: Google Drive
- Data Storage: Google Sheets
- Supported Formats: PNG, JPG, JPEG

Test Cases

1. Valid Invoice Image

Input: A valid PNG, JPG, or JPEG invoice image uploaded to the Unprocessed folder.

Expected Result:
- The workflow identifies the invoice image.
- The image is downloaded successfully.
- Ollama analyzes the invoice.
- Structured invoice information is extracted.
- Extracted information is recorded in Google Sheets.
- The image is moved to the Processed folder.

Status: To be verified.

2. Invoice Data Extraction

Input: An invoice image containing readable invoice details.

Expected Result:
- The AI model identifies available invoice information.
- Extracted values are mapped to the expected fields.
- Expense information is categorized appropriately.
- The structured output is passed to Google Sheets.

Status: To be verified.

3. Unsupported File Format

Input: A file with an unsupported extension, such as PDF.

Expected Result:
- The file is rejected by the format validation step.
- The unsupported file is not sent for image extraction.
- The workflow follows its configured error-handling path.

Status: To be verified.

4. AI Processing Failure

Input: An invoice image that cannot be processed successfully by the AI extraction stage.

Expected Result:
- The workflow handles the extraction failure.
- The failed invoice is routed to the Error folder.
- No successful processing result is recorded for the failed extraction.

Status: To be verified.

5. Google Sheets Integration

Input: Successfully extracted invoice information.

Expected Result:
- The extracted values are mapped to the correct spreadsheet columns.
- A new invoice record is added to Google Sheets.
- The stored information is available for expense tracking.

Status: To be verified.

Test Summary

The test scenarios cover file validation, invoice image processing, AI extraction, structured data storage, and error handling.

Final test statuses should be updated to Passed or Failed after verifying each scenario in the actual n8n workflow.
