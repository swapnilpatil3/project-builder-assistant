#  Project Builder Assistant

> An AI-powered assistant that turns any project idea into a 
> complete project plan + working website using local AI.

---

##  What is this project?

This project was built as part of the AI Internship Training Program (Problem Statement #3 - Project Builder Assistant).

The idea is simple:
- You type any project idea (e.g. "A calculator app")
- The AI asks you 4 clarifying questions
- You answer them
- The AI builds a COMPLETE project plan + working website for you!

---

##  Features

| Feature | Description |
|---|---|
| 💬 Smart Questions | AI asks 4 clarifying questions about your idea |
| 📋 Requirements | Functional and non-functional requirements |
| 🛠️ Tech Stack | Recommends open-source tools with reasons |
| 🏛️ Architecture | Component diagram and data flow |
| 📁 Folder Structure | Complete folder tree with file purposes |
| 📅 Milestones | 4-week roadmap with tasks |
| 🚀 Getting Started | Step-by-step setup instructions |
| 🌐 Live Website | Generates a working website from your idea |
| 👁️ Live Preview | See the website running inside the app |
| 📊 Evaluation | Scores the generated app out of 100 |
| ⬇️ Download | Download plan as Markdown and app as HTML |

---

##  Tech Stack

| Tool | Purpose |
|---|---|
| Google Colab | Development environment |
| Python | Programming language |
| Ollama | Run AI model locally |
| gemma2:2b | Open-source AI model (1.6GB) |
| Gradio | Web UI framework |
| requests | API communication |

> ✅ 100% Open Source — No paid APIs needed!

---

##  How to Run (Step by Step)

### Step 1 — Open Google Colab
- Go to [colab.research.google.com](https://colab.research.google.com)
- Upload `project_builder_assistant.ipynb`
- Change runtime: `Runtime → Change runtime type → T4 GPU`

### Step 2 — Run Cell 1 (Install everything)
```python
!sudo apt-get install -y zstd -q
!curl -fsSL https://ollama.ai/install.sh | sh
!pip install gradio requests -q
```
⏳ Wait 2-3 minutes

### Step 3 — Run Cell 2 (Start Ollama + Download Model)
```python
import subprocess, time
subprocess.Popen(["/usr/local/bin/ollama", "serve"])
time.sleep(4)
!ollama pull gemma2:2b
```
⏳ Wait 3-5 minutes (downloads 1.6GB model)

### Step 4 — Run All Remaining Cells
- Click `Runtime → Run All`
- Wait for all cells to finish

### Step 5 — Open the App
- Look for this line in the last cell output:
```
Running on public URL: https://xxxxxx.gradio.live
```
- Open that link in your browser!

---

##  How to Use the App

1. **Type your project idea** in the text box
   - Example: `A calculator app`
   - Example: `A todo list web app`
   - Example: `A quiz app using PDFs`

2. **Click "Step 1: Generate Questions →"**
   - AI generates 4 clarifying questions
   - Wait 20-30 seconds

3. **Answer the 4 questions**

4. **Click "Step 2: Build Plan + Generate App →"**
   - Wait 3-5 minutes
   - AI builds everything!

5. **Scroll down to see:**
   -  Complete project plan
   -  Live working website
   -  Evaluation score
   -  Download buttons

---

##  How the AI Pipeline Works
```
Your Idea + Answers
        ↓
[Stage 1] Extract Requirements → JSON
        ↓
[Stage 2] Recommend Tech Stack → JSON
        ↓
[Stage 3] Design Architecture → JSON
        ↓
[Stage 4] Generate Folder Structure → JSON
        ↓
[Stage 5] Create 4-Week Milestones → JSON
        ↓
[Stage 6] Write Implementation Steps → JSON
        ↓
[Stage 7] Generate Working Website → HTML
        ↓
[Stage 8] Evaluate the App → Score/100
```

Each stage feeds its output into the next stage!

---

##  Example Output

**Input idea:** `A calculator app`

**Generated plan includes:**
- Requirements: addition, subtraction, multiplication, division
- Tech Stack: HTML + CSS + JavaScript
- Architecture: UI → Calculator Logic → Display
- Folder Structure: index.html, style.css, app.js
- 4-Week Milestones with tasks
- Getting started commands
- Working calculator website with all buttons!
- Evaluation Score: 79/100 👍

---

##  Challenges Faced & Fixes

### Problem 1: Ollama not installing
**Error:** `ERROR: This version requires zstd`
**Fix:** Install zstd first: `!sudo apt-get install -y zstd`

### Problem 2: Buttons not working in generated website
**Error:** AI put JavaScript in external file `calculator.js`
**Fix:** Updated prompt to force all JavaScript inline in HTML

### Problem 3: Colab resets after disconnection
**Fix:** Put all setup code in Cell 1, use `Runtime → Run All`

### Problem 4: LLM not returning valid JSON
**Fix:** Added 3-step JSON parser with fallback using regex

---

##  Repository Structure
```
project-builder-assistant/
├── project_builder_assistant.ipynb  ← Main notebook (run this!)
├── generated_website.html           ← Example generated website
└── README.md                        ← This file
```

---

##  Future Improvements

- [ ] Support more project types (mobile, ML, CLI)
- [ ] Better website generation with more features
- [ ] Save all generated plans to Google Drive
- [ ] Add more evaluation metrics

---




##  Author

- **GitHub:** [swapnilpatil3](https://github.com/swapnilpatil3)
- **Project:** AI Internship Training — Problem Statement #3
- **Built with:** Google Colab + Ollama + Gradio

-**Project Demonstration Link:**https://drive.google.com/file/d/1z91hIfzJxyfT1nKjJLY0i2MQ-g3SL6d6/view?usp=sharing
