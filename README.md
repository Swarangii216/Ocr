<<<<<<< HEAD
# ScanPlus

## What is ScanPlus?
A system that can convert doctor's handwritten prescriptions into machine-readable text and classify the medicines along with their doses. It will also send an alert to the patient's registered email address containing all the relevant prescription details.

Key features:
* AWS Textract: Extracts text from doctor's handwritten prescriptions.
* NER Model: Classifies the extracted text into relevant categories.
* Alert System: Sends an email alert containing all the prescription details (medicines, doses, and category) to the patient's registered email address.

## Approach
**For more in depth information, [refer this article](https://aryaman.space/from-scribbles-to-structured-data-processing-handwritten-prescriptions-with-spark-nlp/).**

   ### 1. Training the NER Model

![Flowchart](https://github.com/user-attachments/assets/cb4d7e6d-ae26-4da1-9c75-32c638ecebae)

   ### 2. OCR and NER Pipeline for Prescription Processing

- **OCR (Optical Character Recognition)**  
   - Converts handwritten doctor prescriptions into machine-readable text using OCR techniques.

- **NER (Named Entity Recognition)**  
   - **Input:** Text from the OCR step containing unstructured data such as medicine names and dosage instructions.
   - **BERT Embedding:** Converts the input text into context-aware embeddings.
   - **CHAR CNN-BiLSTM:**  
     - Character-level CNN captures morphological features of words.
     - BiLSTM captures bidirectional context of the text sequence.
   - **CRF (Conditional Random Field):** Ensures valid label sequences for structured output like medicine names, dosages, and eating schedules.
  
![Flowchart (1)](https://github.com/user-attachments/assets/b53ba391-5d47-4c3b-9681-a4d4c28f3f53)

**Output:** Structured data with medicine names, dosages, and schedules extracted from the text.

## Technologies Used
- Python
- Natural Language Processing (NLP) techniques
- AWS Textract 
- Named Entity Recognition (NER) techniques
- Machine Learning Algorithms
- Cron Jobs

## Setup Instructions
To set up the project locally, follow these steps:
1. Clone the repository
```
git clone https://github.com/Gupta-Aryaman/scanPlus.git
cd scanPlus
```
2. Create a virtual environment
```
python3 -m venv venv
source venv/bin/activate   # On Windows use `venv\Scripts\activate`
```
3. Install the required dependencies
```
pip install -r requirements.txt
```
4. Configure AWS Textract
   - Ensure you have AWS credentials configured. You can use the AWS CLI to set this up:
  ```
  aws configure
  ```
   - Add your region_name, aws_access_key_id and aws_secret_access_key in api/ml_model/ml_model.py file
5. Create the model
   - Go in api/ml_model folder, and open ner.py
   - call the train_model function to the ner train the model
6. Run the project
   - Run the ML model flask app by ->
```
cd api
python3 api.py
```
   - Run the frontend flask app by ->
```
cd frontend
python3 app.py
```
7. Set up Cron Jobs (if applicable)
   - Configure the cron jobs as per your requirements to automate tasks.

## Usage
1. Upload or provide the handwritten prescription image to the system.
2. The system will process the image, extract text, classify it and get the medicine names and dosages along with their schedule.
3. The application will send you email reminders when it's time to take your medication, based on your scheduled dosage timings.

## Contributing
1. Fork the repository.
2. Create a new branch (git checkout -b feature-branch).
3. Commit your changes (git commit -m 'Add some feature').
4. Push to the branch (git push origin feature-branch).
5. Open a pull request.

## License
This project is licensed under the [MIT License](https://github.com/Gupta-Aryaman/scanPlus/blob/main/LICENSE).
=======
# Ocr
>>>>>>> e9158ed25e54fd8cc4ef08016d57d2dec79b237f
