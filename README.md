# Gradio Multi-Model Chat and Brochure Generator

This project demonstrates building user interfaces with Gradio that connect to multiple LLM providers (OpenAI GPT-4o-mini, Anthropic Claude, and Google PaLM). It includes streaming chat responses and a use case generating company brochures from website content.

---

## Features

- Load API keys from `.env` file for OpenAI, Anthropic, and Google
- Simple functions to interact with GPT and Claude models with streaming support
- Gradio UI for text input and markdown output
- Switch between GPT and Claude models in the same interface
- Generate company brochures by scraping and analyzing landing pages
- Dark mode example for Gradio interface
- Clear separation of UI and logic

---

## Setup

1. Create a `.env` file with the following keys:
- OPENAI_API_KEY=your_openai_key
- ANTHROPIC_API_KEY=your_anthropic_key
- GOOGLE_API_KEY=your_google_key


2. Install dependencies:
```bash 
pip install gradio openai anthropic google-generativeai python-dotenv requests beautifulsoup4
```

3. Run the script.

---

## Code Overview

- Environment variables are loaded with `dotenv`.
- API clients initialized for OpenAI, Anthropic, Google.
- `message_gpt(prompt)`: sends a prompt to GPT-4o-mini, returns completion.
- `stream_gpt(prompt)` and `stream_claude(prompt)`: generator functions that stream tokens from models.
- `stream_model(prompt, model)`: selects GPT or Claude stream based on user choice.
- `Website` class: scrapes webpage title and visible text, cleans scripts/styles/images.
- `stream_brochure(company_name, url, model)`: generates a company brochure from the landing page content.
- Multiple Gradio interfaces demonstrate:
- Simple shout function transforming text to uppercase
- Chat with GPT and Claude
- Streaming chat responses with model selection
- Brochure generation UI

---

## Notes

- `flagging_mode="never"` disables Gradio flagging UI.
- Use `share=True` with caution on corporate networks.
- Dark mode is enabled via custom JS in one interface.
- Streaming responses update the output progressively.
- This is a demonstration template and may require API key and model updates.


---

## Example usage

Launch the script and open the Gradio web UI. Enter your text or company info, select the model, and interact with the assistant or generate brochures.

