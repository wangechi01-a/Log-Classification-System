# Log Classification System

## Overview
This project implements a hybrid log classification system that combines multiple approaches to efficiently process logs with different complexity levels. By integrating rule-based, machine learning, and deep learning techniques, the system ensures accurate classification even when dealing with unpredictable patterns.

---

## Classification Methods

1. **Regular Expressions (Regex)**
   - Best suited for structured and predictable log patterns.
   - Uses predefined rules to classify logs efficiently.

2. **Sentence Transformer + Logistic Regression**
   - Ideal for complex patterns when sufficient labeled training data is available.
   - Leverages Sentence Transformers to generate embeddings, which are then classified using Logistic Regression.

3. **Large Language Models (LLMs)**
   - Handles intricate log patterns when training data is insufficient.
   - Acts as a fallback mechanism to improve classification performance.

---

## Project Structure

1. **`training/`**
   - Contains scripts for training models using Sentence Transformers and Logistic Regression.
   - Includes regex-based classification logic.

2. **`models/`**
   - Stores trained models, such as embeddings from Sentence Transformers and the Logistic Regression classifier.

3. **`resources/`**
   - Holds supplementary files like sample CSV datasets, generated outputs, and other project-related resources.

4. **Root Directory**
   - Houses the FastAPI server implementation (`server.py`).

---

## Installation and Setup

### 1. Install Dependencies
Ensure Python is installed, then install the required libraries by running:
```bash
pip install -r requirements.txt
```

### 2. Start the FastAPI Server
Run the following command to launch the server:
```bash
uvicorn server:app --reload
```

Once running, access the API through:
- **Main Endpoint:** `http://127.0.0.1:8000/`
- **Swagger Documentation:** `http://127.0.0.1:8000/docs`
- **ReDoc API Reference:** `http://127.0.0.1:8000/redoc`

---

## Usage
To classify logs, upload a CSV file containing the following columns:
- `source`
- `log_message`

The system will return a processed CSV with an additional `target_label` column, indicating the predicted classification for each log entry.

