# Project Scope: Current Functionality in TalkFlow

## ✅ Description

This project is a frontend-only chatbot interface built with React, TypeScript, Tailwind CSS (via Shadcn UI), and Vite. It allows a user to interact with an external workflow automation system (N8N) via a single webhook endpoint. The application emulates a real-time chat experience using optimistic UI updates, with no backend or real-time communication.

## ✨ Core Features Implemented

- **Single User Chat UI:**
  - Simulates a conversation between one user and a single assistant bot.
  - Messages are displayed in a chat-style format.
  - Markdown rendering for bot responses (code blocks, math via KaTeX, syntax highlighting).
  - File/image upload support with preview and transmission to webhook.

- **Webhook Integration (N8N):**
  - All user messages are sent to a configured N8N webhook via HTTP POST.
  - The bot's response is retrieved from N8N and displayed in the UI.
  - Basic authentication for the webhook is supported via environment variables.

- **Session Management (Local Only):**
  - Users can create and switch between multiple chat sessions.
  - Session state and message history are stored in browser `localStorage`.
  - Sessions persist across reloads (locally), but not across devices.

- **Component-Based UI:**
  - Fully responsive UI using Tailwind CSS and Shadcn components.
  - Dark mode support.
  - Message typing indicator while waiting for N8N response.
  - Toast notifications for errors and status updates.

- **Developer Playground:**
  - Dedicated route (e.g. `/playground`) for testing code or bot outputs.

## ⚠️ Limitations

- No authentication or user accounts – all usage is anonymous and stored locally.
- Only a single N8N webhook is supported.
- No support for multiple bots or commands (e.g., `@bot`).
- No real-time or multi-user functionality (no WebSocket, no server).
- Security limitations due to exposing webhook credentials in the frontend.

## 📦 Tech Stack

- **Frontend:** React + TypeScript + Tailwind CSS + Vite
- **UI Library:** Shadcn UI (based on Radix UI)
- **Data Persistence:** Browser `localStorage`
- **Bot Integration:** HTTP POST to N8N Webhook
- **Markdown Parser:** `react-markdown`, `remark-gfm`, `rehype-highlight`, `rehype-katex`
- **Image Handling:** File upload (Base64), inline preview

## 📝 Environment Variables Used

- `VITE_N8N_WEBHOOK_URL`
- `VITE_N8N_WEBHOOK_USERNAME`
- `VITE_N8N_WEBHOOK_PASSWORD`
