# EXPT-5-Speech-Recognition-using-Python

# AIM: 

# To perform and verify speech recognition using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```asm
!pip install SpeechRecognition pydub

import speech_recognition as sr
from pydub import AudioSegment
from google.colab import files

# Step 1: Upload file (this shows upload button in output)
uploaded = files.upload()

# Step 2: Get uploaded file name
file_name = list(uploaded.keys())[0]
print("Uploaded file:", file_name)

# Step 3: Convert to WAV (handles mp3, etc.)
audio = AudioSegment.from_file(file_name)
audio.export("converted.wav", format="wav")

# Step 4: Speech Recognition
r = sr.Recognizer()

with sr.AudioFile("converted.wav") as source:
    print("Reading audio...")
    audio_data = r.record(source)

    print("Recognizing...")
    try:
        text = r.recognize_google(audio_data)
        print("Recognized Text:\n", text)
    except sr.UnknownValueError:
        print("Could not understand audio")
    except sr.RequestError as e:
        print("API Error:", e)
```

# OUTPUT: 
<img width="1016" height="281" alt="image" src="https://github.com/user-attachments/assets/dfb0481b-a5fd-4c28-9f02-3a6d8d497aa5" />


# RESULT: 
Thus the speech recognition using SCILAB was performed and verified.
