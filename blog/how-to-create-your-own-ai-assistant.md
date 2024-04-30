---
layout: essay
type: blog
title: "How to create your own AI assistant?"
# All dates must be YYYY-MM-DD format!
date: 2024-04-30
published: true
labels:
  - AI
  - Chat Bot
summary: "100% free and accessible without internet, except for model downloads."
---

<img width="200px" class="rounded float-start pe-4" src="../img/ai-assistant/cortana.jpg">

## Setting Up Local Server and Python AI-Assistant

Running on a 16GB RAM PC

### Prerequisites

- [**LM-Studio**](https://lmstudio.ai): For downloading models and running the HTTP server.
- **OpenAI Python Module**: For communication with the HTTP server and the model.

### Installation Steps

1. Install LM Studio.
2. Download any `Llama` model.
3. Go to the Local Server tab in LM Studio, select your model from the top, and start the local server. In the examples, choose the AI-Assistant (Python) option.
4. Install OpenAi python module:  `python3 -m pip install openai`
5. Open your text editor or any IDE and paste the following example code:

```python
# Chat with an intelligent assistant in your terminal
from openai import OpenAI

# Point to the local server
client = OpenAI(base_url="http://localhost:1234/v1", api_key="lm-studio")

history = [
    {"role": "system", "content": "You are an intelligent assistant. You always provide well-reasoned answers that are both correct and helpful."},
    {"role": "user", "content": "Hello, introduce yourself to someone opening this program for the first time. Be concise."},
]

while True:
    completion = client.chat.completions.create(
        model="LM Studio Community/Meta-Llama-3-8B-Instruct-GGUF",
        messages=history,
        temperature=0.7,
        stream=True,
    )

    new_message = {"role": "assistant", "content": ""}
    
    for chunk in completion:
        if chunk.choices[0].delta.content:
            print(chunk.choices[0].delta.content, end="", flush=True)
            new_message["content"] += chunk.choices[0].delta.content

    history.append(new_message)
    
    # Uncomment to see chat history
    # import json
    # gray_color = "\033[90m"
    # reset_color = "\033[0m"
    # print(f"{gray_color}\n{'-'*20} History dump {'-'*20}\n")
    # print(json.dumps(history, indent=2))
    # print(f"\n{'-'*55}\n{reset_color}")

    print()
    history.append({"role": "user", "content": input("> ")})
```

### Running the Code

Execute the Python code to start the AI-assistant:

```bash
python3 main.py
```

### Example Output

Upon running the code, you'll receive an initial prompt from the assistant:

```bash
Hi there! I'm LLaMA, a large language model trained by a team of researchers at Meta AI. I'm here to help you with any questions or tasks you may have. I can provide information on a wide range of topics, from science and history to entertainment and culture. I can also assist with language-related tasks like writing and proofreading. Feel free to ask me anything!
>
```

Now, you can interact with the assistant by providing prompts, and it will respond accordingly.
