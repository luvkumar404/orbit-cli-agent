# Orbit CLI AI Agent

Orbit CLI is a command-line AI assistant with authentication, interactive chat modes, and tool-enabled workflows.

This repository currently contains:
- `server` - Node.js backend and CLI implementation
- `client` - frontend app

## Features

- Device-flow login and token persistence
- `orbit` CLI binary powered by Commander
- Interactive AI experience with:
  - Chat mode
  - Tool-calling mode
  - Agentic mode (in progress)

## Tech Stack

- Runtime: Node.js (ES Modules)
- CLI Framework: Commander
- AI SDK: Vercel AI SDK (`ai`) + Google provider (`@ai-sdk/google`)
- Database ORM: Prisma
- Database: PostgreSQL
- Auth: Better Auth (Device Authorization Flow)
- CLI UI/UX: `@clack/prompts`, `chalk`, `boxen`, `figlet`, `yocto-spinner`

## Prerequisites

- Node.js 18+ (recommended: latest LTS)
- npm
- Running auth/backend services required by the CLI

## Setup

1. Clone the repository.
2. Install dependencies for the CLI:

```bash
cd server
npm install
```

3. Copy environment variables:

```bash
cp .env.example .env
```

4. Fill in your values in `.env`.

## Run the CLI

From the `server` directory:

```bash
npm run cli
```

This starts the `orbit` command from `src/cli/main.js`.

## CLI Commands

- `orbit login` - authenticate using device flow
- `orbit logout` - clear local credentials
- `orbit whoami` - print current authenticated user
- `orbit wakeup` - launch interactive AI mode selector

## Typical Workflow

```bash
cd server
npm run cli -- login
npm run cli -- whoami
npm run cli -- wakeup
```

## Uses

- Build a personal terminal AI assistant for daily Q&A.
- Run authenticated AI chats tied to user sessions.
- Experiment with tool-calling AI workflows from the terminal.
- Generate starter applications using Agentic mode.
- Learn how to combine CLI UX + auth + LLMs in one project.

## Project Structure

```text
orbital-cli-dev/
  client/
  server/
    src/cli/main.js
    src/cli/commands/
    src/cli/chat/
```

## Notes

- Tokens are stored locally under `~/.better-auth/token.json`.
- Make sure your auth server is reachable before running `login`.
- Environment variables reference: `server/.env.example`.

## License

ISC 

## Author
Love Kumar Chaudhary
