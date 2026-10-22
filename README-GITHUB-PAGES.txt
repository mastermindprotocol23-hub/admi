GITHUB PAGES — ADMIN PANEL PACKAGE

WHAT THIS FIXES
- Publishes adminn.html from the repository root and checks that it exists before deployment.
- If the repository has no index.html, creates a temporary homepage in the deployment artifact that opens adminn.html. This prevents a blank/root GitHub Pages 404 without changing your repository files.
- If the repository already has index.html, it is preserved so your public website is not overwritten.
- Includes a GitHub Pages 404 fallback that points unknown paths to the admin panel.
- Does not edit adminn.html, Firebase configuration, Firestore logic, or backend code.

INSTALL
1. Extract this ZIP.
2. Copy the adminn.html file and the .github folder into the ROOT of your existing GitHub repository. Keep existing website files and assets.
3. Make sure the file is named exactly adminn.html (all lowercase) and sits beside index.html, if your repo has one.
4. Commit and push to the main branch. If your main branch has a different name, change "main" in .github/workflows/deploy-pages.yml.
5. On GitHub, open Settings -> Pages -> Build and deployment -> Source and select "GitHub Actions".
6. Open the Actions tab. Wait for "Deploy admin panel to GitHub Pages" to succeed. If it fails, open the run and read the validation error.

OPEN THE PANEL
- Project Pages: https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/adminn.html
- If your repo did not already contain index.html, the site root will also forward to the admin panel.
- If your repo already has index.html, that public homepage stays as-is; use the /adminn.html URL for the admin panel.

IMPORTANT BACKEND NOTE
GitHub Pages hosts static files; it does not host a server/backend. The existing Firebase setup is left untouched, so Firebase-backed features can still connect if its configuration and Firebase security rules allow them. Any requests to server endpoints such as /api/... still require that endpoint to be hosted separately; this package does not create or modify a backend.
