# Cadence — Interview Prep Coach

A zero-build, single-file interview preparation chatbot built with HTML, Tailwind CSS, and vanilla JavaScript. Cadence runs completely offline out of the box with a built-in rubric evaluator and optionally connects to the Google Gemini or OpenAI API for live AI grading.

## Features

- **Four Structured Interview Tracks:** Behavioral (STAR), Data Structures & Algorithms, System Design, and AI & Machine Learning (18 curated questions plus custom question support).
- **Practice & Mock Modes:** Practice mode includes contextual hints, follow-up probes, and collapsible model answer outlines. Mock mode runs a strict 5-question interview and reveals full scores at the end.
- **Difficulty Calibration:** Switch between **Entry**, **Mid**, and **Senior** levels to adjust rubric strictness, and customize your target role (e.g., *Software Engineer*, *ML Engineer*, *SWE Intern*).
- **Instant 4-Dimension Rubric Scoring:** Evaluates every answer out of 100 across **Structure**, **Depth & Signal**, **Specificity**, and **Clarity**, with concrete *What Landed* and *What to Tighten* feedback.
- **Live Session Scorecard & Markdown Debrief:** Track running averages in the sidebar and export a formatted Markdown debrief report with one click.
- **Built-in Interview Tools:** Response stopwatch, live word counter, optional browser voice-to-text input (Web Speech API), and light/dark theme toggle.
- **Optional Live LLM Grading:** Bring your own Google Gemini (`gemini-2.5-flash`) or OpenAI (`gpt-4o-mini`) API key in the settings modal, with automatic fallback to the offline coach if a request fails.

## Interview Tracks

| Track | Framework | Built-in Questions |
| :--- | :--- | :---: |
| **Behavioral (STAR)** | Situation → Task → Action → Result | 5 |
| **DSA & Problem Solving** | Clarify → Brute Force → Optimal → Complexity → Edge Cases | 5 |
| **System Design** | Requirements → Scale Estimates → Architecture → Bottlenecks | 4 |
| **AI & Machine Learning** | Core Concept → Intuition → Trade-offs → Production Reality | 4 |

## Scoring Rubric

Each response is scored on a 0–100 scale using four weighted dimensions:

| Dimension | Weight | What It Evaluates |
| :--- | :---: | :--- |
| **Structure** | 25% | Clear progression matching the track's interview framework |
| **Depth & Signal** | 35% | Coverage of core domain concepts, trade-offs, and edge cases |
| **Specificity** | 22% | Concrete metrics, Big-O notation, first-person ownership, and examples |
| **Clarity** | 18% | Conciseness, sentence pacing, and staying within target answer length |

## Quick Start

No build step, backend, or package installation is required.

1. Clone the repository:

   ```bash
   git clone https://github.com/chiragpandey14112006-gif/cadence-interview-coach.git
   cd cadence-interview-coach
   ```

2. Open `interview_coach.html` directly in any modern browser, or serve it locally:

   ```bash
   python3 -m http.server 8000
   ```

   Then visit `http://localhost:8000/interview_coach.html`.

### Deploy to GitHub Pages

1. Rename `interview_coach.html` to `index.html` (or keep it and link directly to `/interview_coach.html`).
2. Push your files to `https://github.com/chiragpandey14112006-gif/cadence-interview-coach`.
3. Open **Settings → Pages**, select your `main` branch and `/ (root)` folder, and click **Save**.
4. Your live site will be available at `https://chiragpandey14112006-gif.github.io/cadence-interview-coach/`.

## Optional Live AI Setup

Cadence works offline by default. To enable live AI evaluation:

1. Click the **Settings** icon in the top-right header.
2. Select **Google Gemini API (`gemini-2.5-flash`)** or **OpenAI API (`gpt-4o-mini`)**.
3. Paste your API key and click **Save Settings**.

> **Privacy note:** Your API key is kept only in your current browser session memory and is never written to `localStorage` or sent anywhere other than the provider you choose.

## Tech Stack

- **Markup & Layout:** Single-file HTML5 + CSS Custom Properties (light & dark themes)
- **Styling:** Tailwind CSS (`3.4.17` via CDN)
- **Icons:** Lucide Icons (`0.460.0` via CDN)
- **Logic:** Vanilla JavaScript (ES6+), Web Speech API (`SpeechRecognition`)

## Project Structure

```text
.
├── interview_coach.html   # Complete self-contained web application
└── README.md              # Project documentation
```

## Customization

- **Add or edit questions:** Update the `TRACKS` object in the `<script>` section of `interview_coach.html` with your own `prompt`, `signals`, `hint`, `probe`, and `outline` entries.
- **Adjust rubric weights:** Edit the weighted formula inside `evaluateOffline()` to tune scoring for your target roles.

## Author

Built by [@chiragpandey14112006-gif](https://github.com/chiragpandey14112006-gif).

## License

This project is open source and available under the MIT License.