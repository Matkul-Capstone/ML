# Pronunciation Feedback Application

This project provides a FastAPI-based web application for analyzing pronunciation accuracy based on a reference passage. It uses Mozilla's DeepSpeech for speech-to-text transcription and gives feedback on mispronounced or extra words.

## Features

- **Audio Transcription**: Converts and processes uploaded audio files for transcription.
- **Pronunciation Analysis**: Compares transcribed text with a reference passage and provides feedback.
- **Accuracy Calculation**: Calculates the pronunciation accuracy based on matched words.

## Requirements

- Python 3.8.10
- DeepSpeech 0.9.3 model files
- Dependencies specified in `requirements.txt`

## Installation

1. Clone the repository:
    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Download the DeepSpeech model and scorer files from [DeepSpeech Releases](https://github.com/mozilla/DeepSpeech/releases/tag/v0.9.3). Place them in a folder named `deepspeech-model` in the root directory.

## Usage

### Run the Application

1. Start the FastAPI server:
    ```bash
    uvicorn main:app --host 0.0.0.0 --port 8000
    ```

2. Access the API documentation at `http://localhost:8000/docs`.

### API Endpoints

#### `POST /transcribe`

Uploads an audio file and a reference passage to get transcription and pronunciation feedback.

- **Request Parameters**:
  - `file`: Audio file to be transcribed (required).
  - `reference_passage`: Reference text for pronunciation analysis (required).

- **Response**:
  - `transcription`: The transcribed text.
  - `accuracy`: Pronunciation accuracy percentage.
  - `feedback`: List of feedback messages for mispronounced or extra words.
  - `wrong_words`: Words that were mispronounced or missing.
  - `correct_words`: Words correctly pronounced.

### Example Usage

1. Upload an audio file (e.g., `example.wav`) along with a reference passage using a tool like Postman or `curl`:
    ```bash
    curl -X POST "http://localhost:8000/transcribe" \
         -F "file=@example.wav" \
         -F "reference_passage=This is a sample reference passage."
    ```

2. Receive a JSON response with transcription, accuracy, and feedback.

## Audio Format Requirements

- **Sample Rate**: 16,000 Hz
- **Channels**: Mono
- **Sample Width**: 2 bytes (16-bit)

The application automatically converts audio files to the required format using `pydub`.

## Folder Structure

```
.
├── deepspeech-model/           # Contains DeepSpeech model and scorer files
├── main.py                    # Main application file
├── requirements.txt           # Python dependencies
└── README.md                  # Project documentation
```

## Dependencies

- `deepspeech`
- `numpy`
- `pydub`
- `fastapi`
- `uvicorn`

Install dependencies using:
```bash
pip install -r requirements.txt
```

## Features

- **Audio Transcription**: Converts and processes uploaded audio files for transcription.
- **Pronunciation Analysis**: Compares transcribed text with a reference passage and provides feedback.
- **Accuracy Calculation**: Calculates the pronunciation accuracy based on matched words.

## Requirements

- Python 3.8.10
- DeepSpeech 0.9.3 model files
- Dependencies specified in `requirements.txt`

## Installation

1. Clone the repository:
    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Download the DeepSpeech model and scorer files from [DeepSpeech Releases](https://github.com/mozilla/DeepSpeech/releases/tag/v0.9.3). Place them in a folder named `deepspeech-model` in the root directory.

## Usage

### Run the Application

1. Start the FastAPI server:
    ```bash
    uvicorn main:app --host 0.0.0.0 --port 8000
    ```

2. Access the API documentation at `http://localhost:8000/docs`.

### API Endpoints

#### `POST /transcribe`

Uploads an audio file and a reference passage to get transcription and pronunciation feedback.

- **Request Parameters**:
  - `file`: Audio file to be transcribed (required).
  - `reference_passage`: Reference text for pronunciation analysis (required).

- **Response**:
  - `transcription`: The transcribed text.
  - `accuracy`: Pronunciation accuracy percentage.
  - `feedback`: List of feedback messages for mispronounced or extra words.
  - `wrong_words`: Words that were mispronounced or missing.
  - `correct_words`: Words correctly pronounced.

### Example Usage

1. Upload an audio file (e.g., `example.wav`) along with a reference passage using a tool like Postman or `curl`:
    ```bash
    curl -X POST "http://localhost:8000/transcribe" \
         -F "file=@example.wav" \
         -F "reference_passage=This is a sample reference passage."
    ```

2. Receive a JSON response with transcription, accuracy, and feedback.

## Audio Format Requirements

- **Sample Rate**: 16,000 Hz
- **Channels**: Mono
- **Sample Width**: 2 bytes (16-bit)

The application automatically converts audio files to the required format using `pydub`.

## Folder Structure

```
.
├── deepspeech-model/           # Contains DeepSpeech model and scorer files
├── main.py                    # Main application file
├── requirements.txt           # Python dependencies
└── README.md                  # Project documentation
```

## Dependencies

- `deepspeech`
- `numpy`
- `pydub`
- `fastapi`
- `uvicorn`

Install dependencies using:
```bash
pip install -r requirements.txt
```
