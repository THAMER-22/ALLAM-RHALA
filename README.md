#  Rahaala Tourism Assistant

An advanced AI-powered tourism assistant system combining voice interaction capabilities with specialized tourism planning for AlUla, Saudi Arabia.

## System Architecture

The system consists of two main components:
1. **ALLAM** - Voice-based interaction pipeline
2. **Rahaala** - Text-based tourism planning system

### Environment Setup

A `.env` file with the following configurations:

```env
# IBM Watson Configurations
IBM_MODEL_URL = "https://eu-de.ml.cloud.ibm.com"
IBM_MODEL_API = "qhPFZJCIUnmrxWW6ogONdFZrtC95EJ6pXjtLir8hU-0j"
IBM_MODEL_ID = "sdaia/allam-1-13b-instruct"
IBM_MODEL_PID = "285fb1c8-30c8-4b43-bc2c-7d208a9ec43b"

# Eleven Labs TTS Configurations
ELVEN_API = "sk_f3c5e58866644b6ef0a07817c4fa86e67189b79a244bb4a4"
ELVEN_VID = "JBFqnCBsd6RMkjVDRZzb"

# Pinecone Vector Database
PINECONE_API_KEY = "9faf8e48-01a9-422c-93ec-c7329b6708a9"
```

### Installation

1. Install dependencies:
```bash
pip install -r requirements.txt
```

Requirements include:
- pinecone-client: Vector database client
- tika: Document parsing
- ibm-watsonx-ai: IBM Watson AI services
- whisper: OpenAI's speech recognition
- ffmpeg: Audio processing
- transformers: Hugging Face transformers
- Additional utilities: nltk, python-dotenv, requests, beautifulsoup4, langchain
- pydantic==1.10.2: Data validation
- openpyxl: Excel file handling

## ALLAM Pipeline

### Overview
ALLAM is a voice-based interaction system that:
1. Converts audio input to text (Speech-to-Text)
2. Processes the text using IBM Watson's ALLAM-1-13B model
3. Generates responses using language embeddings
4. Converts responses back to audio (Text-to-Speech)

### Usage
```bash
python src/allam.py
```

### File Structure
- `src/allam.py`: Main pipeline implementation
- `src/utils.py`: Utility functions
- `src/prompt_document.py`: System prompts and document management

### Input/Output
- Input: Audio messages (e.g., WhatsApp voice notes)
- Output: Generated audio responses
- Paths configurable in `src/allam.py`

## Rahaala Pipeline

### Overview
Rahaala is a text-based tourism planning system specialized for AlUla attractions and activities.

### Usage
```bash
python src/rahaala.py
```

### File Structure
- `src/rahaala.py`: Main tourism assistant implementation
- `src/helper_rahaala.py`: Utility functions
- `src/rahaala_prompt.py`: Tourism-specific prompts

### Activities Database
- Stored in `alula_activities.xlsx`
- Contains categorized information about:
  - Heritage sites
  - Adventures
  - Restaurants
  - Hotels
  - Wellness activities
  - Prices and durations

### Recommendation System
```bash
python src/AlUla_activities.py
```
### Web Scraping & Processing
- beautifulsoup4: HTML parsing and web scraping
  - Extracts structured data from websites
  - Used for gathering additional tourism information
  - Processes HTML/XML documents
  ```python
  from bs4 import BeautifulSoup
  # Example usage in the system
  soup = BeautifulSoup(html_content, 'html.parser')
  
## Data Privacy & Security
- `.gitignore` configured to exclude:
  - Jupyter notebook checkpoints
  - Python cache files
  - Environment variables

## Model Details

### IBM Watson Configuration
- Model: SDAIA/ALLAM-1-13B
- Deployment: IBM WatsonX AI
- Specialized for Arabic language processing
- Fine-tuned for tourism domain

### Text-to-Speech
- Provider: Eleven Labs
- Configured for natural Arabic speech synthesis
- Custom voice ID for consistent output

### Vector Database
- Platform: Pinecone
- Used for semantic search and content retrieval
- Optimized for tourism-related queries

### Acknowledgments
- Partners & Contributors
- IBM Watson Team
- Eleven Labs
- Pinecone
- AlUla Tourism Authority
### Third-Party Resources
- OpenAI Whisper
- Hugging Face Transformers
- NLTK Community
