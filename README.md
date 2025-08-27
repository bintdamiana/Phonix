# Phonix 🔥
Phonix: a free, AI powered tool for learning phonetics and the International Phonetic Alphabet.

👋 Welcome to Phonix!
Phonix is an open access educational tool that uses AI to deliver detailed phonetic analysis, making the intricacies of spoken language accessible to everyone.  Think of it as a helpful assistant, guided by Phonix the Phoenix 🔥, that turns audio input into pedagogical phonetic explanations.

This project is currently a solo endeavor, built out of a passion for open and accessible education. I've launched the initial version with a core mission: to provide high quality phonetic resources that are free, forever.

🤝 Let's Build This Together 🤝 
To evolve Phonix, I'm looking to collaborate with other developers and visionaries. Whether your expertise is in NLP, AI, open source tech, or education, your contribution could help shape the future of this project. If our mission resonates with you, please reach out!

✨ What Phonix offers:
Deeper Linguistic Insights: Phonix provides a fine grained phonetic breakdown, grounded in our IPA mapped knowledge base, to explain how and why specific sounds are produced.
Accessible Self Practice: A browser-based interface allows you to practice pronunciation and receive instant, detailed feedback, effectively serving as a personalized, AI powered phonetic coach.
Educational Utility: This tool can be used in classrooms for demonstrative phonetics or by students for independent, targeted practice.
Transparent AI and RAG: Phonix serves as a pedagogical example of a Retrieval Augmented Generation (RAG) system. By coupling a trusted, curated knowledge base (phonix_data.json) with a local LLM, it illustrates how AI can be grounded in facts rather than hallucinating responses.
🧠 The Phonetic Pipeline
The processing pipeline includes the following:
Speech-to-Text (Faster-Whisper): Audio input is transcribed into text using the Faster-Whisper model. This is the first step in converting spoken language into a machine-readable format.
Grapheme-to-Phoneme (Eng-to-IPA): The transcribed text is then passed to a custom Eng-to-IPA service. This component generates a phonetic transcription (an IPA string) from the orthographic input, creating a detailed "sound map" of the word.
Knowledge Retrieval and Generation (LLM + RAG):
Retrieval: The IPA transcription serves as the key for the RAG system. The program queries the curated phonix_data.json knowledge base to retrieve specific, expert-authored information about the constituent phonemes.
Generation: A local Large Language Model (phi3:mini via Ollama) processes the retrieved information and the initial request. It synthesizes a clear, educational explanation.
Text-to-Speech (Rime TTS API): The final explanation is converted into high-fidelity audio using the Rime TTS API. This completes the feedback loop by speaking the phonetic breakdown back to the user.

🖥️ Demo & Local Deployment
Try the Live Demo
Experience the full pipeline live on Hugging Face Spaces.
[LINK TO DEMO SOON...]

Run Locally (Windows PC)
To deploy Phonix on your local machine, ensure you have the necessary prerequisites:
Prerequisites:
Python: Version 3.10 or newer.
Ollama: Installed and configured for running local LLMs.
Rime API Key: Obtain a key from the Rime website for TTS services.
Installation Instructions:
Clone the Repository:
bash
git clone https://github.com/bintdamiana/Phonix.git
cd Phonix
Use code with caution.

Set up the Virtual Environment:
bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
Use code with caution.

Download the LLM:
bash
ollama pull phi3:mini
Use code with caution.

Configure API Key:
Add your Rime API key as an environment variable named RIME_API_KEY.
Restart your terminal to apply the changes.
Run the Application:
bash
python app.py
Use code with caution.

📦 Project Structure
phonix/
├── .gitignore
├── app.py                      # Core application logic and Gradio interface
├── requirements.txt            # Python dependencies
├── phonix_data.json            # Curated phonetic knowledge base for RAG
├── README.md                   # This document
├── LICENSE                     # License information
└── ...

🔸 Future Enhancements 🔸
The Phonix project is a platform for ongoing development and enhancement:

Multilingual Expansion: Extend the knowledge base and pipeline to support phonemes from a broader range of languages.
Advanced Phonetic Analysis (MFA): Integrate the Montreal Forced Aligner (MFA) for more robust and precise phoneme-level timing and segmentation.
Vector Database Integration (e.g., ChromaDB): A vector database like ChromaDB would be a significant upgrade. This would enable faster and more efficient retrieval of phonetic information, especially as the knowledge base grows to include more languages and detailed data.
Offline TTS Integration: Investigate a local, self hosted TTS solution to reduce reliance on external APIs and enable offline usage.
Enhanced Knowledge Base: Continually grow and refine the phonetic knowledge base (phonix_data.json) with richer content and more nuanced explanations.

🤝 Contributions Welcome
This is an open source project, and contributions are welcome. Please feel free to open an issue or submit a pull request.

📄 License
This project is licensed under the GPL (GNU General Public License). See the LICENSE file for details.

📧 Contact
Sahara Al-Madi - <Thecyberlingo@gmail.com>
Project Link: https://github.com/bintdamiana/Phonix
