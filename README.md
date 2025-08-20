
# AiAssistant V2.1

An advanced, modular AI assistant built with open-source, lightweight technologies designed for natural language understanding, personalized memory, voice interaction, and dynamic knowledge retrieval. This assistant balances state-of-the-art capabilities with efficient resource use, enabling deployment on moderate hardware without requiring paid APIs or large GPUs.

---

## Features

- **Transformer-based Language Understanding**  
  Utilizes the `all-MiniLM-L6-v2` sentence transformer model to generate rich semantic embeddings for user inputs, enabling robust intent classification.

- **Intent Classification Neural Network**  
  A custom feedforward neural network classifies user intents based on sentence embeddings, supporting diverse conversational intents.

- **Named Entity Recognition & Slot Extraction**  
  Incorporates regex-based entity extraction for recognizing names, dates, and other relevant entities from user queries.

- **Personalized Memory Management**  
  Stores and recalls user-specific information securely across sessions, enabling personalized conversations.

- **External Knowledge Integration**  
  Falls back to searching Wikipedia for answers when intent confidence is low or queries are outside the known scope.

- **Voice Interaction Support**  
  Supports both speech-to-text and text-to-speech using `speech_recognition` and `pyttsx3` libraries for seamless voice communication.

- **Modular and Extensible Design**  
  Clear separation of components for easy customization, extension, and maintenance.

---

## Project Structure

AiAssistant V2.1/
├── main.py # Entry point: voice and text interactive assistant
├── model.py # Neural network model definition
├── train.py # Model training pipeline with validation and early stopping
├── dataset.py # Dataset class using transformer embeddings
├── nlp_utils.py # Text preprocessing, embedding, slot extraction, Wikipedia search
├── memory.py # User information storage and retrieval
├── listen.py # Speech-to-text interface
├── speak.py # Text-to-speech interface
├── intents.json # Intent definitions with patterns and responses
├── config.py # Configuration and hyperparameters
├── requirements.txt # Required packages

text

---

## Installation

1. Clone the repository:

git clone https://github.com/DiwakarTheDev/AiAssistantV2.1.git
cd AiAssistantV2.1



2. Install dependencies:

pip install -r requirements.txt



3. Download NLTK resources (if needed):

import nltk
nltk.download('punkt')


---

## Usage

### Train the model

python train.py

text

This trains the intent classification model on the defined intents, saving the best model as `best_model.pth`.

### Run the assistant

python main.py

text

Speak or type your queries. Say "quit" to exit the assistant.

---

## Example Intents

- Greetings ("hello", "hi")
- Information storage ("remember my birthday is December 10")
- Information retrieval ("what is my birthday?")
- Farewell ("bye", "goodbye")
- Unknown query fallback to Wikipedia search

---

## Design Decisions

- Uses **sentence-transformers** for contextual embedding generation.
- The model architecture is a simple yet effective feedforward neural network.
- Personalization is handled through a local JSON-based memory for simplicity.
- Voice capabilities utilize open-source Python libraries with no external API calls.
- Wikipedia integration adds dynamic ability to handle outside knowledge queries.

---

## Future Improvements

- Add multi-turn dialogue management for better conversational context.
- Integrate incremental learning to adapt to user feedback over time.
- Enhance slot extraction using advanced NLP models.
- Add task and reminder management features.
- Improve naturalness with lightweight generative language models.

---

## License

This project is licensed under the MIT License.

---

## Acknowledgments

- [sentence-transformers](https://www.sbert.net/)
- [PyTorch](https://pytorch.org/)
- [Wikipedia Python Library](https://pypi.org/project/wikipedia/)
- [SpeechRecognition](https://pypi.org/project/SpeechRecognition/)
- [pyttsx3](https://pypi.org/project/pyttsx3/)

---

Feel free to contribute or create issues for features and improvements!
