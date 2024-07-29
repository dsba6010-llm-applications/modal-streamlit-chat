# modal-streamlit-chat

First, create a `.streamlit/secrets.toml` file such that:

```toml
# fill in <your value>
DSBA_LLAMA3_KEY="<your key>"
MODAL_BASE_URL="https://<your url>--vllm-openai-compatible-serve.modal.run"
```

# To run locally:

```bash
$ python3.11 -m venv venv
$ source venv/bin/activate
$ python -m pip install -r requirements.txt
$ python -m streamlit run app.py
```

# To run on modal:

```bash
# sign in
$ modal setup
# to test
$ modal serve modal/serve_streamlit.py

# when ready to deploy
$ modal deploy modal/serve_streamlit.py
```

TODO: Switch to modal secrets