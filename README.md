<h1>Langchain</h1>
<h2>What is LangChain?</h2>
<p>LangChain is a powerful framework that simplifies how developers use <strong>large language models (LLMs)</strong> like OpenAI's GPT, Anthropic's Claude, or Hugging Face models to build advanced applications. Think of it as a toolbox that helps you connect these AI models with other tools like databases, APIs, or file systems, and design workflows to handle complex tasks.</p>

<p><strong>What LangChain Does</strong></p>
<ul>
    <li><strong>Chains:</strong> Create workflows where AI performs a series of steps to complete a task.</li>
    <li><strong>Memory:</strong> Add memory to your AI so it can "remember" past interactions, useful for conversations.</li>
    <li><strong>Agents:</strong> Teach AI to use tools like calculators, search engines, or APIs.</li>
    <li><strong>Data Handling:</strong> Load and process data from files, APIs, or other sources.</li>
</ul>

<p><strong>Breaking It Down with Examples</strong></p>

<p><strong>1. Chains</strong></p>
<p>LangChain lets you combine multiple tasks into a "chain."</p>
<ul>
    <li><strong>Example:</strong></li>
    <ol>
        <li>Step 1: Use AI to suggest destinations based on preferences.</li>
        <li>Step 2: Fetch hotel recommendations from an API.</li>
        <li>Step 3: Summarize the options in a simple email.</li>
    </ol>
</ul>

<p><strong>2. Memory</strong></p>
<p>LangChain allows the AI to "remember" past interactions in a session. Without memory, the AI forgets what you said earlier.</p>
<ul>
    <li><strong>Example without memory:</strong></li>
    <ul>
        <li>User: "What's my name?"</li>
        <li>AI: "I don't know."</li>
    </ul>
    <li><strong>Example with memory:</strong></li>
    <ul>
        <li>User: "My name is Anand."</li>
        <li>AI: "Got it, Anand!"</li>
        <li>User: "What's my name?"</li>
        <li>AI: "Your name is Anand."</li>
    </ul>
</ul>

<p><strong>3. Agents</strong></p>
<p>Agents are like giving the AI superpowers to use tools. Instead of just answering questions, the AI can:</p>
<ul>
    <li>Look up current weather.</li>
    <li>Perform calculations.</li>
    <li>Search the internet.</li>
</ul>
<p><strong>Example:</strong></p>
<ul>
    <li>Task: "How much is 15% of 250 plus 100?"</li>
    <li>Without tools: The AI might try to calculate but could make errors.</li>
    <li>With a calculator tool: LangChain enables the AI to use a calculator and provide the correct answer: 137.5.</li>
</ul>

<p><strong>4. Data Handling</strong></p>
<p>LangChain makes it easy to load data from various sources like PDFs, Word documents, or databases and process it using AI.</p>
<ul>
    <li><strong>Example:</strong> Imagine you have a PDF with 100 pages of legal terms. You can:</li>
    <ol>
        <li>Use LangChain to load the document.</li>
        <li>Ask questions like, "What is the penalty for late payment?"</li>
        <li>Get the answer without manually reading the document.</li>
    </ol>
</ul>

<p><strong>Real-Life Application</strong></p>
<p><strong>Project:</strong> A Customer Support Chatbot</p>
<ol>
    <li>The chatbot remembers the user’s name and preferences (Memory).</li>
    <li>If a user asks about order status, the AI connects to a database to fetch details (Agents + Tools).</li>
    <li>If the user wants product recommendations, the AI processes their preferences and generates suggestions (Chains).</li>
    <li>All chat history is stored securely for future reference.</li>
</ol>

<p><strong>Why Use LangChain?</strong></p>
<p>Without LangChain, you would need to write a lot of custom code to:</p>
<ul>
    <li>Handle memory.</li>
    <li>Connect the AI model to tools or external data.</li>
    <li>Create workflows for multi-step tasks.</li>
</ul>
<p>LangChain simplifies all of this, letting you focus on building applications instead of reinventing the wheel.</p>

<br>
<br>

<h2>Installation Steps</h2>
<p>To get started with LangChain, follow these steps:</p>

<ol>
    <li>
        <strong>Install Python</strong>
        <ul>
            <li>Make sure you have Python 3.7 or higher installed on your system.</li>
            <li>Check Python version:
                <ul>
                    <li><code>python --version</code></li>
                </ul>
            </li>
            <li>If not installed, download and install Python from <a href="https://www.python.org/downloads/">python.org</a>.</li>
        </ul>
    </li>
    <li>
        <strong>Set Up a Virtual Environment (Optional but Recommended)</strong>
        <ul>
            <li>Create a virtual environment:
                <ul>
                    <li><code>python -m venv langchain_env</code></li>
                </ul>
            </li>
            <li>Activate the virtual environment:
                <ul>
                    <li>On Windows: <code>langchain_env\Scripts\activate</code></li>
                    <li>On macOS/Linux: <code>source langchain_env/bin/activate</code></li>
                </ul>
            </li>
        </ul>
    </li>
    <li>
        <strong>Install LangChain</strong>
        <ul>
            <li>Install the LangChain library using pip:
                <ul>
                    <li><code>pip install langchain</code></li>
                    <li><code>pip install langchain_community</code></li>
                </ul>
            </li>
        </ul>
    </li>
    <li>
        <strong>Install LLM Providers</strong>
        <ul>
            <li>LangChain works with various language models. Install the required library:</li>
            <ul>
                <li>For OpenAI: <code>pip install openai</code></li>
                <li>For Hugging Face Transformers: <code>pip install huggingface_hub</code></li>
            </ul>
        </ul>
    </li>
</ol>

<p><strong>Setup Steps</strong></p>
<p>Once the installation is complete, follow these steps:</p>

<ol>
    <li>
        <strong>Set API Keys</strong>
        <ul>
            <li>If you're using an LLM provider like HuggingFace, set your API key:</li>
            <ul>
                <li>Export the API key in your terminal: <code>export HUGGINGFACEHUB_API_TOKEN="your-api-key"</code></li>
                <li>Or, add it directly in your code:
                    <ul>
                        <li><code>import os</code></li>
                        <li><code>os.environ["HUGGINGFACEHUB_API_TOKEN"] = "your-api-key"</code></li>
                    </ul>
                </li>
            </ul>
        </ul>
    </li>
    <li>
        <strong>Test LangChain Installation</strong>
        <ul>
            <li>Run this simple test:

```python
from langchain.llms import HuggingFaceHub
llm = HuggingFaceHub(repo_id="gpt2", model_kwargs={"temperature": 0.7})
response = llm("What is LangChain?")
print(response)
```
            </li>
            <li>If everything is set up correctly, you’ll get a response from the AI.</li>
        </ul>
    </li>
    <li>
        <strong>Explore Examples</strong>
        <ul>
            <li>Start with basic examples from the <a href="https://langchain.readthedocs.io/en/latest/">LangChain Documentation</a>.</li>
        </ul>
    </li>
</ol>

<p><strong>Common Issues and Troubleshooting</strong></p>
<ul>
    <li><strong>Issue:</strong> Missing Dependencies
        <ul>
            <li>Run: <code>pip install -r requirements.txt</code></li>
        </ul>
    </li>
    <li><strong>Issue:</strong> API Key Errors
        <ul>
            <li>Ensure the correct API key is set and there are no typos.</li>
        </ul>
    </li>
    <li><strong>Issue:</strong> Version Mismatches
        <ul>
            <li>Update LangChain to the latest version: <code>pip install --upgrade langchain</code></li>
        </ul>
    </li>
</ul>
