# OpenAgencyAI.dev

AI-Powered Agency Assistant. Provides a clean, responsive chat interface with streaming responses.

## Features

- 💬 Simple and responsive chat interface
- ⚡ Server-Sent Events (SSE) for streaming responses
- 🧠 Powered by AI LLMs
- 🛠️ Built with TypeScript
- 📱 Mobile-friendly design
- 🔄 Maintains chat history on the client
- 🔎 Built-in observability logging

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or newer)

### Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/alex-agency/openagencyai-chat.git
   cd openagencyai-chat
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Generate type definitions:
   ```bash
   npm run cf-typegen
   ```

### Development

Start a local development server:

```bash
npm run dev
```

This will start a local server at http://localhost:8787.

### Deployment

Deploy to compatible edge platforms:

```bash
npm run deploy
```

### Monitor

View real-time logs:

```bash
npm wrangler tail
```

## Project Structure

```
/
├── public/             # Static assets
│   ├── index.html      # Chat UI HTML
│   └── chat.js         # Chat UI frontend script
├── src/
│   ├── index.ts        # Main Worker entry point
│   └── types.ts        # TypeScript type definitions
├── test/               # Test files
├── wrangler.jsonc      # Worker configuration
├── tsconfig.json       # TypeScript configuration
└── README.md           # This documentation
```

## How It Works

### Backend

The backend is built with edge workers and uses AI services to generate responses. The main components are:

1. **API Endpoint** (`/api/chat`): Accepts POST requests with chat messages and streams responses
2. **Streaming**: Uses Server-Sent Events (SSE) for real-time streaming of AI responses
3. **Workers AI Binding**: Connects to AI service via the Workers AI binding

### Frontend

The frontend is a simple HTML/CSS/JavaScript application that:

1. Presents a chat interface
2. Sends user messages to the API
3. Processes streaming responses in real-time
4. Maintains chat history on the client side

## Customization

### Changing the Model

To use a different AI model, update the `MODEL_ID` constant in `src/index.ts`.

### Modifying the System Prompt

The default system prompt can be changed by updating the `SYSTEM_PROMPT` constant in `src/index.ts`.

### Styling

The UI styling is contained in the `<style>` section of `public/index.html`. You can modify the CSS variables at the top to quickly change the color scheme.

## License

MIT © 2026
