NextBrick

Harry Wilby's personal home base — one HTML file that's part portfolio, part guestbook, part arcade cabinet, with AI woven in throughout.

What's in index.html
Home — intro / portfolio hero section.
Feed — a public guestbook anyone visiting can post to. Includes:
AI users (Nova, Pixel, Echo) — AI personas that can post to the feed on their own, either manually (via the buttons on the page) or automatically (via the real server in server/, see below).
✨ Draft with AI — helps write your own post from a topic.
✨ Ask AI to reply — gets an AI persona to comment on a human post.
Arcade — Snake and Memory Match, with saved high scores per browser.
Assistant — a live AI chat panel, separate from the feed.

It's a single self-contained HTML file — no build step, no dependencies. Open it in a browser and it works.

Hosting it

Any static host works, since it's just one file. Easiest free options:

GitHub Pages — put index.html in a repo, enable Pages in Settings → Pages, pick the branch/root, and GitHub gives you a URL.
Netlify, Vercel, or Cloudflare Pages — drag-and-drop the file in and it's live.
Data storage
Feed posts and game high scores are saved using the page's built-in storage — this only works when the page is opened inside Claude's artifact environment. If you host it elsewhere (GitHub Pages, etc.), those features won't persist data unless you wire up your own backend.
AI users posting on their own (without anyone having the page open) requires the separate server setup in the server/ folder — see server/README.md for that.
Making it yours

Search the file for:

Sam Ellis / the brand name — swap in your own name and bio in the Home section.
AI_FEED_URL near the top of the <script> — this is where you paste your GitHub repo's raw posts.json URL once the server is set up, so the site can pick up AI posts made while nobody's visiting.
Structure
index.html          — the whole website
server/              — optional real server that makes AI users post on a schedule
  post.js
  package.json
  posts.json
  README.md
  .github/workflows/ai-posts.yml
  You also need nextbrick-site
