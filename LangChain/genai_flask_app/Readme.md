# AI Assistant — IBM watsonx.ai + Flask

A web-based AI assistant built with **Flask, LangChain, and IBM watsonx.ai**. The application allows users to interact with different large language models (LLMs) through a simple chat interface.

## Features

- **Multiple AI Models:** Choose between Llama, Granite, and Mistral.
- **Interactive Chat Interface:** Send messages and view AI-generated responses.
- **Model Selection:** Select the model you want to use for each request.
- **Response Time Tracking:** Measure the time taken to generate a response.
- **REST API:** Flask endpoint for processing chat requests.
- **Error Handling:** Handles missing inputs, invalid model selections, and processing errors.
- **Responsive UI:** HTML, CSS, and JavaScript-based frontend.

## Tech Stack

| Technology | Purpose |
|---|---|
| Python 3.11 | Backend programming |
| Flask | Web framework and REST API |
| IBM watsonx.ai | Access to foundation models |
| LangChain | LLM integration |
| HTML | Frontend structure |
| CSS | Frontend styling |
| JavaScript | Chat interactions and API requests |
| Git & GitHub | Version control |

## Project Structure

```text
genai_flask_app/
├── app.py                 # Flask application and API routes
├── model.py               # AI model integration
├── templates/
│   └── index.html         # Chat interface
├── static/
│   ├── styles.css         # Frontend styling
│   └── script.js          # Frontend interactions
├── requirements.txt       # Python dependencies
├── .gitignore             # Files excluded from Git
└── README.md              # Project documentation
```

## Getting Started

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd genai_flask_app
```

### 2. Create a virtual environment

```bash
python3.11 -m venv venv
```

**Linux/macOS**
```bash
source venv/bin/activate
```

**Windows**
```powershell
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure IBM watsonx.ai credentials

Configure the credentials required by your implementation, such as your IBM Cloud API key, watsonx.ai service URL, and project ID.

Use environment variables or a local `.env` file if your implementation supports them.

**Never commit API keys, access tokens, or `.env` files to GitHub.**

### 5. Run the application

```bash
python app.py
```

Open the local address shown in your terminal, usually:

`http://127.0.0.1:5000`

## API Usage

### Generate an AI response

- **Endpoint:** `POST /generate`
- **Content-Type:** `application/json`

Example request:

```json
{
  "message": "Explain generative AI in simple words.",
  "model": "llama"
}
```

Supported model identifiers:

- `llama`
- `granite`
- `mistral`

Example response structure:

```json
{
  "response": "Generative AI creates new content based on patterns learned from data.",
  "duration": 1.25
}
```

The exact response fields depend on the implementation of the functions in `model.py`.

## How It Works

1. The user enters a message and selects an AI model.
2. JavaScript sends a JSON request to Flask's `/generate` endpoint.
3. Flask validates the request and identifies the selected model.
4. The corresponding function in `model.py` calls IBM watsonx.ai.
5. The generated response and processing duration are returned to the frontend.
6. JavaScript displays the response in the chat interface.

## Learning Outcomes

Through this project, I practiced:

- Integrating foundation models into a Python application.
- Using Flask to create HTTP routes and JSON APIs.
- Connecting LLMs with LangChain.
- Building an interactive frontend with HTML, CSS, and JavaScript.
- Managing Python dependencies with virtual environments.
- Handling API requests, errors, and response timing.

## Acknowledgements

This project was developed as part of my learning through IBM's Generative AI and LangChain coursework on Coursera.

---

**Author:** Vansh Gupta
