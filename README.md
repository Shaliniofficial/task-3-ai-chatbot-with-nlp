# task-3-ai-chatbot-with-nlp
# chatbot_nlp.py

import nltk
import random
import string
from nltk.chat.util import Chat, reflections
from nltk.corpus import wordnet
from nltk.tokenize import word_tokenize

# Download NLTK data
nltk.download('punkt')
nltk.download('wordnet')

# Define a basic set of pairs (question-response)
pairs = [
    [
        r"(hi|hello|hey|hii|heyy)",
        ["Hello!", "Hi there!", "Hey! How can I help you?"]
    ],
    [
        r"(what is your name?|who are you?)",
        ["I am a simple NLP-based chatbot created by Shalini."]
    ],
    [
        r"(how are you?|how’s it going?)",
        ["I'm good! Thanks for asking.", "Doing well. What about you?"]
    ],
    [
        r"(.*) (your name|created you|made you)",
        ["My creator is Shalini for her Codetch internship."]
    ],
    [
        r"(bye|exit|quit)",
        ["Goodbye!", "See you later!", "Have a great day!"]
    ],
    [
        r"(.*)",
        ["Sorry, I didn’t get that.", "Can you rephrase it?", "I’m still learning. Try asking something else."]
    ]
]

# Create chatbot using NLTK
chatbot = Chat(pairs, reflections)

# Run chatbot
print("Hi, I'm your NLP Chatbot! Type 'bye' to exit.")
chatbot.converse()
