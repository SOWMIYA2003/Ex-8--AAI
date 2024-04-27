 <H3>ENTER YOUR NAME : Sowmiya N</H3>
<H3>ENTER YOUR REGISTER NO : 212221230106</H3>
<H3>EX. NO.8</H3>
<H3>DATE:27.04.2024</H3>
<H1 ALIGN =CENTER>Implementation of Speech Recognition</H1>
<H3>Aim:</H3> 
 To implement the conversion of live speech to text.<BR>
<h3>Algorithm:</h3>
Step 1: Import the speech_recognition library<Br>
Step 2: Initialize the Recognizer<Br>
Step 3: Create an instance of the Recognizer class, which will be used for recognizing speech.<Br>
Step 4: Set the duration for audio capture<Br>
Step 5: Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.<Br>
Step 6: Display a message in the console to prompt the user to speak.<Br>
Step 7: Capture audio from the default microphone<Br>
Step 9: Use the default microphone as the audio source.<Br>
Step 10: Record audio for the specified duration using the Recognizer instance.<Br>
Step 11: Perform speech recognition with exceptional handling:<Br>
•	Attempt to recognize speech from the captured audio using the Google Speech Recognition service.<Br>
•	If successful, print the recognized text.<Br>
•	Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.<Br>
•	A generic exception block captures any other unexpected errors.<Br>

### Program:

```
pip install SpeechRecognition
pip install pyaudio
# Initialize the Recognizer
import speech_recognition as sr
r=sr.Recognizer()
# Set the duration for audio capture
duration = 5  # seconds
# Record audio
print("Start Speech")
# Use the default microphone as the audio source
with sr.Microphone() as source:
    audio_data=r.listen(source,timeout=duration)
# Perform speech recognition with exception handling
try:
    text=r.recognize_google(audio_data)
    print("You said:",text)
except sr.UnknownValueError:
    print("Sorry,could not understand audio")
except sr.RequestError as e:
    print(f'Error with the request to Google Speech Recognition service : {e}')
except Exception as e :
    print(f'Error:{e}')
```

### Output:
![op](./a1.png)
![op](./a2.png)
###  Result:
 Thus the implementation of  the conversion of live speech to text is done successfully.