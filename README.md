# TDS Project 1 – virtual Teaching Assistant Discourse responder (Intelligent Query Interface)

This project is part of the Tools in Data Science (TDS) course. It builds a semantic search system over markdown lecture notes and Discourse forum posts using OpenAI embeddings and serves a fast API-based query interface.

🔍 Features

* Parses and chunks markdown lecture content and Discourse posts
* Embeds content using OpenAI API
* Stores embeddings and metadata in SQLite
* FastAPI backend to serve semantic search queries
* Web UI hosted via Vercel to allow question-answering
* Full-text search fallback if embedding is unavailable

🚀 Live Demo

Frontend: [https://tds-project-1-snowy.vercel.app/query](https://tds-project-1-snowy.vercel.app/query)
Backend (API): [http://0.0.0.0:8000/query](http://127.0.0.1:8000/query) (local)

🗂️ Project Structure

* Scraper.py: Scraping TDS Discourse posts with content from 1 Jan 2025 - 14 Apr 2025.
* Crawler.py: Scrapping Course content with content for TDS Jan 2025 as on 15 Apr 2025.
* preprocess.py: Preprocesses markdown and Discourse data into chunks and stores embeddings
* app.py: FastAPI app that handles query requests
* downloaded\_threads/: Contains Discourse JSON files
* markdown\_files/: Contains markdown notes
* knowledge\_base.db: SQLite database for chunks and metadata
* .env: Stores OpenAI API key
* requirements.txt: Python dependencies
* vercel.json & frontend/: Frontend client (optional if using hosted)

⚙️ Setup Instructions

1. Clone the repository:

   bash
   git clone [https://github.com/23f1000805/tds-project-1.git](https://github.com/23f1000805/tds-project-1.git)
   cd tds-project-1

2. Install dependencies:

   bash
   conda create -n tds python=3.10
   conda activate tds
   pip install -r requirements.txt

3. Add your OpenAI API key in a .env file:

   .env

   OPENAI\_API\_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

4. Add your markdown files and discourse data:

* Place markdown notes in markdown\_files/
* Place discourse\_posts.json and metadata.json in downloaded\_threads/

5. Run preprocessing:

   bash
   python preprocess.py

6. Start the FastAPI server:

   bash
   python app.py

📦 Deployment

Frontend is deployed using Vercel. Backend runs on FastAPI (can be hosted with Uvicorn/Gunicorn or deployed to platforms like Render).

📝 License

This project is licensed under the MIT License.

🙋 Acknowledgments

* IIT Madras Online BSc Program
* TDS Course Project First
* OpenAI API
* Discourse API
