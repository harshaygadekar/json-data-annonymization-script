
# JSON data annonymization script 

This Python script is designed to anonymize sensitive information in JSON-formatted medical records. 

It replaces personally identifiable information (PII) with realistic fake data while maintaining the structure and consistency of the original dataset. 

The script uses named entity recognition (NER) for text fields and provides consistent anonymization across related fields.



## Licenses

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)

## This script is particularly suitable for:

- Medical records in JSON format
- Datasets containing personal information such as names, addresses, dates of birth, and medical details
- Records with nested structures and text fields containing sensitive information


## Features
1. **PII Field Anonymization**: Replaces specific fields like names, addresses, and contact information with realistic fake data.
2. **Text Anonymization**: Uses SpaCy's NER to identify and replace entities in text fields.
3. **Consistent Date Anonymization**: Maintains relative time relationships between date fields.
4. **Nested Structure Support**: Capable of anonymizing data in complex, nested JSON structures.
5. **Error Handling and Logging**: Implements try-except blocks and logging for robust error management.
6. **Customizable Field Mapping**: Allows easy addition or modification of fields to be anonymized.

## Script Running Process
1. **Initialization**:
   - Import required libraries (json, copy, Faker, spaCy)
   - Set up logging
   - Load SpaCy's English language model

2. **Data Preparation**:
   - Define the JSON data structure to be anonymized
   - Specify PII fields and text fields requiring anonymization

3. **Anonymization Functions**:
   - `anonymize_field()`: Replaces specific PII fields
   - `anonymize_text()`: Uses NER to anonymize text content
   - `anonymize_date()`: Ensures consistent date anonymization
   - `traverse_and_anonymize()`: Recursively processes the JSON structure

4. **Main Execution**:
   - Create a deep copy of the original data
   - Apply the anonymization process
   - Handle potential errors and log issues

5. **Output**:
   - Print the anonymized JSON data

## Installation

Install my-project with git clone command

Install necessary libraries:

```bash
  pip install faker spacy
```
Download the SpaCy English language model 
```bash
python -m spacy download en_core_web_sm
```
Modify the `data_json` variable with your JSON data or import it from a file.

Run the script

## Customization
- Modify the `PII_FIELDS` dictionary to include additional fields for anonymization
- Adjust the `TEXT_FIELDS` list to specify which nested fields should undergo text anonymization
- Customize the `anonymize_field()` function to handle specific data types in your dataset

## Note:
- The script maintains consistency by using mapping dictionaries to ensure the same original value is always replaced with the same fake value
- Error handling is implemented to gracefully handle unexpected data structures or values
- Logging is used to track any issues during the anonymization process




