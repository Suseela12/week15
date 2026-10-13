# Experiment 15 : Multimodal Receipt Extraction

## Aim
To explore multimodal prompting using a vision-capable LLM to extract structured information from a restaurant receipt image and return the result as JSON.

## Problem Statement
Analyze a receipt image and extract the restaurant name, date, ordered items, subtotal, tax, and total. Validate whether subtotal plus tax equals the total.

## Technologies Used
- Python
- OpenAI GPT-4o Vision
- OpenAI API
- Base64 encoding
- JSON

## Algorithm
1. Install the required OpenAI package.
2. Configure the OpenAI API key.
3. Load the receipt image.
4. Encode the image in Base64.
5. Send the image and multimodal prompt to GPT-4o.
6. Extract the response and parse it as JSON.
7. Validate subtotal and tax against the total.
8. Save the extracted information to `output/receipt.json`.

## Installation

```bash
pip install -r requirements.txt
```

## API Key Setup

Windows Command Prompt:

```cmd
set OPENAI_API_KEY=your_api_key_here
```

Windows PowerShell:

```powershell
$env:OPENAI_API_KEY="your_api_key_here"
```

Never upload your API key to GitHub.

## Input
Place a restaurant receipt image named `receipt.jpg` inside the `src` folder.

Supported formats: JPG, JPEG, PNG, and WEBP.

## Execution

```bash
python src/main.py
```

## Output
The program prints the extracted receipt fields as JSON and saves them to `output/receipt.json`.

Example structure:

```json
{
  "restaurant_name": "The Golden Wok",
  "date": "2026-03-15",
  "items": [
    {"name": "Spring Rolls", "price": 5.99},
    {"name": "Kung Pao Chicken", "price": 14.99}
  ],
  "subtotal": 20.98,
  "tax": 1.68,
  "total": 22.66,
  "validation": {
    "subtotal_plus_tax_equals_total": true,
    "difference": 0.0
  }
}
```

The values above are illustrative. Actual output depends on the receipt image provided.

## Result
A multimodal extraction pipeline was implemented to analyze a receipt image, produce structured JSON, and check the arithmetic consistency of the extracted amounts.
