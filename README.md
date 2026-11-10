# StudyPilot AI
Personalized AI-assisted study planning for students. Organise a syllabus, build an editable study plan, practise with topic-based quizzes and track real learning activity.

## MVP status
This repository contains an initial full-stack MVP foundation. Configure credentials and run the verification steps before presenting it as tested or deployed. Gemini features require a server-side API key. Local JSON persistence is used unless Firestore is configured.

## Stack
React, Vite, Tailwind CSS, React Router, Lucide React, Node.js, Express, Google Gemini API and Firebase Admin/Firestore.

## Run locally
Requirements: Node.js 20+.
```bash
npm install
npm --prefix client install
npm --prefix server install
cp server/.env.example server/.env
# Add GEMINI_API_KEY to server/.env for AI features
npm run dev:server
# In another terminal:
npm run dev:client
```
Open http://localhost:5173.

## Environment
See [server/.env.example](server/.env.example). Never expose Gemini or Firebase credentials in frontend variables.

## Architecture
React client -> Express REST API -> Gemini service and data repository. Firestore is user-scoped; local JSON is for development. The demo `x-user-id` header is NOT authentication. Add Firebase Authentication token verification and Firestore security rules before public deployment.

## Current scope and limitations
- Subject/topic management, deterministic time-capped study planning, Gemini topic-based quiz generation, quiz scoring and progress endpoints.
- Syllabus text analysis endpoint accepts extracted text. PDF binary upload and OCR are not included yet.
- Firestore adapter is optional; local JSON is the default.
- No authentication, deployment or end-to-end browser test suite yet.
- Add genuine screenshots after running the application. Do not claim tests passed unless executed.

## Testing
`npm test` in the server directory runs planner unit tests. Manually verify subject creation, topic completion, plan generation, quiz submission and progress with credentials configured.

## Future work
PDF extraction and human review, Firebase Authentication, spaced repetition, weekly activity analytics, accessibility and E2E tests.

## Authors
Add verified contributor names, GitHub handles and actual contribution details.
