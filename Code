import pyttsx3
import datetime
import speech_recognition as sr


engine = pyttsx3.init()


def speak(audio):
    engine.say(audio)
    engine.runAndWait()

def time():
    Time = datetime.datetime.now().strftime("%I:%M:%S")
    speak(Time)

def date():
    year = int(datetime.datetime.now().year)
    month = int(datetime.datetime.now().month)
    date = int(datetime.datetime.now().day)
    speak(date)
    speak(month)
    speak(year)

def wishme():
    speak("Hey there noodle!")
    speak("the time is")
    time()
    speak("the date is")
    date()
    hour = datetime.datetime.now().hour
    if hour >= 6 and hour<12:
        speak("Have a good morning noodle!")
    elif hour >=12 and hour<18:
        speak("Enjoy your afternoon noodle!")
    elif hour >= 18 and hour<24:
        speak("Have a good evening noodle!")
    else:
        speak("Enjoy your night noodle!")
    speak("I am at your service. Please tell me how i can help you")
wishme()

def takeCommand():
    r = sr.Recognizer()
    with sr.Microphone()as source:
        print("Listening...")
        r.pause_threshold = 1
        audio = r.listen(source)

    try:
        print("Recognizing...")
        query = r.recognize_google(audio, language='en-in')
        print(query)

    except Exception as e:
        print(e)
        speak("Noodle say that again...")

        return "None"
    return query

takeCommand()
