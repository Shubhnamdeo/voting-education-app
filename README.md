# 🗳️ VoteSmart: The Educational Voting Game

**A Google Antigravity Challenge Submission**

## 🎯 Chosen Vertical
This project tackles the **Education & Civic Awareness** vertical. It is a gamified, interactive web application designed to educate young Indians (ages 14-25) about the world's largest democratic process—the Indian General Election.

## 🧠 Approach and Logic
Millions of first-time voters participate in Indian elections without fully understanding the process, leading to confusion at the polling booth. 

Our approach was to bridge this gap through **step-by-step storytelling and gamification**. We created a linear, 5-stage journey that puts the user in the shoes of a newly eligible 18-year-old voter. 

**The 5 Stages:**
1. **Registration (Form 6):** Teaches the necessity of the Electoral Roll with an interactive UI and generates a personalized digital Voter ID.
2. **Campaigns (MCC):** Educates users on the Model Code of Conduct through an interactive "Rule Check" quiz with randomized questions.
3. **Voting Day (EVM & VVPAT):** Simulates the physical act of voting using an Electronic Voting Machine and explains the VVPAT slip verification process (with custom sound effects!).
4. **Result Day (FPTP):** Explains the First-Past-The-Post system through a randomized, live-counting bar chart race.
5. **Completion:** Rewards the user with a highly stylized, downloadable "Hack2Skill Voting Champion" certificate.

## ✨ Key Features & Challenge Integrations

### 1. The "Election Buddy" (Google Services Requirement)
To fulfill the requirement of building a **smart, dynamic assistant**, we integrated the **Google Gemini AI API**. 
*   **What it does**: A floating chatbot widget sits in the corner. Users can use built-in "quick reply" buttons to ask basic questions, or type their own questions (e.g., "What is a VVPAT?"). It also features a "Reset Chat" function.
*   **Logic**: The bot is prompted via `system_instructions` to act as a friendly, child-friendly election expert, ensuring responses are safe, concise, and educational.
*   **Simulate Mode**: If users do not want to provide an API key, the bot falls back to a "Simulate Mode" which safely mocks responses, ensuring the UI remains fully testable without credentials!

### 2. Accessibility (Evaluation Metric)
*   **Text-to-Speech (TTS):** We implemented the Web Speech API. Users can click the 🔊 icon next to paragraphs to have the text read aloud, making the game accessible to younger audiences or those with reading difficulties.
*   **Bilingual Support:** A toggle instantly translates the entire application between English and Hindi, ensuring it reaches a wider Indian demographic.

### 3. Usability & Polish
*   **Local Storage:** The app uses browser `localStorage` to save the user's name and progress.
*   **Dynamic Visuals:** Features a custom SVG cursor (which gets "inked" after you vote!), confetti, and CSS animations.

## ⚙️ How the Solution Works
The entire application is built as a **Single-Page Application (SPA)** using pure HTML, CSS, and vanilla JavaScript. There are no external frameworks (like React or Tailwind) and no backend database, ensuring maximum efficiency, offline capability (for the core game), and keeping the repository size well under the 1 MB limit.

### Running the App
1. Simply download or clone this repository, or visit the live GitHub Pages link!
2. Open `index.html` in any modern web browser.
3. To use the "Election Buddy" Chatbot, click the floating robot icon.
4. You can either provide a free Google Gemini API Key when prompted (stored securely in your browser's local storage), OR click **"Simulate Mode"** to test the UI without a key!

## 🤔 Assumptions Made
*   **API Key Management:** We assume the judges reviewing the code have access to their own Gemini API key for testing the assistant. To keep the repository secure, no hardcoded API keys are included in the source code.
*   **Offline First:** We assumed the core educational flow should work entirely offline. Only the Gemini Chatbot and TTS features require an active internet connection.
