# Attentions.ai Project

This README provides an overview of the development process and core components of the Attentions.ai project, focusing on creating a dynamic trip planner application that generates customized itineraries based on user preferences, location-specific weather, and news updates.

## Project Overview
Due to strict time constraints, I aimed to create a practical, functioning solution by making some key assumptions and prioritizing effective system integration.

### Key Assumptions & Decisions
1. **Groq API for LLM Calls**: Initially, I tested Ollama's "phi" model (1.6 GB) as the smallest local model available. However, results were subpar, leading me to switch to Groq's llama-3.1-70b-versatile model for more accurate responses. 
2. **Prompt Optimization**: While prompt tuning could further improve the LLM output, time limitations prevented extensive optimization.
3. **API Integrations**: I used OpenWeather for location-specific weather data and NewsAPI for recent local news updates, enhancing trip relevance.
4. **Development Environment**: Although I started on VS Code, connectivity issues with Neo4j led me to migrate to Google Colab, where I used tunneling to run the Streamlit app seamlessly.

## Project Structure
I have created a flowchart to illustrate the flow of calls in the application. Please refer to 'Flow_Chart.png' for details.
Here's an outline of the system's operation, including how Langchain and Neo4j interact to produce personalized trip plans:

1. **User Inputs via Streamlit**: The user enters basic trip details like location, budget, and preferred activities.
2. **Data Collection**: The system retrieves weather and news updates based on the selected location.
3. **Memory Integration**: Using Langchain, we fetch message history and relevant data from Neo4j, storing user preferences and relevant context as a connected graph.
4. **LLM Call**: All collected data—user inputs, weather, news, and memory history—is structured into a sophisticated prompt for the LLM call, generating a detailed trip itinerary.

## Technology Stack
- **Neo4j**: Graph database for storing user interaction data, enabling personalized responses.
- **Langchain**: Facilitates connections between data sources and the language model.
- **FastAPI**: Powers efficient API interactions.
- **Groq LLM Model**: Core language model used for trip planning.
- **Ollama (Phi Model)**: Initially considered but found unsuitable due to low response quality.
- **Streamlit**: Frontend interface allowing users to input trip details interactively.

### How to Run
1. **Run the main.ipynb**: Run all the cells in this notebook. Then, follow the tunnel link and enter the provided IP address to launch the Streamlit app

### I've also included a Practice and Exploration file, which contains code related to my learning process and experimentation. Since working with Neo4j and graph databases was new to me, this file documents my approach and steps taken to understand and apply these technologies
