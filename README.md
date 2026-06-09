# CareerCoach — AI-Powered Job Search Assistant

CareerCoach is a full-stack web application built to streamline and organize your entire job search journey. This free, open-source, and self-hosted platform helps job seekers efficiently track applications, manage resumes, and leverage AI to stay competitive — all from a single, intuitive interface running on your own system.

Job searching can be overwhelming, with countless applications to track and deadlines to meet. CareerCoach simplifies the process so you can focus on what matters: landing the right opportunity. It provides every tool you need to stay organized, informed, and proactive from your first application to your final offer.

## Key Features

- **Application Tracker:** Keep a detailed record of all your job applications, including company details, job titles, application dates, and current status.

- **Monitoring Dashboard:** Visualize your job search progress with an interactive dashboard that provides insights into your application activities, success rates, and upcoming tasks.

- **Resume Management:** Store and manage multiple resumes, export them as professionally formatted PDFs, and use them with AI to get reviews and match against job descriptions.

- **PDF Resume Export:** Export any resume as a professionally formatted PDF directly from the resume page. The generated PDF is automatically saved to your Downloads folder and attached to the resume for use with AI job matching and review features.

- **Task & Activity Management:** Manage tasks and track activities linked to your applications, complete with time tracking.

- **AI Assistant:** Leverage multi-provider AI to improve your resumes and match with jobs. Get personalized job matching with scoring to identify the best opportunities tailored to your profile.

## Free to Use and Self-Hosted

CareerCoach is completely free and open source. It gives everyone access to a powerful job search management tool at no cost. Designed to be self-hosted, it puts you in full control of your data — no third-party accounts, no subscriptions, no tracking. Using Docker, you can spin up CareerCoach on your own machine or server in minutes.

## Quick Start

Make sure Docker is installed and running, then:

```sh
git clone https://github.com/Gsync/jobsync.git
cd jobsync
docker compose up
```

Open `http://localhost:3737` and create your account. That's it!

API keys for AI providers can be configured in **Settings** after signing in.

### Configuration (Optional)

Environment variables can be set in `docker-compose.yml`:

| Variable | Description |
|---|---|
| `TZ` | Your timezone (e.g. `America/Montreal`). **Set this on remote servers** to avoid activity time shifts. |
| `AUTH_SECRET` | Auto-generated if not set. To set manually: `openssl rand -base64 32` |

### Updating

From the project directory, run the deploy script to pull the latest changes and rebuild:

```sh
curl -fsSL https://raw.githubusercontent.com/Gsync/jobsync/main/deploy.sh | sudo bash -s
```

> **Note:** If you are updating in a homelab environment, edit `NEXTAUTH_URL` in your `.env` file to use your server IP address instead of `localhost`. See `.env.example` for the expected format.

## Supported AI Model Providers

API keys for all cloud providers can be configured in **Settings > AI Settings** after signing in. Ollama is selected as the default provider.

> **Note:** Selected models must support **structured output** for AI features to work correctly.

**Ollama (Local)**

Works with Ollama to run AI models locally on your machine. No API key required — runs entirely on your hardware. Make sure Ollama is installed and running on the same system. Recommended: increase the Ollama context length from the default 4k for better results.

**OpenAI**

Add your API key in **Settings > AI Settings**, select OpenAI as the provider, and choose your preferred model. Available models are fetched dynamically from the OpenAI API.

**DeepSeek**

Add your API key in **Settings > AI Settings** and select DeepSeek as the provider.

**Google Gemini**

Add your API key in **Settings > AI Settings** and select Gemini as the provider.

**OpenRouter**

Access a wide range of AI models from multiple providers through a single API. Get your API key at [openrouter.ai/keys](https://openrouter.ai/keys), add it in **Settings > AI Settings**, and select OpenRouter as the provider.

## Contributing

Contributions are welcome! Please read the Contributing Guidelines to get started. This project follows a Code of Conduct — by participating, you agree to uphold its standards.

### Credits

**Developed by Ali El-Sayed Ali**

Built with: React, Next.js, Shadcn UI, Prisma, Tailwind CSS, Tiptap, Nivo, SQLite, Vercel AI SDK, Ollama.

## Support the Project

If CareerCoach has been helpful in your job search, consider giving it a star on GitHub! It helps others discover the project and motivates continued development.

Every star means a lot — thank you for your support!

---

*CareerCoach — Built by **Ali El-Sayed Ali***
