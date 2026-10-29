# AL HAKAM — Netlify-ready

This project is prepared for deployment on Netlify. The website is built with Vite, and the AI endpoints run as a Netlify Function so the Gemini key stays on the server.

## Deploy (easiest way)
1. Upload this project folder to a GitHub repository.
2. In Netlify, choose **Add new site → Import an existing project** and connect that GitHub repository.
3. Netlify should detect `netlify.toml`. Confirm build command `npm run build` and publish directory `dist`.
4. In **Site configuration → Environment variables**, add `GEMINI_API_KEY` with your Gemini API key.
5. Deploy the site. Your public link will look like `https://your-site-name.netlify.app`.

## Run on your computer
1. Install Node.js (LTS).
2. Run `npm install`.
3. Create `.env` in the project root and add `GEMINI_API_KEY=your_key_here`.
4. Run `npm run dev` to start the full local app. To test the Netlify Function locally, run `npx netlify dev`.

## Important
- Never put your Gemini API key in `src/` or in a `VITE_...` variable. It must be stored in Netlify environment variables.
- The three AI games call `/api/judge/football`, `/api/judge/pose`, and `/api/judge/proverb`; these are routed to the Netlify Function.
- AI model access and API usage depend on your Google AI Studio account and current model availability/quotas.
