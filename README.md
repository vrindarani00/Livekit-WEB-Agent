# LiveKit-Web-Agent

A lightweight Python script to launch a LiveKit voice assistant that listens, transcribes, searches the web, and responds via text-to-speech.

## Features

* **Real-time audio**: Joins a LiveKit room and captures audio from participants.
* **Speech-to-Text**: Transcribes user speech using OpenAI’s RealtimeModel.
* **Web Search**: Fetches live search results via DuckDuckGo.
* **Text-to-Speech**: Responds with audio using OpenAI’s TTS.
* **Extensible**: Easily integrate additional tools or plugins via LiveKit’s agent framework.

## Prerequisites

* Python 3.8 or higher
* A LiveKit server URL and credentials.
* An OpenAI API key with access to RealtimeModel and TTS.

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/livekit-web-agent.git
   cd livekit-web-agent
   ```

2. Create and activate a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate    # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Configuration

1. Copy or create a `.env` file in the project root:

   ```dotenv
   LIVEKIT_URL=<your_livekit_server_url>
   LIVEKIT_API_KEY=<your_livekit_api_key>
   LIVEKIT_API_SECRET=<your_livekit_api_secret>
   OPENAI_API_KEY=<your_openai_api_key>
   ```

2. Ensure your OpenAI key has permission for RealtimeModel (STT) and TTS.

## Usage

Run the agent in the LiveKit playground:

```bash
python main.py start
```

### Example

1. Start your LiveKit server or use the hosted playground.
2. Invite the bot to a room.
3. Speak in the room; the bot will transcribe, search the web, and respond with spoken answers.

## Customization

* Modify or extend the `search_web` function in `main.py` to integrate other search providers.
* Swap out the TTS engine by replacing `openai.TTS()` with another supported service (e.g., ElevenLabs).
* Add new tools by decorating functions with `@function_tool` and registering them in the agent session.

## Dependencies

See `requirements.txt` for the full list:

```
livekit-agents[openai]>=1.0
python-dotenv>=1.0
duckduckgo-search>=8.0
```
