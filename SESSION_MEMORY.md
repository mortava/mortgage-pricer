# Mortgage Pricer - Project Session Memory

## Project Overview
- **Project Name:** Mortgage Pricer (Rate Quote Builder)
- **Location:** C:\Users\beach\mortgage-pricer
- **Created:** 2025-02-01

## Repository & Deployment
- **GitHub Repo:** https://github.com/mortava/mortgage-pricer
- **Vercel Production URL:** https://mortgage-pricer.vercel.app
- **Vercel Project:** james-projects-d94c6754/mortgage-pricer

## Embed URL (G1 Pricing Engine)
```
https://grow.g1wins.com/pricing-engine-embed?key=g1_live_7GnMocrNBm04Rduku-zrlWwgdVn31QdK&borrowerMode=true&leadId=03b54ca8-0a6a-464b-9afd-8176ed3460fb&margin=150
```

## Project Structure
```
mortgage-pricer/
├── index.html          # Main UI with embedded pricing engine + AI chat
├── server.js           # Express server for local development
├── package.json        # Node dependencies
├── vercel.json         # Vercel deployment configuration
├── .gitignore          # Git ignore rules
├── api/
│   ├── chat.js         # Vercel serverless function - proxies AI chat requests
│   └── health.js       # Health check endpoint
└── SESSION_MEMORY.md   # This file
```

## Key Features Implemented
1. **Tabbed Interface**
   - Rate Quote tab: Embedded G1 pricing engine iframe
   - AI Assistant tab: Chat interface for mortgage questions

2. **Iframe Clipping (Header/Footer Hiding)**
   - Used CSS clipping technique to hide embedded iframe header
   - `.iframe-clip-container` with `overflow: hidden`
   - Iframe positioned with `top: -140px` to push header out of view
   - Adjust this value if more/less clipping needed

3. **API Proxy**
   - `/api/chat` - Proxies requests to G1 AI chat API
   - URL: `https://grow.g1wins.com/api/pricing-engine/ai/chat?public=true`

4. **Responsive Design**
   - Mobile-friendly layout
   - Full-screen iframe on all devices

## CSS Clipping Details (for hiding iframe header)
```css
.iframe-clip-container {
  flex: 1;
  position: relative;
  overflow: hidden;
  min-height: 0;
}

.embed-wrapper iframe {
  width: 100%;
  height: calc(100% + 140px);
  border: none;
  position: absolute;
  top: -140px;  /* Adjust this to hide more/less of the header */
  left: 0;
}
```

## Branding
- Logo: "AI TOOLS by G1 GROUP"
- Title: "Rate Quote Builder"

## Commits Made This Session
1. `feat: Add pricing engine embed wrapper with updated UI/UX`
2. `fix: Add embed parameters to hide header/footer in pricing engine iframe`
3. `feat: Clip iframe to hide embedded header/footer, update branding`

## Useful Commands
```bash
# Local development
cd C:\Users\beach\mortgage-pricer
npm start

# Deploy to Vercel
vercel --prod

# Push to GitHub
git add . && git commit -m "message" && git push
```

## API Endpoints Used
- **Lead Capture:** `/api/leads/capture`
- **Pricing Evaluation:** `/api/pricing/evaluate-all`
- **Rate Selection:** `/api/leads/rate-selection-notification`
- **Analytics:** `/api/sdk/analytics`

## Notes
- The iframe clipping technique is a workaround since the G1 embed doesn't support hideHeader/hideFooter params
- Footer is hidden via `display: none` in CSS
- The site auto-deploys on git push (GitHub + Vercel connected)

## Session Date
2025-02-01
