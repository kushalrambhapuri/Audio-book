# Create Your Own Audio Book with Python! 
Tired of reading PDFs? Turn them into an audio book with just a few lines of Python! Here's how to do it using Pyttsx3 and PyPDF2 libraries.
Requirements
Install Python on your computer.
Install the required libraries:
pyttsx3: A Python library for text-to-speech conversion.
PyPDF2: A library for reading and manipulating PDF files.
Download the sample PDF file for testing here or use your own.
Step 1: Install the Libraries
Open your terminal or command prompt and run the following commands:

pip install pyttsx3  
pip install PyPDF2  
Step 2: The Python Code
Here’s the complete script for creating your audio book:

import pyttsx3  
import PyPDF2  

Open the PDF file  
book = open('object_oriented_python_tutorial.pdf', 'rb')  # Replace with your PDF file name  
pdfReader = PyPDF2.PdfFileReader(book)  
pages = pdfReader.numPages  

Print the number of pages  
print(f"The PDF has {pages} pages.")  

Initialize the text-to-speech engine  
speaker = pyttsx3.init()  

Read the PDF from page 7 onwards  
for num in range(7, pages):  # Start reading from page 7  
    page = pdfReader.getPage(num)  
    text = page.extractText()  
    speaker.say(text)  
    speaker.runAndWait()  

print("Your Audio Book is ready!")  
Step 3: Running Your Code
Save the script as audio_book.py.
Place your PDF file in the same folder as the script.
Run the script in your Python environment (e.g., PyCharm).
Listen to your PDF being read out loud!
How It Works
Read the PDF: The PyPDF2 library extracts text from the given PDF file.
Text-to-Speech Conversion: The pyttsx3 library reads the extracted text aloud.
Page Selection: The script skips the first 7 pages (you can adjust this).
Notes
Ensure the PDF file is text-based, not image-based.
Adjust the range(7, pages) to start from a different page.
You can customize the voice and speech rate using the pyttsx3 settings.
Enjoy your personalized Audio Book experience! 🎧
