# Publishing the Blog Update

1. Download and extract this update ZIP.
2. Review the files and compare the updated HTML/CSS with your repository.
3. Copy the updated files into the repository root, preserving the `blog/` and `css/` folders.
4. Preview locally:

   ```bash
   python3 -m http.server 8000
   ```

   Open `http://localhost:8000`.

5. Verify navigation on Home, About, Projects, Certifications and Blog.
6. Check the mobile layout and all article links.
7. Commit and push:

   ```bash
   git add index.html about.html projects.html certifications.html css/style.css blog README.md PUBLISHING.md
   git commit -m "Add portfolio blog navigation and article pages"
   git push origin main
   ```

   If your default branch is not `main`, use the correct branch.

The new articles are starter drafts. Review and sanitise them before publishing as finished technical content.
