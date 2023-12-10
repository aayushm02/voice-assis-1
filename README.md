# voice-assis-1
the start of the ml journey with the very basics of the voice assistant features and library knowledge....
import speech_recognition as sr
import subprocess
from  AppOpener import open
import gtts
from playsound import playsound



#setting lang 
language = 'en'

# Create a recognizer object
r = sr.Recognizer()

# Use the recognizer to recognize speech from the microphone
with sr.Microphone() as source:
    audio = r.listen(source)

# Try to recognize the speech
try:
    mtext = r.recognize_google(audio)
    print("voice input is: " + mtext)
    tts = gtts.gTTS(text=mtext)
    tts.save("welcome.mp3")
    playsound("welcome.mp3")
 #   os.system("welcome.mp3")


except sr.UnknownValueError:
    print("Could not recognize speech")

#conditional statements for the check of the commands in real time for performing functions ::

if mtext == "open Notepad":
    open("Notepad")
elif mtext == "open Valorant":
    open("Valorant")
elif mtext == "open spotify":
    open("Spotify")
elif mtext == "open Chrome":
    open("Google Chrome")
elif mtext == "open WhatsApp":
    open("Whatsapp")
    
