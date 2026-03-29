# Medicine Recognition System

A Flask web application that uses **Google Gemini Pro Vision** to analyze uploaded medical images and generate detailed clinical descriptions. The app identifies medical conditions, anomalies, and potential treatments from the image, with a built-in validation step to ensure only medical images are processed.

## Features

- Upload any medical image (X-ray, scan, pathology slide, etc.) for AI analysis
- Gemini Pro Vision generates detailed medical descriptions including conditions, anomalies, and treatment recommendations
- Validation step using Gemini Pro to reject non-medical images
- Clean Flask web UI with file upload support
- API key managed securely via environment variables

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| Google Gemini Pro Vision | Image-based medical content generation |
| Google Gemini Pro | Validation of medical image relevance |
| Flask | Web framework |
| Pillow | Image loading and processing |
| python-dotenv | Environment variable management |

## Project Structure

```
medicine-recognition-system/
├── app.py              # Flask application & Gemini integration
├── requirements.txt    # Python dependencies
├── templates/
│   └── index.html      # Web UI with file upload
├── static/
│   └── style.css       # Stylesheet
└── .env                # API key config (not committed)
```

## Getting Started

### Prerequisites

- Python 3.8+
- A Google Gemini API key (available at [Google AI Studio](https://aistudio.google.com/))

### Installation

```bash
git clone https://github.com/smunir25/llm-medicine-recognition-system.git
cd llm-medicine-recognition-system
pip install -r requirements.txt
```

### Configuration

Create a `.env` file in the project root:

```env
GOOGLE_API_KEY=your_google_api_key_here
```

### Run

```bash
python app.py
```

Visit `http://localhost:5000` in your browser.

## Usage

1. Click **Choose File** and upload a medical image (JPG, PNG, etc.)
2. Click **Submit**
3. The app validates the image is medically relevant
4. If valid, Gemini Pro Vision returns a detailed clinical description including:
   - Identified conditions or anomalies
   - Medical context and observations
   - Potential treatments or recommended actions
5. If the image is not medical, the app prompts to upload a valid image

## How It Works

1. **Image Upload** — The image is received and opened with Pillow
2. **Vision Analysis** — `gemini-pro-vision` processes the image with a structured medical prompt
3. **Validation** — `gemini-pro` checks if the generated context is medically relevant
4. **Response** — Valid results are displayed; invalid images are rejected with a message

## Disclaimer

> This application is for **educational purposes only**. It is not a substitute for professional medical diagnosis or clinical judgment. Always consult a qualified healthcare provider.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
