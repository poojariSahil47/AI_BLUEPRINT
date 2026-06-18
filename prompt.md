You are a Senior Python Architect, Flask Engineer, Vercel Deployment Expert, and AI SaaS Developer.

I have an existing Streamlit application and I want a COMPLETE PRODUCTION-GRADE migration to Flask while preserving ALL functionality.

CRITICAL REQUIREMENTS:

The attached Streamlit app.py is the source of truth.

DO NOT SIMPLIFY.

DO NOT REMOVE FEATURES.

DO NOT CREATE AN MVP.

DO NOT REDUCE FUNCTIONALITY.

The final Flask version must preserve the exact architecture, exact inputs, exact outputs, exact workflows, exact Gemini prompting logic, exact arXiv integration, exact chart generation, exact bibliography generation, exact LaTeX generation, exact ZIP generation, exact PDF generation logic, exact section generation workflow, exact calculations, exact UI fields, exact user flow, and exact download functionality.

The goal is:

100% feature parity with the original Streamlit application.

━━━━━━━━━━━━━━━━━━━━━━
PROJECT STRUCTURE
━━━━━━━━━━━━━━━━━━━━━━

Generate ONLY these files:

/
├── app.py
├── requirements.txt
├── vercel.json
└── templates/
└── index.html

No additional files.

No blueprints.

No services folder.

No utils folder.

No static folder.

No CSS files.

No JS files.

No React.

No Vue.

No Tailwind build process.

Everything must be contained inside:

1. app.py
2. index.html

━━━━━━━━━━━━━━━━━━━━━━
FLASK REQUIREMENTS
━━━━━━━━━━━━━━━━━━━━━━

The Flask version must:

* Use Flask 3+
* Use render_template
* Use AJAX fetch calls
* Use JSON APIs
* Use send_file for downloads
* Preserve session state behavior
* Preserve generated paper state
* Preserve generated ZIP state
* Preserve generated LaTeX state
* Preserve generated PDF state

Routes should be production ready.

━━━━━━━━━━━━━━━━━━━━━━
VERCEL DEPLOYMENT
━━━━━━━━━━━━━━━━━━━━━━

This application will be deployed to Vercel.

Generate a CORRECT modern Vercel deployment.

Important:

Serverless functions on Vercel Hobby have a 10-second timeout.

This application requires approximately 20–60 seconds for paper generation because multiple Gemini calls are executed sequentially.

Therefore:

Generate vercel.json using:

{
"version": 2,
"builds": [
{
"src": "app.py",
"use": "@vercel/python"
}
],
"routes": [
{
"src": "/(.*)",
"dest": "app.py"
}
]
}

Additionally configure:

maxDuration = 60

where appropriate for Vercel Pro deployments.

Explain any Vercel Hobby limitations directly in code comments.

Do not use deprecated configurations.

Ensure Flask can be imported by Vercel runtime.

━━━━━━━━━━━━━━━━━━━━━━
GOOGLE GEMINI
━━━━━━━━━━━━━━━━━━━━━━

Use the latest Google GenAI SDK.

Correct imports:

from google import genai

Do NOT use deprecated google-generativeai package.

All Gemini logic from the Streamlit application must be preserved exactly.

Maintain:

* Gemini model names
* prompts
* temperatures
* retry logic
* citation logic
* section generation logic
* bibliography logic
* chart generation logic

Do not rewrite prompts.

Do not simplify prompts.

━━━━━━━━━━━━━━━━━━━━━━
ENVIRONMENT VARIABLES
━━━━━━━━━━━━━━━━━━━━━━

NO HARDCODED API KEYS.

API keys must be loaded using:

import os

api_key = os.getenv("GEMINI_API_KEY")

Generate code assuming:

GEMINI_API_KEY

is configured in Vercel Environment Variables.

Do not request user input for API keys.

Do not store API keys in HTML.

━━━━━━━━━━━━━━━━━━━━━━
MATPLOTLIB REQUIREMENTS
━━━━━━━━━━━━━━━━━━━━━━

The Streamlit application generates academic charts.

This functionality must remain.

Vercel-compatible matplotlib setup is mandatory.

At the very top of app.py:

import os
os.environ["MPLCONFIGDIR"] = "/tmp"

import matplotlib
matplotlib.use("Agg")

Use:

import matplotlib.pyplot as plt

Ensure charts render correctly in serverless environments.

Charts must be generated entirely in memory.

Do not rely on local writable directories except /tmp.

Do not call plt.show().

Always close figures.

Prevent memory leaks.

━━━━━━━━━━━━━━━━━━━━━━
FILE GENERATION
━━━━━━━━━━━━━━━━━━━━━━

Preserve:

* ZIP generation
* LaTeX generation
* BibTeX generation
* PDF generation logic
* Download endpoints

All generated assets should use:

io.BytesIO

when possible.

Minimize disk writes.

Support Vercel serverless execution.

━━━━━━━━━━━━━━━━━━━━━━
INDEX.HTML REQUIREMENTS
━━━━━━━━━━━━━━━━━━━━━━

The current Streamlit UI has:

* Sidebar
* Tabs
* Metadata section
* Authors section
* Research context section
* Bibliography section
* Generate section
* Download section
* Preview section
* Word count section

Recreate ALL of these in HTML.

Do not simplify.

Do not remove inputs.

Every field from Streamlit must exist.

All CSS should be embedded inside index.html.

All JavaScript should be embedded inside index.html.

No external JS files.

No external CSS files.

Maintain light theme, Whitish BG with blue accent colors overall professional pallete with rounded card based deisgn.
Maintain professional SaaS UI.
Maintain responsive layout.

Use AJAX fetch APIs to communicate with Flask.

━━━━━━━━━━━━━━━━━━━━━━
REQUIREMENTS.TXT
━━━━━━━━━━━━━━━━━━━━━━

Generate a production-ready requirements.txt.

Use exact compatible versions.

Must include:

Flask==3.0.0
google-genai
pandas==2.2.0
matplotlib==3.8.2
Jinja2==3.1.3
python-dotenv==1.0.1
gunicorn==21.2.0
Werkzeug==3.0.1

Add any additional dependencies required by the original Streamlit application.

━━━━━━━━━━━━━━━━━━━━━━
CODE QUALITY
━━━━━━━━━━━━━━━━━━━━━━

Generate complete code.

No placeholders.

No pseudocode.

No TODO comments.

No “implement here” sections.

No omitted functions.

No shortened snippets.

Every file must be fully generated.

The final output must be a complete production-ready application that can be copied into files and deployed directly.

First analyze the provided Streamlit source code completely.

Then generate:

1. requirements.txt
2. vercel.json
3. app.py
4. templates/index.html

in that exact order.

Output full code for every file.
