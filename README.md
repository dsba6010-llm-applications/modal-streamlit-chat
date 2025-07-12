# modal-streamlit-chat

First, create a `.streamlit/secrets.toml` file such that:

```toml
# fill in <your value>
API_KEY="<your key>"
BASE_URL="https://<your url>" # OpenAI compatible w/o /v1
MODEL_NAME="<your model>"
ARIZE_API_KEY="<your key>"
ARIZE_PROJECT_NAME="<your project name>"
SPACE_ID="<your key>"
```

or to run run locally fill out `.env` following `.env-example` format.

# On local machine

```bash
$ python3.10 -m venv venv
$ source venv/bin/activate
$ python -m pip install -r requirements.txt
$ python -m streamlit run app.py
```

# To run on modal:

Make sure you have a [Modal account](https://modal.com/). 

First, sign in:

```bash
# sign in
$ python -m modal setup
```

Then set Modal secrets which is your LLM serving endpoint (not including `v1/`). This includes Arize tokens via OpenTelemetry.

You can run a temporary "dev" environment to test:

```bash
# to test
$ modal serve modal/serve_streamlit.py
```

Or deploy it as a new app to modal:

```bash
# when ready to deploy
$ modal deploy modal/serve_streamlit.py
```
