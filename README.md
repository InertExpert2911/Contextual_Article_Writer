# Contextual Article Writer ✍️📄✨

[![License: MIT](https://img.shields.io/badge/License-MIT-white.svg)](https://opensource.org/licenses/MIT) [![Python Version](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/) [![Made with Gradio](https://img.shields.io/badge/Made%20with-Gradio-orange)](https://www.gradio.app/) [![Uses Gemini API](https://img.shields.io/badge/Uses-Gemini%20API-green)](https://ai.google.dev/) [![Made with Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?logo=jupyter)](https://jupyter.org/)
[![Open In Kaggle](https://img.shields.io/badge/Open%20In-Kaggle-blue?logo=kaggle)](https://www.kaggle.com/code/tharunreddy2911/contextual-article-writer) [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1us_rmp7YpYaLR2nVUgRYFA6Tw7tjBV9f?usp=sharing)

----

### Transform raw information from URLs and documents into structured article drafts using the power of Google Gemini and an interactive workflow.

----

## Table of Contents

* [Bridging Context & Content](#introduction-bridging-context-&-content-)
* [Core Capabilities](#core-capabilities-)
* [The Workflow](#the-workflow-)
* [Quick Start](#quick-start-)
* [Detailed Setup Instructions](#detailed-setup-instructions-)
* [Running the Application](#running-the-application-)
* [Usage Scenarios](#usage-scenarios-)
* [Important Considerations & Limitations](#important-considerations--limitations-)
* [Contributing](#contributing-)

---

## Bridging Context & Content 🌉

Writing compelling, well-structured articles often begins with gathering information from various sources – web pages, reports, documents. Translating this raw context into a coherent narrative with a logical flow requires significant effort in synthesis and outlining before the actual writing even begins.

The **Contextual Article Writer** is designed to accelerate this process. It acts as an intelligent assistant, leveraging Google's Gemini models to:

1.  **Ingest and Understand:** Process text from provided URLs and documents (PDF/DOCX).
2.  **Structure Ideas:** Generate a detailed, hierarchical outline based on your topic and the ingested context.
3.  **Collaborate and Refine:** Allow you to interactively edit and approve the generated outline.
4.  **Draft the Narrative:** Write a full article draft that follows your refined structure, grounded in the source material.

This tool aims to help you move faster from research to a polished first draft, ready for your essential human review and enhancement.

## Core Capabilities ✨

1.  **📚 Context Processing & Understanding:** Intelligently extracts and processes text from multiple URLs and common document formats (PDF, DOCX) to establish a contextual foundation using Google Gemini.
2.  **✏️ AI-Assisted Outlining & Editing:** Generates detailed, context-aware Markdown outlines (headings, keywords) and provides an interactive UI textbox for seamless user refinement before drafting.
3.  **✍️ Structured Article Drafting:** Writes comprehensive article drafts that strictly adhere to the structure and flow defined in the user-confirmed outline.
4.  **🔄 Customizable & Iterative Workflow:** Offers controls for generation parameters (tone, audience, word count) and supports easy regeneration of outlines or articles with additional user feedback for refinement.
5.  **🚀 Flexible & Accessible Platform:** Runs smoothly on Kaggle, Google Colab, or local Jupyter environments with automatic, secure API key detection and standard export options (MD, TXT).

## The Workflow 📝

The tool guides you through a multi-tab interface:

1.  **Input Sources (Tab 1 📥):** Provide URLs and/or upload documents. Click **"Process Sources & Go to Outline"**.
2.  **Outline Generation & Editing (Tab 2 📝):** Define your article topic/prompt and generation parameters (industry, audience). Click **"Generate Outline"**. Review and **edit the outline** in the textbox. Click **"Confirm Outline & Go to Article Generation"**.
3.  **Article Configuration & Generation (Tab 3 ✨):** Set the desired tone and word count. *(Optional)* Add specific instructions if regenerating. Click **"Generate Article"** (or **"Regenerate Article..."**).
4.  **Review & Download (Tab 4 💾):** Examine the generated article draft. Download using the `.md` or `.txt` buttons.
5.  **Human Review (Crucial!):** Always perform a final review, edit, and fact-check of the downloaded content.

## Quick Start 🚀

[![Open In Kaggle](https://img.shields.io/badge/Open%20In-Kaggle-blue?logo=kaggle)](https://www.kaggle.com/code/tharunreddy2911/contextual-article-writer) [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1us_rmp7YpYaLR2nVUgRYFA6Tw7tjBV9f?usp=sharing)

## Detailed Setup Instructions 🛠️

Setting up requires a Google Gemini API key configured securely. **Never paste your API key directly into the code!**

**1. Google Gemini API Key:**
1. Go to [Google AI Studio](https://aistudio.google.com/).
2. Sign in and generate a new API key ("Get API key").
3. Copy the key and store it securely.

**Step 2: Configure the API Key for Your Environment**

The script will automatically look for your key in these places, in this order. You only need to set it up in **one** of these locations:

* **Method A: [Kaggle](https://www.kaggle.com/)**
    1. In your Kaggle notebook, use the **"Add-ons" > "Secrets"** menu.
    2. Add secrets with these exact label: `GOOGLE_API_KEY`.
    3. Ensure the notebook has access selected for these secrets.

* **Method B: [Google Colab](https://colab.research.google.com/)**
    1. Use the **"Secrets" tab** in the left sidebar.
    2. Add secrets with the exact labels: `GOOGLE_API_KEY`.
    3. Ensure the notebook has access selected for these secrets.

* **Method C: Local Environment Variable / `.env` File (For running on your own machine)**
    * **Option C.1: System Environment Variable:**
        1.  Set a system-wide environment variable named `GOOGLE_API_KEY` with your API key as its value. This makes the key available system-wide but can be less project-specific.
        2.  **How-To Guides:** See external links for setting persistent environment variables on [Windows](https://www.computerhope.com/issues/ch000549.htm), [macOS](https://support.apple.com/guide/terminal/use-environment-variables-apd382cc5fa-4f58-4449-b20a-41c53c006f8f/mac), or [Linux](https://www.digitalocean.com/community/tutorials/how-to-read-and-set-environmental-and-shell-variables-on-linux).
    * **Option C.2: `.env` File (Recommended for Local Projects):**
        1.  Create a file named exactly `.env` (note the leading dot) in the root directory of your project (where you run the script/notebook from).
        2.  Add the following line to the `.env` file, replacing `YOUR_API_KEY_HERE` with your actual key:
            ```dotenv
            GOOGLE_API_KEY="YOUR_API_KEY_HERE"
            ```
        3.  **Important:** Add `.env` to your `.gitignore` file to prevent accidentally committing your secret key to version control.
        4.  You'll need a Python library to load this file. The script assumes `python-dotenv` is used (you might need to install it: `pip install python-dotenv`). The code in Cell 3 should ideally include logic to load the `.env` file if detected (e.g., using `load_dotenv()` from the `dotenv` library *before* accessing `os.environ.get`).
        5.  **How-To Guides:** Learn more about `.env` files and the `python-dotenv` library: [python-dotenv on PyPI](https://pypi.org/project/python-dotenv/) or [Using .env for Environment Variables in Python](https://www.geeksforgeeks.org/how-to-create-and-use-env-files-in-python/).

**Important:** Ensure the secret/variable name `GOOGLE_API_KEY` is spelled correctly and matches exactly in whichever method you choose.

## Running the Application 🏃

1.  **Environment:** Use the Kaggle/Colab links above.
2.  **Dependencies & Key:** Execute the initial setup cells/steps to install libraries and configure the API key (as per the setup instructions above).
3.  **Verify:** Check console output for successful library installation, API key detection (it should state the source: Kaggle, Colab, or Environment Variable), and model initialization. Address any errors before proceeding.
4.  **Launch:** Run the final cell containing `app.launch(...)`.
5.  **Access UI:** Open the provided URL (`*.gradio.live` or `http://127.0.0.1:...`) in your browser.
6.  **Keep Active:** The Gradio UI requires the Python kernel/script to remain running.

## Usage Scenarios 🧭

This tool can be valuable for:

* **✍️ Writers & Bloggers:** Quickly structure posts and generate first drafts based on research notes or source links.
* **📊 Researchers & Analysts:** Synthesize findings from multiple papers or reports into structured summaries or preliminary analyses.
* **🎓 Students & Educators:** Create summaries or study guides from lecture notes, textbooks (PDFs), or academic articles.
* **📝 Marketers:** Draft content briefs, initial website copy, or informative articles based on product documentation or market research.
* **💡 Anyone needing to structure information:** Transform collections of text into organized narratives or reports.

## Important Considerations & Limitations ⚠️

* **AI as an Assistant:** Treat the output as a **draft**. It requires human oversight, editing, fact-checking, and refinement to ensure quality, accuracy, and originality.
* **API Costs & Terms:** You are responsible for usage costs and adherence to Google's API terms.
* **Source Quality:** The output quality is highly dependent on the clarity, relevance, and accuracy of the provided source materials.
* **Context Length:** Extremely long documents or a vast number of URLs might exceed the model's processing capacity.
* **Web Scraping:** May fail on complex, JavaScript-heavy websites or pages behind logins.
* **Formatting Loss:** Complex formatting (tables, specific layouts) from source files might not be preserved in the extracted text or final output.

## Contributing 🤝

Contributions, bug reports, and feature ideas are welcome!

1.  **Check Issues:** Look for existing issues before opening a new one.
2.  **Open an Issue:** Clearly describe the bug (with steps to reproduce) or enhancement suggestion.
3.  **Pull Requests:** Please fork the repo, create a feature branch, make your changes (with comments and testing), and submit a PR with a clear description.

---

### ✨ Go from scattered sources to structured drafts in minutes. Happy writing! ✨
