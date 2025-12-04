# 🧑‍💻 **CodeMentor** - Personalized Programming Learning Chatbot

A specialized, self-adaptive AI chatbot built on a modern Laravel foundation, designed to be a personalized mentor for programming education. It leverages **Consistency-based Self-adaptive Prompting (COSP)** and an **Agentic AI architecture** to provide highly effective and context-aware guidance.

## 🚀 Introduction

**CodeMentor** uses the `ai-chat` starter kit as its foundation to create a robust, real-time learning environment. Moving beyond generic Q\&A, this project focuses on research and development in advanced AI prompting and agent systems, specifically:

  * **Consistency-based Self-adaptive Prompting (COSP):** Implementing dynamic, self-optimizing prompts that ensure teaching consistency and adapt the learning material based on the user's current progress and comprehension.
  * **Agentic AI Approach:** Structuring the chatbot as a multi-component agent system (e.g., a Planner Agent, a Tutor Agent, a Code Review Agent) to handle complex, multi-step programming tasks and provide structured, goal-oriented learning paths.

The application is built with Laravel, featuring real-time streaming responses using Prism, Inertia.js, Vue.js, and TailwindCSS.

## ✨ Key Enhancements & Features

The core features of the base project are enhanced with a focus on educational and agentic capabilities:

  * **Self-Adaptive Learning (COSP):** Real-time adjustment of teaching style, complexity, and examples based on student performance.
  * **Agentic Workflow:** Structured, multi-agent interactions to simulate a dedicated programming mentor (e.g., goal setting, code generation, error correction, topic review).
  * **Real-time AI Responses**: Stream AI responses as they're generated for immediate feedback.
  * **Reasoning and Planning Support**: Leveraging models with strong reasoning for complex programming problem-solving.
  * **Multiple AI Providers**: Support for various models (OpenAI, Anthropic, Google Gemini, etc.) to test performance across different agent roles.
  * **Authentication & User Management**: Built-in system to track individual learning progress.
  * **Appearance & Theming**: Light/dark mode and customizable theming for a comfortable coding environment.
  * **Chat Sharing**: Share successful code snippets or learning sessions.

## 🛠️ Tech Stack

  * **Backend**: Laravel 12.x, Prism PHP SDK, **Custom Agentic Logic**
  * **Frontend**: Vue.js 3, Inertia.js 2.x
  * **Styling**: TailwindCSS 4.x, Shadcn components
  * **Database**: SQLite (configurable to MySQL/PostgreSQL)
  * **Authentication**: Laravel Sanctum
  * **Real-time**: Server-Sent Events (SSE)

-----

## Prerequisites & Installation

The prerequisites and installation steps remain the same as the base `ai-chat` project.

### Prerequisites

  * **PHP 8.4** with extensions: `curl`, `dom`, `fileinfo`, `filter`, `hash`, `mbstring`, `openssl`, `pcre`, `pdo`, `session`, `tokenizer`, `xml`
  * **Composer 2.5.5**
  * **Node.js 25.2.1** and npm/bun
  * **SQLite** (or MySQL/PostgreSQL if preferred)

### Installation

Use the Laravel installer:

```bash
laravel new --using=pushpak1300/ai-chat codementor-ai
cd codementor-ai
```

Or using Composer:

```bash
composer create-project pushpak1300/ai-chat codementor-ai
cd codementor-ai
```

After installation:

```bash
# Install frontend dependencies
npm install

# Generate application key (if not done automatically)
php artisan key:generate

# Create database file (for SQLite)
touch database/database.sqlite

# Run migrations
php artisan migrate

# Start the development server
composer run dev
```

-----

## ⚙️ Configuration

### Environment Setup

```bash
cp .env.example .env
```

Ensure you configure your AI provider keys in the `.env` file.

### Agentic & COSP Configuration

Development will involve modifying the core prompt and message handling logic, typically within:

  * **`app/Services/ChatService.php`**: To implement COSP logic and prompt manipulation.
  * **`app/Http/Controllers/ChatController.php`**: To manage the multi-step agent workflow and state.

### AI Provider and Model Configuration

Focus on selecting models that support advanced reasoning, context window size, and function calling (for future tool-use agent enhancements).

AI models are defined in the `app/Enums/ModelName.php` file.

#### Adding New Models

Follow the base steps to add new models, focusing on those suitable for complex tutoring:

1.  Add the Model Case: `case NEW_MODEL = 'provider-model-name';`
2.  Implement Required Methods (`getName()`, `getDescription()`, `getProvider()`).

-----

## 🗺️ Roadmap: **Agentic & COSP Development**

The primary focus of this project is the following advanced AI capabilities:

  * **Full COSP Implementation**: Integrating feedback loops and state management to ensure prompt consistency and dynamic adaptation.
  * **Agentic System Development**: Implementing distinct AI roles (e.g., **Planner Agent**, **Tutor Agent**, **Evaluator Agent**) that collaborate to guide the user's learning.
  * **Tool Call Support**: Enabling agents to use external tools (e.g., a simulated code interpreter/sandbox) for practical coding exercises.
  * **Multimodal Learning**: Future support for processing images (e.g., diagrams, error screenshots) as part of the learning context.
  * **Code Review & Feedback**: A dedicated agent for analyzing user-written code and providing in-depth, personalized critiques.

-----

## Security, Troubleshooting, and Contributing

The sections for **Deployment**, **Security**, **Troubleshooting**, and **Contributing** remain largely as per the original project. Contributions focused on agentic architectures, COSP, and programming education are highly welcome\!

## License

This project is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

Built with ❤️ using [Laravel](https://laravel.com), [Prism](https://prismphp.com), and [Inertia.js](https://inertiajs.com)