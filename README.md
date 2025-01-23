
Multi-Agent Conversational AI Customer Assistant Platform with RAG, Vector DB (Astra DB), Streamlit
# Langflow Project

Welcome to the **Langflow** project! 🚀 This repository showcases a **Retrieval-Augmented Generation (RAG)** system built to handle complex customer queries by leveraging **long PDF documents** and a **large database** containing order and product details. The system efficiently answers user queries by routing them through a well-structured agent-based architecture.

---

## 🧩 Project Overview

The Langflow system is designed to simplify customer support interactions by handling a wide variety of queries through a **chat input interface**. It can answer questions that require digging through lengthy PDFs or provide specific information from the order database.

### Key Features:
- 📄 **Document Querying**: Extract information from long PDFs like terms and conditions, cancellation policies, and refund conditions.
- 📦 **Order and Product Details**: Retrieve specific details about orders or products stored in the database.
- 🔄 **Agent-Based Workflow**: Use a **Manager Agent** to route queries to specialized sub-agents for efficient handling.

---

## 📚 Data Storage

The system leverages a **Vector Database** and a **structured database** to store and retrieve data efficiently:

1. **PDF Documents**: Stored in a **Vector Database** using **Astra DB**, allowing fast semantic search and retrieval of relevant sections.
2. **Order and Product Data**: Stored in structured collections within the database from **CSV files** for quick and reliable querying.

---

## 🎙️ Agent-Based Workflow

The system uses a **Manager Agent** to route queries to the appropriate sub-agent based on the type of question asked by the user.

### Manager Agent
The **Manager Agent** acts as a decision-maker, analyzing the user query and routing it to the relevant sub-agent:

- 🗄️ **Policy Agent**: 
  - Queries the **Vector Database** to retrieve relevant sections from the stored PDFs.
  - Useful for answering questions related to terms and conditions, cancellation policies, refund conditions, etc.

- 📦 **Order Info Agent**:
  - Handles queries related to order details and product information.
  - Queries two collections in the structured database:
    - **Order Collection**: Contains detailed order-related information.
    - **Product Collection**: Contains product details and specifications.

---

## 📝 Response Handling

Once the appropriate sub-agent generates a response, the **Manager Agent** compiles the answer and sends it back to the **Chat Output** interface to complete the query resolution.

### Query Resolution Flow:
1. **User Input**: User asks a question via the chat interface.
2. **Manager Agent**: Routes the query to the relevant sub-agent.
3. **Policy Agent / Order Info Agent**: Retrieves the relevant information from the database.
4. **Manager Agent**: Compiles the final response.
5. **Chat Output**: Displays the answer to the user.


---

## 💻 Technologies Used
- **Python**
- **Langchain**
- **Astra DB** (Vector Database)
- **CSV** (Structured Data Storage)
- **FastAPI** (for building the chat interface)
- **Streamlit** (for front-end interface)

---

## 🚀 Getting Started
### Prerequisites
- Python 3.8+
- Astra DB account
- Required libraries in `requirements.txt`

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/langflow.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the backend application:
   ```bash
   python app.py
   ```
4. Run the front-end interface using Streamlit:
   ```bash
   streamlit run frontend/streamlit_app.py
   ```

---

## 🤖 Usage
1. Start the chat interface.
2. Ask queries such as:
   - "What are the refund conditions?"
   - "What's the status of my order #1234?"
3. The system will automatically route your query to the correct agent and provide a detailed response.

---

## 🛠 Future Improvements
- Integrate more agents to handle broader queries.
- Add support for additional data sources (e.g., JSON, SQL).
- Improve response accuracy with advanced NLP techniques.

---

## 📧 Contact
For any queries or suggestions, feel free to reach out!

Happy querying! 😊

