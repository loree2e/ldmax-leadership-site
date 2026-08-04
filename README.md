# LD Max Leadership — Website

The website for LD Max Leadership (ldmaxleadership.com), built as a single self-contained HTML file. No build step, no dependencies, no hosting fees.

## Files

- `index.html` — the entire site (content + styles in one file)
- `assets/loree-headshot.jpg` — primary headshot (navy blazer, smiling)
- `assets/loree-headshot-alt.jpg` — alternate headshot (pink blazer)
- `MIGRATION-GUIDE.md` — step-by-step plan for leaving Squarespace
- `ANNOUNCEMENT-DRAFTS.md` — LinkedIn + newsletter drafts for the launch

## To edit

Open the project in Claude Code and describe the change, or edit `index.html` directly. To preview locally, ask Claude Code to "run the ldmax site" (a dev server config named `ldmax-site` is set up).

## Deployment (live setup)

- Repo: https://github.com/loree2e/ldmax-leadership-site
- Hosting: GitHub Pages (main branch, root), custom domain ldmaxleadership.com
- Domain: registered at Hover; DNS points apex A records to GitHub Pages IPs, www CNAME to loree2e.github.io
- To publish changes: commit and push to main; live in about a minute

## Before launch checklist

- [ ] Buy ldmaxleadership.com (verified available as of Aug 4, 2026)
- [ ] Swap the contact email in `index.html` from loreedraude@gmail.com to loree@ldmaxleadership.com once domain email is set up (search for "mailto:")
- [ ] Confirm the LinkedIn URL in the site footer and contact section is correct
- [ ] Review all copy, especially the About section and stats
- [ ] Optional: add client testimonials when you have permission to use names
- [x] Team section: linked to daysixleadership.com — still confirm they're comfortable being named before launch
- [ ] Optional: name individual coaches on the bench (photo + 2-line bio each) once you've confirmed who's in and gotten their OK
