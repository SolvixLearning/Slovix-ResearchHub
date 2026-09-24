# SOLVIX Research Hub

A responsive website for the research initiative within SOLVIX Learning. It includes research guidance, scientific writing, data and methods support, mentorship, workshops, an interactive event calendar and contact channels.

**Ready for GitHub Pages.** This is a static HTML/CSS/JavaScript website: no npm install, build step, database or paid hosting service is required. It preserves the existing Research Hub design and supplied emblem.

## Publish with GitHub Desktop

1. Open your existing SOLVIX repository in GitHub Desktop. If it is not cloned, choose **File → Clone repository → URL**, paste its GitHub URL and choose a local folder.
2. Extract this ZIP. Copy the **contents** of `solvix-research-hub` into your cloned repository folder. `index.html` must be directly in the repository root, not inside another `solvix-research-hub` folder. Include `.nojekyll` and `.gitignore`.
3. If files already exist, inspect differences before replacing them. Do not delete your repository's `.git` folder.
4. In GitHub Desktop, review the changes, enter `Add SOLVIX Research Hub website`, click **Commit to main**, then **Push origin**. Use your repository's actual default branch if it is not `main`.
5. On GitHub, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select **main** and **/(root)**, then **Save**.
6. Wait for deployment to finish. GitHub Pages will display the live website URL in Settings → Pages. A typical project URL is `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`.

GitHub Free supports Pages from public repositories. Other plans support additional repository configurations. Pages is generally a public website; the private ChatGPT preview's access restrictions do not carry over to this copy. Publishing files to GitHub does not publish a website until Pages is enabled.

Official instructions, checked 24 September 2026: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Preview on your PC

For a quick check, double-click `index.html`. For a closer hosting preview, use VS Code's Live Server extension or, with Python installed, run this from the repository folder:

```sh
python -m http.server 8000
```

Then open http://localhost:8000. Press Ctrl+C to stop the server. Fonts use Google Fonts with local sans-serif fallbacks; the core website and images work without external font access.

## Files and editing map

| File | What to change |
| --- | --- |
| `site-config.js` | Services, research topic lists, contact links and event details |
| `app.js` | Hero, mission, vision, section headings, navigation, footer and interactive behaviour |
| `style.css` | Colours, fonts, spacing, sizes, responsive layout and animation |
| `index.html` | Browser title, search description, theme colour and favicon |
| `assets/research-emblem.png` | Current emblem used in the header, hero and browser tab |
| `assets/network.png` | Research background image |
| `.nojekyll` | Keeps the site as plain static files; leave this file present |
| `CUSTOMIZATION.md` | Detailed editing examples and common changes |
| `CHANGELOG.md` | Changes made for this GitHub-ready edition |

## Update the website later

Edit locally → preview → review in GitHub Desktop → commit with a descriptive message → Push origin. GitHub Pages republishes after pushes to the selected source branch.

To undo a published change, use GitHub Desktop's History view, right-click the relevant commit and choose **Revert changes in commit**, then push the new revert commit. Avoid rewriting shared Git history. If several later changes depend on the old change, review the resulting files before pushing.

## Before announcing the site

- Set official contact links in `site-config.js`; empty channels currently explain that details are coming soon.
- The first workshop is planned for 3 November 2026. Confirm its time, delivery format, speakers, fees and registration before changing its status.
- Review mission, vision, service availability and the emblem. No real speaker names or endorsements are claimed.
- Check the page on mobile and desktop, open every contact link and test event details.
- Update the browser description if your scope changes.

This site does not collect form submissions or process payments. Registration links can point to an external booking form or event service. A real login, database, payment flow or email submission service requires additional services; GitHub Pages only hosts static files.

## Troubleshooting

- **404 at the website URL:** Confirm Pages uses the correct branch and root folder and that `index.html` is at that root. Check the Actions tab for deployment errors.
- **Images or CSS missing:** Keep the `assets` folder and relative `./` paths. Filenames are case-sensitive online. Do not replace relative URLs with `/assets/...` for a project site.
- **Blank page after an edit:** Open the browser developer console. Check commas, brackets and quotation marks in `site-config.js`. Restore the last working commit if necessary.
- **Old content still visible:** Confirm Push origin succeeded and deployment finished, then refresh with Ctrl+F5.
- **No events visible:** Navigate to their month and verify ISO dates such as `2026-10-24`. The calendar starts at the earliest upcoming event, or the current month when none remain.
- **Custom domain:** Configure it in Settings → Pages and follow GitHub's DNS guidance. This package does not presume a domain.

## Ownership and assets

The existing SOLVIX emblem and background are copied from the original Research Hub source. No new open-source licence is granted by this package. Confirm your preferred licence and rights to branding/imagery before granting reuse permissions. No credentials, hosting metadata or source-repository history are included.
