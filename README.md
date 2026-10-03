# QuizReel – Quiz Video Maker

Create timed multiple-choice quizzes (4 options), reveal the answer after a countdown,
and record the result as a video. Single static page: no build step, no backend.

## Features
- 4 options per question (A–D), add / edit / delete / shuffle
- Per-quiz timer (seconds to answer) and answer-reveal duration
- Bulk upload from Excel (.xlsx, .xls) or .csv
- Video shapes: 16:9 landscape, 9:16 vertical, 1:1 square
- Three visual themes, custom video title, tick + reveal sounds
- Records canvas + audio to WebM and downloads it

## Excel format
First sheet, first row = headers: `Question | A | B | C | D | Answer`
Answer may be A-D, 1-4, or the exact option text. See `samples/`.

## Run locally
Open `index.html` in Chrome, Edge or Firefox (internet needed for the SheetJS and font CDNs).
Or: `npx serve .`

## Deploy: GitHub + Vercel
1. Create an empty repo on github.com (e.g. `quizreel`).
2. In this folder:
   ```
   git init
   git add .
   git commit -m "QuizReel"
   git branch -M main
   git remote add origin https://github.com/<your-username>/quizreel.git
   git push -u origin main
   ```
3. Go to vercel.com > Add New > Project > import the repo > Deploy.
   Framework preset: Other. Leave build command and output directory empty.
Every `git push` redeploys automatically.

## Notes
- Output is WebM. For MP4 (Instagram, some editors) convert with HandBrake or CloudConvert.
- Recording runs in real time: a 10-question quiz at 10s + 4s takes about 2m22s.
- Keep the tab visible while recording; background tabs throttle rendering.
- Vertical/square layouts show only the question number in the header (title appears on the intro frame).
