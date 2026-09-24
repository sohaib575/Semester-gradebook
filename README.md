# Semester-gradebook
Interactive semester GPA &amp; CGPA target planner — tracks current SGPA, calculates the exact grade needed to hit a target CGPA, and visualizes your trajectory with Chart.js. Pure HTML/CSS/JS, no backend.
An interactive, logic-driven web tool that helps university students track semester performance, plan future grade targets, run "what-if" scenarios, and visualize their CGPA trajectory across semesters.

No backend, no build step, no dependencies to install — pure HTML, CSS, and vanilla JavaScript. Open index.html and it runs.

✨ Features
1. Course Entry & SGPA Calculation
Add/remove unlimited courses with name, credit hours, and letter grade
Fully editable 4.0 grading scale (change any point value and everything recalculates)
Live Semester GPA (SGPA), total credit hours, and projected new CGPA
2. What-If Scenario & Target Analyzer
Enter your current CGPA, completed credit hours, and a target CGPA
Instantly calculates the exact minimum SGPA needed this semester to hit that target
Suggests one achievable grade combination (e.g. "2 A's + 1 B+") that reaches the required SGPA
Reality check alert: if the required SGPA exceeds 4.00, it flags the target as unachievable in one semester and estimates the minimum number of semesters needed instead
3. CGPA Trajectory Visualizer
Chart.js line graph spanning Semester 1–8
Historical CGPA — your entered past-semester values
Projected path — where your CGPA is headed if you hit the required SGPA each future term
Target threshold — a benchmark line at your goal CGPA
🗂️ Project Structure
gradebook/
├── index.html    # Markup only
├── style.css     # Theming and layout
├── logic.js      # Math/Logic Engine — pure functions, no DOM (SGPA, CGPA, target SGPA, min-semesters, grade combos)
├── chart.js      # Chart Rendering Engine — trajectory graph
└── ui.js         # Interactive UI — forms, dynamic rows, tabs, localStorage persistence

Load order matters: logic.js → chart.js → ui.js (already set up correctly in index.html).

🚀 Getting Started
Clone or download this repo
Keep all five files in the same folder
Open index.html in any modern browser

No npm install, no server required. (If your browser blocks local JS via file://, run: python -m http.server 8000, then visit http://localhost:8000.)

🧮 Core Formula
required_SGPA = (target × (current_credits + new_credits) − current_CGPA × current_credits) / new_credits

If required_SGPA > 4.00, the target can't be reached in a single semester — the app estimates the minimum number of semesters assuming a perfect 4.00 SGPA each term.

🛠️ Tech Stack
HTML5 + vanilla JavaScript (no framework)
Chart.js (via CDN) for the trajectory graph
LocalStorage for per-device session persistence — nothing sent to a server
