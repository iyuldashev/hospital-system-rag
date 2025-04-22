# 🏥Hospital Sytem RAG Chatbot

Welcome to the **Hospital Retrieval-Augmented Generation (RAG) Chatbot**! This innovative project combines a **Neo4j graph database**, **OpenAI's advanced LLMs**, and a **user-friendly Streamlit interface** to deliver intelligent, data-driven insights for healthcare queries. Whether you're exploring hospital operations, physician specialties, or patient visit trends, this chatbot provides contextually accurate responses with ease.

<img src="https://github.com/user-attachments/assets/ffe2c11c-6907-42d2-b817-9ece2fa18432" alt="Project Architecture" width="700"/>

## 🌟 Why This Project Stands Out

- **Graph-Powered Insights**: Leverages **Neo4j AuraDB** to model complex relationships between hospitals, physicians, patients, and more, enabling powerful and efficient queries.
- **AI-Driven Conversations**: Combines **OpenAI GPT-3.5 Turbo** models with retrieval-augmented generation (RAG) for nuanced, context-aware responses.
- **Interactive Exploration**: A **Streamlit** web app offers a user-friendly interface to query data and visualize results.
- **Scalable & Reproducible**: Deployed with **Docker Compose** for seamless setup and consistent performance across environments.
- **Real-World Applications**: Built on realistic healthcare datasets to simulate practical use cases in hospital administration, patient care, and research.

## 📦 Tech Stack

- **OpenAI GPT-3.5 Turbo**: Powers intelligent, conversational responses.
- **Neo4j AuraDB**: Scalable graph database for Checked and updated linksefficient querying of interconnected data.
- **FastAPI**: Modern, high-performance web API framework for the chatbot backend.
- **Streamlit**: Intuitive web interface for interactive data exploration.
- **Docker & Docker Compose**: Containerized deployment for easy setup and scalability.
## 🚀 Setup

### Prerequisites
- **OpenAI API Key**: Create one [here](https://platform.openai.com/api-keys).
- **Neo4j AuraDB Instance**: Set up a free instance [here](https://neo4j.com/cloud/platform/aura-graph-database/).
- **Docker Compose**: Install it by following [these instructions](https://docs.docker.com/compose/install/).

### Setup Instructions

1. **Create a `.env` File**  
   In the root directory, create a `.env` file and add the following environment variables:

   ```env
   OPENAI_API_KEY=<YOUR_OPENAI_API_KEY>

   NEO4J_URI=<YOUR_NEO4J_URI>
   NEO4J_USERNAME=<YOUR_NEO4J_USERNAME>
   NEO4J_PASSWORD=<YOUR_NEO4J_PASSWORD>

   HOSPITALS_CSV_PATH=https://raw.githubusercontent.com/hfhoffman1144/langchain_neo4j_rag_app/main/data/hospitals.csv
   PAYERS_CSV_PATH=https://raw.githubusercontent.com/hfhoffman1144/langchain_neo4j_rag_app/main/data/payers.csv
   PHYSICIANS_CSV_PATH=https://raw.githubusercontent.com/hfhoffman1144/langchain_neo4j_rag_app/main/data/physicians.csv
   PATIENTS_CSV_PATH=https://raw.githubusercontent.com/hfhoffman1144/langchain_neo4j_rag_app/main/data/patients.csv
   VISITS_CSV_PATH=https://raw.githubusercontent.com/hfhoffman1144/langchain_neo4j_rag_app/main/data/visits.csv
   REVIEWS_CSV_PATH=https://raw.githubusercontent.com/hfhoffman1144/langchain_neo4j_rag_app/main/data/reviews.csv

   HOSPITAL_AGENT_MODEL=gpt-3.5-turbo-1106
   HOSPITAL_CYPHER_MODEL=gpt-3.5-turbo-1106
   HOSPITAL_QA_MODEL=gpt-3.5-turbo-0125

   CHATBOT_URL=http://host.docker.internal:8000/hospital-rag-agent
   ```

2. **Run the Project**  
   Once the `.env` file is configured and prerequisites are met, open a terminal in the project directory and run:

   ```bash
   docker-compose up --build
   ```

3. **Access the Application**  
   After the containers are built, you can access:
   - **Chatbot API**: `http://localhost:8000/docs` for API documentation and testing.
   - **Streamlit App**: `http://localhost:8501` for an interactive web interface.
