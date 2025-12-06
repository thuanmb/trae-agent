1. Install Python 3.12+
2. Install `uv`:

```
pip install uv
```

3. Clone the repository

```
git clone https://github.com/bytedance/trae-agent.git
cd trae-agent
```

4. Create a virtual environment and install dependencies using uv. Note: --all-extras installs all optional dependencies, including LLM providers.

```
uv sync --all-extras
```

5. Activate the new virtual environment

```
source .venv/bin/activate
```

6. Configuration

```
cp trae_config.yaml.example trae_config.yaml
```

7. Running ollama cloud model:

```
ollama run qwen3-coder:480b-cloud
```

Notes:

-  Authentication
   For direct access to ollama.com’s API, first create an API key.
   Then, set the OLLAMA_API_KEY environment variable to your API key.

```
export OLLAMA_API_KEY=your_api_key
```

-  Listing models
   For models available directly via Ollama’s API, models can be listed via:

```
curl https://ollama.com/api/tags
```

8. Testing

```
trae-cli run "Create a Python script that calculates the Fibonacci sequence" --docker-image python:3.12
```
