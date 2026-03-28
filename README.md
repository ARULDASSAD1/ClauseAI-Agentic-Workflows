⚖️ ClauseAI Ultimate: The Multimodal Neural Contract Auditor

ClauseAI Ultimate is a next-generation Legal Tech SaaS platform that transforms static contract analysis and legal research into an interactive, multimodal, and vernacular experience.

It acts as an automated legal consultant that can hear, think, and speak to users in multiple Indian languages, breaking down language barriers and complex legal jargon.

🚀 The Vision: From Academic Research to Consumer SaaS

This project is built upon the theoretical foundation of the 2026 academic paper:

"A Reusable Prompting Framework for Applying Large Language Models to Legal Tasks" (Sriram et al., IEEE Access 2026).

While the base paper proves that Structured Prompting (Chain-of-Thought, Role-Based) improves LLM accuracy on legal tasks over standard RAG models, it is inherently limited to text-based, high-literacy environments.

ClauseAI operationalizes this academic research into a consumer-facing product with 4 major innovations:

Multimodal AI Agent: Transitions from "Text-In/Text-Out" to a Real-Time Video Avatar with Speech-to-Text (STT) and Text-to-Speech (TTS).

Hyper-Localization (Vernacular AI): Custom-engineered to support English, Hindi, Tamil, Telugu, Spanish, and French with dynamic video lip-syncing algorithms tuned specifically for the syllable density of Indian languages.

Full-Stack SaaS Architecture: Includes a Gatekeeper authentication system (SQLite), simulated tiered billing (Free vs. Pro), and secure session management.

Persona-Driven Anti-Hallucination: System-level role injection directly into the audio stream, preventing the AI from breaking character or providing illegal advice.

✨ Core Features

🗣️ Interactive AI Legal Consultant: Talk face-to-face with a video avatar that listens to your spoken legal queries and responds in real-time.

🌍 Vernacular Support: Ask questions in Tamil, Telugu, or Hindi. The AI translates, analyzes the law, and responds in your native tongue using culturally accurate neural voices.

🔐 Secure "Gatekeeper" Access: Fully functional Login and Sign-Up system powered by SQLite.

💳 Tiered Subscription Model: Freemium architecture where advanced features (like the AI Avatar and The Vault) are unlocked via a simulated Pro upgrade.

📄 Neural Contract Auditing (Main Console): Deep scan PDFs/documents for hidden risks, missing clauses, and compliance issues via specialized Multi-Agents.

📊 Analytics & Vault: Organize, visualize, and securely store your legal document data.

🛠️ Technology Stack

Frontend: Streamlit, Custom CSS-in-JS, Streamlit-Option-Menu

Backend: Python, SQLite, Asyncio

AI & NLP: * speech_recognition (Google STT API for multi-language input)

edge_tts (Microsoft Edge Neural Voices for high-quality audio output)

Custom universal_llm wrapper (Integration with Gemini/OpenAI for Chain-of-Thought reasoning)

Multi-Agent Orchestration & Pinecone Vector Database (RAG)

Media Handling: Base64 dynamic video injection for 16:9 cinematic avatar rendering.

📂 Project Structure

AI-tool-to-analyze-legalcontracts/
│
├── .env                       # Environment variables (API Keys, Configs)
├── .gitignore                 # Ignored files (venv, __pycache__, .env)
├── LICENSE                    # MIT License
├── README.md                  # Comprehensive project documentation
├── requirements.txt           # Python dependencies for deployment
├── app.py                     # Main Streamlit application entry point
├── config.py                  # Global configuration settings
├── debug_imports.py           # Dependency and import debugging script
├── start.py                   # Alternative application runner
├── test_keys.py               # API key validation script
├── test_pipeline.py           # Core agent pipeline testing script
├── users.db                   # SQLite database for user auth & billing
│
├── .vscode/                   # VS Code workspace settings
│
├── assets/                    # Media and static assets
│   ├── avatar_closed.png      # AI Avatar (Idle state image)
│   ├── avatar_open.png        # AI Avatar (Speaking state image)
│   ├── idle.mp4               # Silent, breathing avatar loop (9:16)
│   └── talking.mp4            # Speaking avatar loop (9:16)
│
├── data/                      # Sample datasets and input files
│   ├── sample.docx
│   ├── sample.pdf
│   └── sample.txt
│
├── demo contracts/            # Test contracts for analysis
│
├── fonts/                     # Custom typography for UI & PDF exports
│
├── graph/                     # Workflow state management logic
│   └── doc_graph.py           # Document processing workflow graph
│
├── multi_agents/              # Specialized LLM Agents
│   ├── compliance.py          # Agent checking regulatory compliance
│   ├── finance.py             # Agent auditing financial clauses
│   ├── legal.py               # Core legal risk analysis agent
│   └── operations.py          # Operational obligations agent
│
├── planner/                   # Task orchestration for multi-agents
│   └── planner.py             # Decomposes queries into agent tasks
│
├── prompts/                   # System instructions and prompt templates
│   ├── compliance.txt
│   ├── finance.txt
│   └── legal.txt
│
├── utils/                     # Helper functions and core modules
│   ├── classify.py            # Document classification utilities
│   ├── db.py                  # Database connection & user management
│   ├── docsloader.py          # Document parsing (PDF, Word, TXT)
│   ├── export_docx.py         # DOCX report generation
│   ├── export_html.py         # HTML export generation
│   ├── export_utils.py        # PDF and general export utilities
│   ├── helpers.py             # General utility functions
│   ├── pdf_inspector.py       # Layout and text extraction from PDFs
│   ├── pinecone_client.py     # Vector Database client for RAG retrieval
│   ├── styles.py              # Custom UI components and CSS injects
│   ├── translator.py          # Multi-language translation logic
│   ├── universal_llm.py       # LLM API routing and invocation
│   └── viz_utils.py           # Data visualization (charts/graphs)
│
└── views/                     # Streamlit UI Page Modules
    ├── ai_consultant.py       # Multimodal Video Avatar logic (Vernacular)
    ├── analytics.py           # Data visualization dashboard
    ├── architecture.py        # System workflow diagrams
    ├── auth.py                # Login & Registration forms
    ├── landing.py             # Public hero page & features overview
    ├── main_console.py        # Contract scanning interface
    ├── oracle.py              # Advanced legal Q&A text chat
    ├── payment.py             # Billing & Subscription upgrade UI
    └── vault.py               # Secure document storage UI


⚙️ Installation & Setup

Follow these steps to run ClauseAI locally on your machine.

1. Clone the Repository

git clone [https://github.com/springboardmentor986/AI-tool-to-analyze-legalcontracts.git](https://github.com/springboardmentor986/AI-tool-to-analyze-legalcontracts.git)
cd AI-tool-to-analyze-legalcontracts


2. Set Up a Virtual Environment

It is highly recommended to isolate dependencies using a virtual environment.

python -m venv venv

# On Windows:
venv\Scripts\activate

# On macOS/Linux:
source venv/bin/activate


3. Install Dependencies

Ensure you have Python 3.9+ installed, then run:

pip install -r requirements.txt


4. Configure Environment Variables

Create a .env file in the root directory and add your API keys:

GEMINI_API_KEY=your_gemini_api_key_here
PINECONE_API_KEY=your_pinecone_api_key_here


5. Configure Assets

Ensure your AI Avatar videos are placed inside the assets/ folder. The app requires:

assets/idle.mp4

assets/talking.mp4

6. Run the Application

streamlit run app.py


(The application will automatically generate the users.db SQLite database upon first launch.)

🎮 How to Use the Platform

Landing Page: You will be greeted by the ClauseAI hero screen. Click Sign Up.

Registration: Create a new account. You will start on the Free tier.

Upgrade to Pro: Navigate to Billing & Plans in the sidebar. Click Upgrade to Pro to unlock the AI Consultant.

Consult the AI: Go to the AI Consultant tab.

Select your preferred language from the dropdown (e.g., Tamil, Telugu, English).

Click Start Talking and speak your legal query into your microphone.

The AI will process your speech, analyze the legal context via Multi-Agent Chain-of-Thought reasoning, and the video avatar will reply with synchronized, translated speech.

📈 Future Roadmap

[ ] Mobile Optimization: Porting the Streamlit frontend to a Flutter-based mobile app for better on-the-go accessibility.

[ ] Local LLM Integration: Implementing secure, offline open-source models (like Llama 3) for highly confidential corporate data without relying on cloud APIs.

[ ] Advanced Agentic Workflows: Expanding the multi_agents framework to autonomously draft responses to opposing counsel using retrieved context from Pinecone.

⚖️ License & Credits

Designed & Developed by: ARULDASS

Version: build v1

License: MIT License

Copyright: © 2026 ClauseAI Inc. All Rights Reserved.

Disclaimer: This tool provides AI-generated legal information and should not be considered a substitute for professional, human legal counsel.
