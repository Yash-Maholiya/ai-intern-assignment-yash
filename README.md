# AI Automation Intern — Technical Assessment

**Candidate Information**
- **Full Name**: Yash
- **Email**: ch.yash8434@gmail.com
- **Date of Submission**: September 12, 2026
- **Repository**: [https://github.com/Yash-Maholiya/ai-intern-assignment-yash](https://github.com/Yash-Maholiya/ai-intern-assignment-yash)

---

## Project Overview

This repository contains the complete practical technical assessment for the **AI Automation Intern** role at HSA Team. It covers front-end form engineering with vanilla web technologies, automated webhook pipelines and scheduled data ingestion using **N8N**, end-to-end integration, and documentation.

### Repository Structure
```text
ai-intern-assignment-yash/
├── part-a/
│   └── index.html                              # Pure HTML + CSS + Vanilla JS Student Lead Capture Form
├── part-b/                                     # N8N Automation Workflows (Upcoming)
│   ├── workflow-b1-lead-notification.json
│   ├── workflow-b2-scheduled-fetch.json
│   ├── screenshot-b1.png
│   └── screenshot-b2.png
├── part-c/                                     # End-to-End Webhook Integration (Upcoming)
│   ├── index.html
│   └── demo.gif / loom-link.txt
└── README.md                                   # Comprehensive documentation & setup guide
```

---

## Part A — HTML, CSS & Vanilla JavaScript Lead Capture Form

### Implementation Summary
- **Zero Frameworks**: Built using pure semantic HTML5, modern vanilla CSS, and clean vanilla JavaScript.
- **Form Fields**:
  - **Full Name**: Text input with minimum length and alphabet validation.
  - **Email**: Input validated against RFC 5322 pattern with instant and on-submit feedback.
  - **Country**: Accessible dropdown `<select>` populated with international study destinations.
  - **Course Level (Radio)**: Responsive degree level selection.
    - *Desktop*: Displays 3 balanced, equal cards side-by-side (`Undergraduate (UG)`, `Postgraduate (PG)`, `Doctorate (PhD)`).
    - *Mobile*: Fluidly converts to full-width interactive selection rows with animated radio indicators, degree badges, and descriptions for optimal thumb ergonomics.
  - **Preferred University**: Text input with non-empty validation.
  - **Personal Statement / Inquiry**: Multiline textarea with a **live 300-character counter** (dynamically tracks characters remaining, changes to warning at $\le 40$ and danger at $0$).
- **Client-side UX & Validation**:
  - Validates all fields upon form submission with clear, accessible inline red error messages beneath each invalid field (`role="alert"`, `aria-invalid`).
  - Errors automatically clear as the user types/corrects inputs.
  - Focus is automatically moved to the first invalid field.
  - **No Page Reload**: Intercepts `submit` event via `event.preventDefault()`.
  - On valid submission: displays a clean, animated Thank-You confirmation card with submitted details and a reset option ("Submit Another Application").
  - Formatted JSON payload is cleanly logged to the browser console (`console.group` / `console.log(JSON.stringify(payload, null, 2))`).

### How to Run and Test Part A
1. **Direct Browser Open**:
   - Simply double click or open [`part-a/index.html`](part-a/index.html) in any modern browser (Chrome, Edge, Firefox, Safari).
2. **Local HTTP Server (Optional)**:
   - Run Python's built-in web server:
     ```bash
     python3 -m http.server 3000
     ```
   - Open [http://localhost:3000/part-a/](http://localhost:3000/part-a/) on your laptop, or `http://<your-local-ip>:3000/part-a/` on mobile devices connected to the same network.
3. **Validation Checklist**:
   - [x] Click **Submit Application** with empty fields $\rightarrow$ inline error messages appear for all required fields.
   - [x] Type an invalid email format (e.g. `test@`) $\rightarrow$ displays specific email error.
   - [x] Type in the message textarea $\rightarrow$ live counter decrements from 300 in real time.
   - [x] Submit valid form data $\rightarrow$ page does not reload, Thank-You card appears, and JSON payload logs to browser console.

---

## Part B — N8N Automation Workflows *(In Progress)*
*Documentation for B1 (Lead Notification Workflow) and B2 (Scheduled Data Fetch Workflow) will be added upon implementation in Part B.*

---

## Part C — Integration Challenge *(Upcoming)*
*Documentation for end-to-end webhook integration, submit button loading states, and error handling will be added upon implementation in Part C.*

---

## Challenges Faced & Resolutions (Part A)
1. **Mobile Layout for Degree Radio Cards**:  
   *Challenge*: On narrow mobile screens, having 3 horizontal square cards caused awkward stacking and empty whitespace on the right.  
   *Resolution*: Implemented a responsive hybrid design using CSS media queries. On desktop viewports, options display as 3 sleek horizontal cards in a row. On screens $\le 580\text{px}$, they dynamically transform into full-width interactive selection rows with animated radio indicators and descriptions.
2. **Framework-Free Live Validation & State Management**:  
   *Challenge*: Providing instant feedback without triggering premature error messages before initial user submission.  
   *Resolution*: Applied a two-tier validation lifecycle in vanilla JavaScript—validating completely on submit while attaching lightweight input listeners to clear errors in real-time as users correct their entries.
