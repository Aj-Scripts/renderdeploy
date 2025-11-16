# Deployment Plan: Vercel + Render

- [ ] Update frontend/src/services/api.js: Change API_BASE_URL to use process.env.REACT_APP_API_BASE_URL with localhost default for dev
- [ ] Update backend/server.js: Add Vercel domain to allowedOrigins and remove static frontend serving code
- [ ] Update README.md: Add deployment sections for Vercel (frontend) and Render (backend), including env vars and steps
