# SALSA WebAR

Web-based AR (A-Frame + AR.js) that overlays a dancing lady and Mexican music when the SALSA marker is detected.

## Run locally

```bash
npm install
npm run start
# open http://localhost:8080
```

Serve over HTTPS on real devices (recommended) or use a tunneling tool.

## Assets

- Put your marker pattern at `public/assets/markers/salsa.patt`.
- Put the animated GLB at `public/assets/models/dancer.glb`.
- Put the audio track at `public/assets/audio/mariachi.mp3`.

## Make the SALSA marker

Use the AR.js marker generator:
- https://ar-js-org.github.io/AR.js-Docs/marker-based/
- Upload a high-contrast image showing the word SALSA
- Export `.patt` and place as `public/assets/markers/salsa.patt`

## Accessibility

- On-screen controls: Start AR, Mute/Unmute, Restart
- Caption line communicates state

## Deploy

Any HTTPS static hosting works (GitHub Pages, Netlify, Vercel, S3/CloudFront).

1. Upload `/public` contents
2. Ensure `index.html` is at the site root
3. Verify camera permission prompt and AR works

## Testing checklist

- iPhone Safari and Chrome: camera opens, marker detected, audio plays after tap
- Android Chrome and Edge: camera opens, marker detected, audio plays
- Marker lost pauses/hides content and stops audio
- Mute/Unmute and Restart buttons work
- Performance: model loads fast (<3–5s on 4G), steady FPS
- Accessibility: captions visible, buttons focusable and large enough

