# BoardReady — CBSE Class 10 Competency Practice

A responsive static website for chapter-wise CBSE Class 10 practice. Built with HTML, CSS, JavaScript and a JSON question bank; designed for GitHub Pages.

## Features
- Chapter-wise question bank with subject, chapter, question type, difficulty and keyword filters
- Instant MCQ checking with explanations
- Timed mock tests with score and answer review
- Mistake notebook
- Printable worksheets with optional separate answer key (print or Save as PDF)
- Search across questions, chapters, options and explanations
- Browser-local progress tracking (attempts, accuracy, saved mistakes and theme)
- Responsive layout and dark mode
- No build tools or paid hosting required

## Run locally
Because the site loads JSON using `fetch()`, open it through a local web server rather than double-clicking `index.html`.

With Python installed:
```bash
python -m http.server 8000
```
Then visit `http://localhost:8000`.

## Publish with GitHub Pages
1. Create a GitHub repository, e.g. `cbse-competency-practice`.
2. Upload all files and folders in this project to the repository root. Keep `questions/questions.json` in the same relative path.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Choose branch `main` and folder `/ (root)`, then save.
6. Wait for deployment and open the URL shown in Settings → Pages.

## Add more questions
Edit `questions/questions.json`. Each question uses this shape:
```json
{
  "id": "MATH-CHAPTER-001",
  "subject": "Mathematics",
  "chapter": "Coordinate Geometry",
  "type": "application",
  "difficulty": "medium",
  "marks": 2,
  "question": "Write an original question here.",
  "options": ["Option A", "Option B", "Option C", "Option D"],
  "answer": 1,
  "explanation": "Explain why the answer is correct."
}
```
- `id` must be unique.
- `answer` is zero-based: `0` = A, `1` = B, `2` = C, `3` = D.
- Supported question types in the filters: `application`, `case-based`, `reasoning`.
- Supported difficulty levels: `easy`, `medium`, `hard`.
- The current sample bank contains original illustrative practice questions, not an exhaustive CBSE question bank. Expand it chapter by chapter and verify every answer.

## Important limitations
- Progress is saved in the current browser on the current device; it does not sync across devices.
- The site currently uses multiple-choice questions. Descriptive answers, teacher/admin uploads, secure accounts and shared leaderboards would need further development and a backend.
- Do not put API keys or secrets in frontend files. GitHub Pages serves client-side code publicly.
- This is an independent study project and is not affiliated with or endorsed by CBSE. Use original questions and respect the permissions for any external source material.
