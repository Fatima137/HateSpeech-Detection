# Hate Speech Detection from Audio

This project uses an AI model to transcribe audio and detect hate speech in English and Roman Urdu. The system mounts a pre-trained model from Google Drive, processes audio input, transcribes it into text, and classifies the text as hate speech or not.

## Features
- Mounts the hate speech detection model from Google Drive.
- Accepts an audio file as input.
- Uses OpenAI Whisper or Google Speech-to-Text for transcription.
- Classifies transcribed text using a pre-trained machine learning model.
- Outputs whether the text contains hate speech.

## Prerequisites
Ensure you have the following installed:
- Python 3.8+
- Required Python libraries:
  ```sh
  pip install openai gdown joblib speechrecognition pydub
  ```
- Google Drive access to store and retrieve the AI model.

## Setup
1. Clone the repository:
   ```sh
   git clone <repository-url>
   cd <repository-folder>
   ```
2. Download the hate speech detection model from Google Drive:
   ```python
   import gdown
   gdown.download("YOUR_GDRIVE_MODEL_LINK", "hate_speech_model.pkl", quiet=False)
   ```
3. Place your audio file in the project directory.

## Usage
Run the script with an audio file as input:
```sh
python inference.py /path/to/audio/file.mp3
```

## Code Structure
- `HateSpeech.py` - Main script to process audio and detect hate speech.
- `hate_speech_model.pkl` - Pre-trained machine learning model.
- `mergedDataset` - DataSet in english and roman urdu.

## How It Works
1. **Model Loading**: Downloads the hate speech detection model from Google Drive if not already present.
2. **Transcription**: Uses OpenAI Whisper API or Google Speech-to-Text to transcribe the given audio file.
3. **Hate Speech Detection**: Uses a pre-trained model to classify the transcribed text.
4. **Output**: Displays whether the text contains hate speech.

## Example Output
```sh
Transcribed Text: "This is an example sentence."
Hate Speech Detected: No
```

## Troubleshooting
- If `whisper_timestamped` is missing, use an alternative transcription method like OpenAI Whisper API.
- Ensure `hate_speech_model.pkl` is downloaded correctly.
- If using OpenAI’s Whisper API, provide a valid API key.

## License
This project is for educational purposes only.
