# Ticket Generator

This tool helps convert Confluence documents into a list of Jira tickets. It analyzes the content of your documents and creates corresponding tickets under an Epic that you specify.

## Setup

1. **Install Gemini CLI**: Ensure you have the Gemini CLI installed. If not, refer to the [main setup guide](../README.md).

2. **Navigate to the Directory**:
   ```bash
   cd ticket-generator
   ```

3. **Install Atlassian MCP Server**:
   Execute the following command to install the necessary extension:
   ```bash
   gemini extensions install https://github.com/atlassian/atlassian-mcp-server
   ```

## Usage

1. **Start Gemini**:
   Run the Gemini CLI in this directory:
   ```bash
   gemini
   ```

2. **Verify Installation**:
   Inside the Gemini session, verify that the Atlassian MCP server is active:
   ```
   /mcp list
   ```
   You should see `atlassian-rovo-mcp-server` in the list.

3. **Authorize**:
   Authenticate with Atlassian by running:
   ```
   /mcp auth atlassian-rovo-mcp-server
   ```
   Follow the authentication prompts.

4. **Generate Tickets**:
   To start the process, simply type:
   > I want to generate some Jira tickets

   Gemini will ask you for a list of Confluence tickets. From here, follow the prompts.

