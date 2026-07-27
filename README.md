# MedTech Training & Certificate System — Prototype

A web-based training and certification platform that helps healthcare workers in Rwanda and Africa learn to correctly operate medical diagnostic equipment (ultrasound, X-ray, laboratory analyzers), complete quizzes, and earn certificates.

This is a **front-end prototype**: plain HTML, CSS, and JavaScript, with `localStorage` acting as the database (no backend/server required). It implements the functional requirements from the SRS:

- **FR1/FR2** — User registration and login (learner or administrator role)
- **FR3** — Course catalog and enrollment
- **FR4** — Training videos and module materials
- **FR5** — Quizzes with scoring
- **FR6** — Auto-generated, downloadable certificates on passing (≥70%)
- **FR7** — Progress tracking dashboard
- **FR8** — Admin course management (create/edit/delete courses)

## How to run it locally

No installation, build step, or dependencies are required.

1. Download or clone this repository.
2. Open the folder in your file explorer.
3. Double-click `index.html` to open it in your browser (Chrome or Edge recommended).
   - Or, for the best experience, serve it with a simple local server so relative paths and video playback behave consistently:
     ```
     # from inside the project folder
     python3 -m http.server 8000
     ```
     then visit `http://localhost:8000` in your browser.
4. Create an account on the **Create account** tab (choose "Doctor / Healthcare worker" or "Administrator").
5. Log in, browse **Courses**, enroll, mark modules complete, take the quiz, and view/download your certificate.
6. Log in as an **Administrator** account to see **Manage courses** in the sidebar, where you can add, edit, or delete courses.

## Deploying it publicly (for submission)

Since this is a static site, you can deploy it for free with **GitHub Pages**:

1. Push this project to a public GitHub repository.
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment," set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save. GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/`.
5. Use that URL as your public product link.

## Project structure

```
medtech/
├── index.html          # Landing page + login/signup
├── dashboard.html       # Learner dashboard, progress tracking
├── courses.html         # Course catalog
├── course.html          # Course detail: video, modules, enroll
├── quiz.html             # Quiz + scoring
├── certificate.html     # Certificate view/download (canvas-generated)
├── certificates.html    # List of all earned certificates
├── admin.html            # Admin: create/edit/delete courses
├── css/
│   └── style.css         # Design system
└── js/
    ├── store.js           # Data layer (localStorage-backed)
    └── shell.js            # Shared sidebar/app shell
```

## Notes on this prototype

- Data (users, enrollments, courses) is stored in the browser's `localStorage`, so it is per-browser/device and resets if browser storage is cleared. A production version would replace `js/store.js` with real API calls to a backend and database.
- Course videos use a placeholder public sample video file for demo purposes; production would host the actual equipment-training footage per module.
- Passwords are stored in plain text in `localStorage` for prototype simplicity only — never do this in a production system.