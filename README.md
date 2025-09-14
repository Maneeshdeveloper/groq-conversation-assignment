# groq-conversation-assignment
Assignment on Conversation Management &amp; Classification using Groq API

Overview

This project demonstrates a **conversation management system** and **chat classification** using the **Groq API** (OpenAI-compatible). It allows you to:

* Maintain a running **conversation history**.
* Perform **automatic summarization** to keep the chat concise.
* Extract **structured information** from user chats using a **JSON schema**.

---
 Features

Task 1 — Conversation Management with Summarization

* Stores user and assistant messages in a running history.
* Truncates messages by **number of turns** or **character length**.
* Performs **automatic summarization** every k-th message.
* Example output:

```
After 3 messages (summarized):
[{'role': 'system', 'content': 'Summary: User greeted the assistant, the assistant offered assistance, and the user asked a joke.'}]
```

---

### Task 2 — JSON Schema Classification

* Extracts structured information like **name** and **topic** from chats.
* Uses Groq API's **function-calling / JSON object output**.
* Example input/output:

**Input Chat:**

```
User: Hi, I am Alex.
User: I want to talk about machine learning.
```

**Extracted JSON:**

```json
{"name": "Alex", "topic": "machine learning"}
```

---

## Installation & Setup

1. Clone this repository or download the notebook:

```bash
git clone https://github.com/Maneeshdeveloper/groq-conversation-assignment.git
```

2. Open the notebook in [Google Colab](https://colab.research.google.com).
3. Install dependencies:

```python
!pip install openai -q
```

4. Add your **Groq API Key**:

```python
import os
os.environ["OPENAI_API_KEY"] = "YOUR_GROQ_API_KEY"
```

5. Initialize the client:

```python
from openai import OpenAI

client = OpenAI(
    api_key=os.environ["OPENAI_API_KEY"],
    base_url="https://api.groq.com/openai/v1"
)
```

---

## How to Use

### Interactive Chat

1. Run the notebook cell with the **interactive chat loop**.
2. Type your messages in the input prompt.
3. The assistant responds using Groq API.
4. Summarization triggers automatically when history grows too long.
5. Type `exit` to end the chat.

---

### Structured Information Extraction

1. Provide chat history as input to the extraction function.
2. Groq API returns structured JSON.
3. Example usage:

```python
chat_history = [
    {"role": "user", "content": "Hi, I am Priya."},
    {"role": "user", "content": "Let's talk about space travel."}
]

extracted = extract_info_from_chat(chat_history)
print(extracted)
```

---

## Technologies Used

* Python 3
* Groq API (OpenAI-compatible SDK)
* Google Colab
* JSON Schema validation

---

## Notes

* Conversation summarization and truncation settings can be **customized**.
* Ensure your Groq API key is **valid and active**.
* The notebook demonstrates **both conversation management and classification** with example chats.

