# Speech Recognition and Repeater

This is a simple Python program that utilizes SpeechRecognition library to recognize speech input from the microphone and repeats it back. It provides a basic example of how to capture audio from the microphone, convert it to text using Google's speech recognition service, and then output the recognized text.

## Prerequisites

Make sure you have the following prerequisites installed:

- Python 3.x
- SpeechRecognition library
- pyttsx3 library
- pyaudio library

You can install the required libraries using pip:

```
pip install SpeechRecognition
pip install pyttsx3
pip install pyaudio
```

## Usage

1. Run the Python script `Speech_Recognition_Repeater.ipynb`.
2. Once the program starts, it will ask you to maintain silence briefly to adjust for ambient noise.
3. After that, it will prompt you to speak.
4. Speak clearly into the microphone.
5. The program will then repeat the text it recognized from your speech.

## Code Example

```python
import speech_recognition
import pyttsx3

sr = speech_recognition.Recognizer()
with speech_recognition.Microphone() as source:
    print('Silence please')
    sr.adjust_for_ambient_noise(source, duration=2)
    print('Speak now...')
    audio = sr.listen(source)
    audio_to_text = sr.recognize_google(audio)
    audio_to_text = audio_to_text.lower()
    print('Did you say: ' + audio_to_text)
```

## Note

- You can uncomment the `SpeakNow()` function in the provided code to hear the recognized speech output through the computer's speakers.

## Contribution

Contributions are welcome! Feel free to fork this repository, make changes, and submit pull requests.
