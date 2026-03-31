TECHNO FAIL QUIZ

An interactive web quiz about the Polish electronic music scene.


About
A single-page web application built for the Polish techno and electronic music community. No frameworks, no dependencies — pure HTML, CSS and JavaScript.
Deployed on Vercel as a static site.
Stack

Vanilla HTML / CSS / JS
Google Fonts (Bebas Neue, Share Tech Mono, Barlow Condensed)
Vercel (static hosting)

Structure
/
└── index.html    # entire app — single file, no build step required
Deploy
Option A — Vercel CLI
bashnpm i -g vercel
vercel --prod
Option B — GitHub + Vercel UI

Push index.html to a GitHub repository
Import the repository at vercel.com/new
Leave all settings as default → Deploy

Vercel detects the static file automatically. No configuration needed.
Local preview
bash# any static server works, e.g.:
npx serve .
# or just open index.html directly in a browser
Adding questions
Questions live in the QUESTIONS array inside index.html. Each entry follows this shape:
js{
  scenario: "...",   // the setup / context
  prompt: "...",     // the actual question
  answers: [
    {
      text: "...",     // answer label
      icon: "...",     // emoji shown with the riposte
      riposte: "..."   // sarcastic commentary shown after selection
    }
  ]
}
Add an object, save, done.
Fail submission (backend)
The submitFail() function currently logs to console. To collect submissions, replace the log with a call to your preferred backend:

Formspree — drop-in fetch to https://formspree.io/f/{id}
Airtable API — POST to a base table
Any REST endpoint — the payload is plain JSON

License
MIT
