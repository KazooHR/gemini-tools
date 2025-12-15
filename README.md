# ⚠️ WARNING: DO NOT COMMIT GEMINI CREDENTIALS

**Verify that your Gemini credentials (e.g., `oauth_creds.json`, `google_accounts.json`) are NEVER committed to this repository.**

---

# Gemini Tools

This repository contains tools and configurations for the Gemini CLI.

## Setup

1. **Install Gemini CLI**: Follow the setup instructions at [Gemini CLI Get Started](https://geminicli.com/docs/get-started/).

## Using a Tool

To use one of the tools in this repository:

1. Open your terminal.
2. `cd` into the specific tool's directory (e.g., `cd ticket-generator`).
3. Follow the instructions provided in that tool's specific README or prompts.

## Adding a New Tool

To add a new tool to this repository:

1. **Set up your tool**: Create your tool directory and configure your prompts/agents.
2. **Update `.gitignore`**: This repository ignores all files by default (`*`). You must explicitly whitelist the files you want to commit.
   - Open `.gitignore`.
   - Add your new tool's folder and `settings.json` with an exclamation mark `!` to include them.
   - Example:
     ```gitignore
     !/my-new-tool/
     !/my-new-tool/settings.json
     ```
   - **Ensure you do NOT whitelist credential files.**
