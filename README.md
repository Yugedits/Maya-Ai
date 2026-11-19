# Maya-Ai
This is my First Ai Chatbot
<br>
Author - Yug

# Maya AI Assistant

Backend (maya-backend/) — Cloudflare Workers

/chat — LLM chat with persistent memory + conversation history (Workers AI, Llama 3.1)

/memory — D1 CRUD for storing user preferences and facts

/stt — Speech-to-text via Whisper (multilingual)

/tts — Text-to-speech via MeloTTS (multilingual, configurable speed/lang)

/tasks — Multi-step task planner (agent mode — LLM generates a JSON plan, stored in D1)

Web dashboard — chat UI + memory viewer at /

Client (maya-client/) — Python

Push-to-talk voice loop: mic → VAD → /stt → /chat → /tts → speaker

Configurable voice profile (speed, pitch, volume, language)

Safe by default (push-to-talk, no continuous listening)

To get it running:

# Backend

cd maya-backend

npm install

npm run db:create    # copy database_id into wrangler.toml

npm run kv:create    # copy namespace id into wrangler.toml

npm run db:migrate

npm run dev          # http://localhost:8787



# Client (separate terminal)

cd maya-client

python -m venv .venv && source .venv/bin/activate

pip install -r requirements.txt

python main.py       # press Space to talk



cd maya-backend

npm install

npm run db:create    # copy database_id into wrangler.toml

npm run kv:create    # copy namespace id into wrangler.toml

npm run db:migrate

npm run dev          # http://localhost:8787



cd maya-client

python -m venv .venv && source .venv/bin/activate

pip install -r requirements.txt

python main.py       # hold Spacebar to speak

Isko is tarah se build kr jo ki Mai isko phone par bhi use kar saku

This project was built with [Lovable](https://lovable.dev).

**Live app**: https://chrono-talk-agent.lovable.app

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/efe6b617-91f1-4bfd-bd88-149050cf218f).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
