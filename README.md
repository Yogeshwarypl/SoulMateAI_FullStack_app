# SoulMateAI

This is a NextJS starter in Firebase Studio.

To get started, take a look at src/app/page.tsx.


# SoulMateAI - Your Empathetic AI Companion

SoulMateAI is a Next.js web application designed to be an empathetic AI companion. It provides a supportive space for users to express their feelings and receive understanding responses, leveraging the power of generative AI. The application features both text-based chat and voice interaction capabilities.

## Core Features:

*   **Empathetic Chat:** AI-driven empathetic conversation tool that provides supportive responses.
*   **Voice Interaction:** Voice-to-text and text-to-voice capabilities for natural interaction.
*   **Sentiment Analysis:** Emotion detection to identify and respond appropriately to the user's emotional state through textual analysis.
*   **Uplifting Content:** Optional integration of inspirational quotes or affirmations powered by an LLM.
*   **User-Friendly Interface:** Simple and intuitive chat interface built with ShadCN UI and Tailwind CSS.
*   **Privacy Aware:** Conversations are designed to be ephemeral; no chat logs are stored by the application. (Note: Interactions with third-party AI services are subject to their terms).
*   **Demo Authentication:** Simple login system for demonstration purposes.

## Tech Stack:

*   **Frontend Framework:** [Next.js](https://nextjs.org/) (v15+ with App Router)
*   **UI Library:** [React](https://react.dev/)
*   **UI Components:** [ShadCN UI](https://ui.shadcn.com/)
*   **Styling:** [Tailwind CSS](https://tailwindcss.com/)
*   **AI Integration:** [Genkit (by Google)](https://firebase.google.com/docs/genkit)
    *   **LLM Provider:** Google Gemini (e.g., `gemini-2.0-flash`)
*   **Programming Language:** [TypeScript](https://www.typescriptlang.org/)
*   **Speech Recognition & Synthesis:** Browser's Web Speech API
*   **Icons:** [Lucide React](https://lucide.dev/)
*   **Fonts:** Geist Sans, Geist Mono

## Project Structure:

```
SoulMateAI/
├── .vscode/                 # VS Code settings
├── public/                  # Static assets
├── src/
│   ├── ai/                  # Genkit AI flows and configuration
│   │   └── flows/
│   ├── app/                 # Next.js App Router (pages, layouts)
│   │   ├── chat/
│   │   ├── login/
│   │   └── voice-practice/
│   ├── components/          # React components
│   │   └── ui/              # ShadCN UI components
│   ├── context/             # React context (e.g., AuthContext)
│   ├── hooks/               # Custom React hooks (e.g., useSpeechToText, useTextToSpeech)
│   ├── lib/                 # Utility functions
│   └── ...
├── .env                     # Local environment variables (SHOULD NOT BE COMMITTED)
├── next.config.ts           # Next.js configuration
├── package.json             # Project dependencies and scripts
├── tailwind.config.ts       # Tailwind CSS configuration
├── tsconfig.json            # TypeScript configuration
└── README.md                # This file
```

## Getting Started: Prerequisites

Before you begin, ensure you have the following installed on your local machine:

*   **Node.js:** (v18 or later recommended) - includes npm (Node Package Manager). You can download it from [nodejs.org](https://nodejs.org/).
*   **Google Cloud CLI:** Required for authenticating Genkit to use Google AI services. Install it from [cloud.google.com/sdk/docs/install](https://cloud.google.com/sdk/docs/install).

## Setup and Running Locally:

1.  **Clone the Repository (if you haven't already):**
    ```bash
    git clone <your-repository-url>
    cd SoulMateAIProject # Or your project's root folder name
    ```

2.  **Install Dependencies:**
    Navigate to the project's root directory in your terminal and run:
    ```bash
    npm install
    ```
    (If you prefer Yarn, use `yarn install`)

3.  **Configure Google Cloud Authentication for Genkit:**
    Genkit needs to authenticate with Google Cloud to use the Gemini models.
    *   Open your terminal and run:
        ```bash
        gcloud auth application-default login
        ```
    *   This command will open a web browser. Log in with your Google account and grant the necessary permissions. This will allow Genkit to use your credentials for accessing Google AI services during local development.
    *   **Important:** Ensure the Google Cloud project associated with your account has the "Vertex AI API" (or "AI Platform Training and Prediction API") enabled.

4.  **Environment Variables (Optional for this Demo):**
    *   This project uses a `.env` file for local environment variables. For this demo, no critical API keys are expected in `.env` as Genkit uses the `gcloud` authentication.
    *   If you were to add services requiring API keys (e.g., a database), you would create a `.env` file in the project root and add them there:
        ```env
        # Example for a hypothetical database
        # DATABASE_URL="your_database_connection_string"
        # NEXT_PUBLIC_ANALYTICS_ID="your_analytics_id"
        ```
    *   **Note:** The `.env` file should be listed in your `.gitignore` file and **never** committed to version control.

5.  **Run the Development Server:**
    ```bash
    npm run dev
    ```
    This command starts the Next.js development server, usually on port `9002`. You should see output similar to:
    ```
    ▲ Next.js <version> (Turbopack)
    - Local:        http://localhost:9002
    - Network:      http://<your-local-ip>:9002
    ```

6.  **Access the Application:**
    Open your web browser and navigate to [http://localhost:9002](http://localhost:9002).

7.  **Login with Demo Credentials:**
    *   **Email:** `yogeshwar.test@gmail.com`
    *   **Password:** `T3$t@5959`

8.  **Optional: Run Genkit Developer UI:**
    To inspect Genkit flows, traces, and prompts, you can run the Genkit Developer UI in a *separate terminal window*:
    ```bash
    npm run genkit:dev
    ```
    This usually starts on [http://localhost:4000](http://localhost:4000).

## Available Scripts:

*   `npm run dev`: Starts the Next.js development server with Turbopack.
*   `npm run build`: Builds the application for production.
*   `npm run start`: Starts a Next.js production server (after building).
*   `npm run lint`: Lints the codebase using Next.js's built-in ESLint configuration.
*   `npm run typecheck`: Runs TypeScript type checking.
*   `npm run genkit:dev`: Starts the Genkit Developer UI.
*   `npm run genkit:watch`: Starts the Genkit Developer UI and watches for changes in AI-related files.

## Deployment:

This project is configured for deployment on platforms supporting Node.js and Next.js.
*   For **Firebase App Hosting**, the `apphosting.yaml` file is included.
*   For other platforms like **Vercel**, **Netlify**, or **Google Cloud Run**, follow their respective deployment guides for Next.js applications.
*   **Important:** When deploying, ensure any necessary API keys (especially for Google AI if not using service account ADC) are set as secure environment variables on your hosting platform. Do **not** commit `.env` files or hardcode secrets into your deployed code.

## Contributing:

(This section can be expanded if you plan to have others contribute to the project.)

Currently, this is a solo project. If you wish to contribute, please fork the repository and submit a pull request.

## License:

(Specify a license if you wish, e.g., MIT License. If not specified, standard copyright laws apply.)

This project is unlicensed.
```
