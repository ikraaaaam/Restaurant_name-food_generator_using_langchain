# Restaurant Name & Food Generator (LangChain)

A simple LLM project that suggests a fancy restaurant name for a given cuisine — and then recommends matching food items for that restaurant. Built with LangChain and OpenAI, with a Streamlit web interface.

## How it works

Pick a cuisine in the sidebar (Indian, Italian, Mexican, Arabic or American) and two chained LLM calls run in sequence:

1. **Name chain** — suggests a fancy restaurant name for that cuisine.
2. **Menu chain** — suggests menu items for the generated restaurant name, returned as a comma-separated list.

The chains are wired together with LangChain's `SequentialChain` (`langchain_helper.py`), using OpenAI with temperature 0.7.

## Run it

```bash
pip install streamlit langchain openai
streamlit run main.py
```

You need an OpenAI API key: put it in `secret_key.py` as `openapi_key` (that file is how `langchain_helper.py` reads the key).

## Files

- `main.py` — Streamlit app: cuisine picker, name + menu display.
- `langchain_helper.py` — the two LangChain chains (name, then menu items).
- `secret_key.py` — your OpenAI API key (keep this file private, do not commit a real key).
