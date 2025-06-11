Quick Start Guide:

1. Create virtual environment:
   python -m venv venv
   venv\Scripts\activate

2. Install Rasa:
   pip install rasa

3. Train the model:
   rasa train

4. Start the server:
   rasa run -m models --enable-api --cors "*" --debug

5. Open index.html in your browser to test the chatbot.
