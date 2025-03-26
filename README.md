# 🚀 Project Name : Gen AI-Based Email Classification 

## 📌 Table of Contents
- [Introduction](#introduction)
- [Demo](#demo)
- [Inspiration](#inspiration)
- [What It Does](#what-it-does)
- [How We Built It](#how-we-built-it)
- [Challenges We Faced](#challenges-we-faced)
- [How to Run](#how-to-run)
- [Tech Stack](#tech-stack)
- [Team](#team)

---

## 🎯 Introduction
With the rapid growth of email communication, identifying and categorizing emails efficiently is a critical task. Manually analyzing emails for classification can be tedious and error-prone. This project aims to simplify the process by using Gen AI to classify and extract meaningful details from .eml, .pdf, .docx, .txt files.
Our solution allows users to upload email file (.eml) and attachments files (.pdf, .docx,.txt) by selecting a file manually. Once uploaded, the file is processed using a Flask-based backend integrated with an OpenAI model (gpt-3.5) to classify and extract relevant information.


## 🎥 Demo

🖼️ **Screenshots**: Screenshots of the application are available in the following powerpoint presentation : https://github.com/ewfx/gaied-semper-fortis/tree/main/artifacts/<br>

🔗 **Live/ Demo (Applicable)** : Demo display of application can be accessed inside the following powerpoint presentation under ;Application Demo' slide : https://github.com/ewfx/gaied-semper-fortis/tree/main/artifacts/<br>


## 💡 Inspiration
Handling large volumes of emails manually often leads to inefficiencies and errors. Inspired by the need to automate this task, we developed a Gen AI-based email classification tool that accurately extracts and classifies email content. Our goal was to enhance productivity and reduce manual efforts by leveraging AI technologies.

## ⚙️ What It Does
•	File Uploading: Allows users to upload  .eml, .pdf, .docx, .txt files via drag-and-drop or file selection.<br>
•	Email/ document Parsing & Extraction: Extracts key details from the email body, including sender, subject, and content.<br>
•	AI-Based Classification: Uses Gen AI to classify and analyze the email content.<br>
•	Result Display: Shows classified results with extracted information dynamically on the frontend.<br>


## 🛠️ How We Built It
**Frontend: Angular**

   •	Manual file selection Interface: We created manual file selection interface using Angular, allowing users to easily upload .eml, .pdf, .docx, .txt files.<br>
   •	API Calls to Flask Backend: We used Angular’s provideHttpClient to make POST API calls to the Flask backend, sending the file to be processed and receiving the result.<br>
   •	Dynamic Responses with Angular: Angular’s *ngIf and innerHTML were used to dynamically update the UI based on the backend's response, rendering the results neatly in the interface.<br>

**Backend: Flask (Python)**

   •	**File Parsing**: We used Python's built-in email library to parse the uploaded files and the BeautifulSoup (bs4) library to extract and clean the email contents. Used OpenAI API to classify email content and extract relevant information.<br>
   •	Define /validate Endpoint: We created a POST endpoint (/validate) in the Flask backend to:<br>
      -   Receive the uploaded .eml file.<br>
      -   Process the email contents and classify them using the LLM model.<br>
      -   Return the classification results back to the frontend in JSON format.<br>
   
   •	**LLM Model Handling (OpenAI API)**: After parsing the email content, we integrated the OpenAI API to classify the email content based on the extracted data. We used the model to:<br>
      -   Understand the subject and body of the email.<br>
      -   Classify the email into predefined categories (e.g., personal, promotional, work-related).<br>
      -   Extract relevant information such as sender, recipient, date, and subject.<br>
   
**File Handling Logic**

   •	Validated file type (.eml, .pdf, .docx, .txt) on the backend.<br>
   •	Sent the file to the backend using FormData and displayed error messages if the file was invalid.<br>
   •	Dynamically updated the UI based on the response.<br>


## 🚧 Challenges We Faced

1.	Email Parsing Complexity:<br>
   •	Parsing multi files at the backend and extracting clean, structured content was challenging.<br>
2.	Identify the new service request/ duplicate mail for existing service request<br>
   •	Identifying the new service request or the duplicate mail for the existing service request based on multi user text.<br>
3.	API Latency:<br>
   •	Delays in getting responses from the Gen AI model.<br>
   •	Handled using loading indicators and setting error timeouts.<br>


## 🏃 How to Run

**Prerequisites**:

•	Node.js and Angular CLI installed.<br>
•	Python 3.x with Flask installed.<br>
•	Install required Python packages <br>

**Setup: Backend**

1.	Clone the Repository.	To clone the repository from GitHub, run the following command:<br>
Replace with your actual repository URL<br>
`git clone https://github.com/ewfx/gaied-semper-fortis.git`<br>
Navigate to the project directory<br>
`cd gaied-semper-fortis/backend`<br>

2.	Create a Virtual Environment.	To keep dependencies isolated, create a virtual environment.<br>
`python -m venv venv`<br>

3.	Activate the Virtual Environment.	After creating the virtual environment, activate it.<br>
`venv\Scripts\activate`<br>
Once activated, you should see (venv) in your terminal.<br>

4.	Install Required Dependencies.	Install all required packages from requirements.txt:<br>
`pip install -r requirements.txt`<br>

5.	Run the Flask Application.		To start the Flask application, Navigate to the Flask backend directory and run:<br>
`python app.py`<br>
`Flask API will run on http://127.0.0.1:5000.`<br>


**Setup: Frontend**

1. Clone the Repository.	To clone the repository from GitHub, run the following commands:<br>
Replace with your actual repository URL<br>
`git clone https://github.com/ewfx/gaied-semper-fortis.git`<br>
Navigate to the project directory<br>
`cd gaied-semper-fortis/frontend`<br>

2. Install Node.js and npm (If Not Installed).	install Node.js and npm. After installation, verify the versions:<br>
`node -v`<br>
`npm -v`<br>

3. Install Project Dependencies (node_modules).	Navigate to frontend project directory and Install node_modules folder with dependencies by running:<br>
Install dependencies from package.json<br>
`npm install`<br>

4. Run the Angular Application.	Once dependencies are installed, run the application:<br>
Run the Angular development server<br>
`ng serve`<br>
Open http://localhost:4200 in your browser.<br>

## 🏗️ Tech Stack

**Frontend:**

•	**Angular**: For building the single-page application (SPA) with dynamic views and user interactions.<br>
•	**provideHttpClient (Angular)**: For making HTTP requests to the Flask backend and handling file uploads.<br>
•	**CSS/HTML**: For styling and structuring the frontend components.<br>

**Backend:**

•	**Flask**: A lightweight Python web framework used to create the API endpoint (/validate) for receiving the file and processing it.<br>
•	**Python**: The primary programming language for the backend logic, including file parsing and integration with the LLM model.<br>
•	**email (Python Library)**: Used to parse the uploaded .eml files and extract the email content.<br>
•	**BeautifulSoup (bs4)**: For cleaning and extracting structured data from the raw email content.<br>
•	**OpenAI API**: For classifying the email content using a pre-trained large language model (LLM).<br>

**Development Tools:**

•	Visual Studio Code (VS Code): For frontend and backend code development.<br>
•	Git: For version control, collaborating on the project, and managing the code repository.<br>

**Deployment & Hosting:**

•	GitHub: For code version control and repository management.<br>


## 👥 Team

- Abhishek Gupta<br>
- Yatish Gupta<br>
- Gaurav Kumar<br>

# SemperFortis
