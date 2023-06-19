# **AI driven Invoice Processing System**

**Problem Statement:**
The problem is to extract relevant information from an invoice document and validate the extracted invoice number against a sample invoice database.

**Approach:**
To solve the problem, the following approach is taken:

1. **Optical Character Recognition (OCR):** The pytesseract library is used to perform OCR on the invoice document. OCR converts the scanned or image-based text into machine-readable text. This step is crucial as it enables us to extract the required information from the invoice document.

2. **Extracting Invoice Information using Regex:** After performing OCR and obtaining the extracted text from the invoice document, regular expressions (regex) are used to search for specific patterns and extract relevant information. The following information is extracted from the text:
   - Invoice Number: A regex pattern is used to search for the invoice number in the text.
   - Invoice Date: Another regex pattern is used to search for the invoice date in the text.
   - Amount Due: A regex pattern is used to search for the amount due in the text.

   If the extracted information matches the expected patterns, it is returned. Otherwise, appropriate error messages are provided.

3. **Validation of Invoice Number:**
   - The extracted invoice number is validated using the `validate_invoice_number()` function.
   - The function checks for the following conditions:
     - If no invoice number is provided, it returns a message asking the user to enter an invoice number.
     - The invoice number is checked against a regex pattern to ensure it is in a valid format (alphanumeric characters only).
     - The invoice number is checked against a sample invoice database to verify its uniqueness.
     - If the invoice number passes all the validation checks, a success message is returned. Otherwise, relevant error messages are provided.

**Reasoning for the Approach:**
The chosen approach combines OCR with regex pattern matching to solve the problem. Here's the reasoning behind each step:

1. **OCR:** Optical Character Recognition (OCR) is used because invoices are often in the form of scanned documents or images. By performing OCR, we can convert the image-based text into machine-readable text, enabling us to extract the required information.

2. **Regex Pattern Matching:** Regular expressions (regex) are employed to search for specific patterns in the extracted text. Invoices usually have structured formats with consistent patterns for invoice numbers, dates, and amounts due. Regex provides a flexible and powerful way to search for and extract these patterns from the text.

3. **Validation Checks:** The validation of the extracted invoice number is necessary to ensure data integrity and prevent duplication. By checking the format and uniqueness of the invoice number against a sample invoice database, we can validate its authenticity and avoid potential errors.

**Conclusion:**
The approach presented combines OCR, regex pattern matching, and validation checks to extract and validate invoice information. OCR is used to convert image-based text into machine-readable text, regex is utilized to extract specific patterns, and validation checks are performed to ensure the accuracy and uniqueness of the extracted invoice number. By employing this approach, we can effectively extract relevant invoice information and validate it against a given sample invoice database.
