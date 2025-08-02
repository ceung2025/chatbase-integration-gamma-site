
Built by https://www.blackbox.ai

---

# Chatbase Integration for Gamma Site

## Project Overview
The Chatbase Integration project is designed to enhance user experience on the Gamma website (creator.medtools.id) by providing an AI-driven chat assistant. It seamlessly integrates with the website to offer live chat support using Chatbase, enabling users to interact with AI for assistance regarding Medtools services.

## Installation
To get started with integrating the Chatbase AI Assistant within your Gamma site, follow these steps:

1. **Open your Gamma Editor**
   - Visit your Gamma dashboard.
   - Open your site (creator.medtools.id) for editing.

2. **Add a Custom HTML Block**
   - Look for the "Embed" or "Custom HTML" component in Gamma.
   - Add a new HTML/Embed block to your desired page.

3. **Insert Integration Code**
   - Copy the contents from `gamma-chatbase-embed.html` or use the script only from `gamma-copy-paste-code.html` examples.
   - Paste it directly into the HTML/Embed block.

## Usage
After embedding the code, the AI chat button will appear in the bottom-right corner of the webpage. Users can click this button to initiate a conversation with the AI Assistant. If the primary AI service is unavailable, a fallback button will provide alternative interactions.

## Features
- **Automatic Retry Logic**: The integration automatically attempts to load the Chatbase script multiple times.
- **Fallback Interface**: If the main service fails to load, a temporary chat interface ensures users can still receive assistance.
- **Status Indicators**: Users receive visual feedback regarding the loading status and any errors encountered.
- **Mobile Responsive**: The design accommodates all screen sizes for an optimal user experience.
- **Non-intrusive Design**: The chat button is displayed minimally at the bottom-right corner of the page.

## Dependencies
Currently, there are no explicit dependencies listed in a `package.json` file. The integration works directly with the provided HTML and JavaScript code.

## Project Structure
The project consists of the following key files:

- **`chatbase-integration.html`**: Initial HTML integration file containing the chat assistant and fallback logic.
- **`chatbase-integration-fixed.html`**: Fixed version of the initial integration for reduced errors in execution.
- **`gamma-chatbase-embed.html`**: Recommended HTML file that combines the essential structure and functionality for easy embedding.
- **`gamma-implementation-guide.md`**: A comprehensive guide for implementing the Chatbase integration on Gamma with step-by-step instructions.
- **`gamma-copy-paste-code.html`**: Simple code snippet for quick integration without needing to copy complete HTML files.

## Conclusion
The Chatbase Integration project offers an effective way to enhance user engagement on your website via an AI-powered chat assistant. Follow the provided instructions closely to embed the integration smoothly and ensure that users always have access to support.

For any support or troubleshooting, feel free to consult the implementation guide or check for errors in your browser console while testing the integration.