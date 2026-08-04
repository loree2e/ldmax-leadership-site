# Owning Your Websites: The Squarespace Exit Guide

## The big picture

Squarespace bundles three separate things into one monthly bill:

1. **Domain registration** (owning the name, e.g. loreedraude.com)
2. **Hosting** (a computer that serves your site to visitors)
3. **Site builder** (the drag-and-drop editor)

The plan is to separate them so you control each piece:

| Piece | Where it goes | Cost |
|---|---|---|
| Domains | A registrar you control (Cloudflare, Porkbun, or Hover) | ~$11–18/yr per domain |
| Hosting | Cloudflare Pages or GitHub Pages | **$0** |
| The site itself | Plain HTML files in a git repository on your Mac | $0 |

Your sites become ordinary files that you own forever. Editing = change the file, push, live in under a minute. Claude Code can make any edit for you. Compare that to roughly $200–300/yr **per site** on Squarespace.

---

## Step 1 — Buy ldmaxleadership.com (verified available Aug 2026)

Yes, you need to buy it at a registrar. Three good options:

- **Cloudflare Registrar** — at-cost pricing (~$11/yr, no markup, renewals never spike). Best choice if you also host on Cloudflare Pages, because domains + DNS + hosting live in one free dashboard. This is my recommendation.
- **Porkbun** — ~$11/yr, friendly, no upsells.
- **Hover** — ~$18/yr, the nicest interface, great support. Totally fine if you prefer it.

Note for Cloudflare: create the free account first, add the domain via "Register a domain." Their registrar requires using their DNS, which is what we want anyway.

## Step 2 — Put the new site live (no Squarespace involved)

The site is ready at `~/ldmax-leadership-site`. To deploy:

1. Create a free GitHub account (github.com) if you don't have one.
2. Create an empty repository named `ldmax-leadership-site`.
3. In Terminal (or ask Claude Code to run these):

```bash
cd ~/ldmax-leadership-site
git init
git add .
git commit -m "LD Max Leadership site v1"
git remote add origin https://github.com/loree2e/ldmax-leadership-site.git
git push -u origin main
```

4. In Cloudflare: **Workers & Pages → Create → Pages → Connect to Git**, pick the repo, no build settings needed (it's plain HTML), deploy.
5. In the Pages project: **Custom domains → add ldmaxleadership.com.** Since the domain is already at Cloudflare, this is one click.

Site is now live, free, with automatic HTTPS. Every future `git push` updates it.

## Step 3 — Archive your Squarespace content (do this soon, regardless)

Two complementary moves:

- **Squarespace's export**: Settings → Advanced → Import & Export → Export. Gives you an XML file of pages and blog posts. Text only; images are not included.
- **A full mirror** of each site as browsable HTML (ask Claude Code to run this):

```bash
cd ~/Documents && mkdir -p site-archives && cd site-archives
wget --mirror --convert-links --page-requisites --no-parent https://loreedraude.com
wget --mirror --convert-links --page-requisites --no-parent https://encausetch.com
wget --mirror --convert-links --page-requisites --no-parent https://ifeeltheneedshow.com
```

Now nothing is hostage to Squarespace, whatever you decide later.

## Step 4 — Rebuild the other sites (one at a time, no rush)

Same pattern as LD Max: one folder, one repo, one free Pages project each.

- **ifeeltheneedshow.com** — likely a one-pager; an afternoon's work.
- **encausetch.com** — gallery site; static HTML handles image galleries beautifully.
- **loreedraude.com** — decide its future role: keep as the personal/speaker/author hub, with coaching and organizational work pointing to ldmaxleadership.com. (loredraudecoaching.com already just redirects to it, so that domain can simply redirect to the new site instead.)

## Step 5 — Transfer the existing domains

Once the rebuilt sites are live on Pages:

1. In Squarespace: Domains → select domain → unlock transfer → copy the auth/EPP code.
2. At the new registrar: "Transfer a domain," paste the code. Costs about one year's renewal (~$11) and adds a year to the registration. Takes up to 5–7 days.
3. **Before switching**, screenshot every DNS record. If any domain handles email (Google Workspace MX records, email forwarding), recreate those records at the new DNS first. This is the one step where care matters; get it wrong and email bounces until fixed.

## Step 6 — Cancel Squarespace

Only after every site is rebuilt, live on its domain, and email verified working. Then downgrade/cancel each Squarespace site subscription. Keep the archives from Step 3.

## Sequencing summary

1. **This week**: buy ldmaxleadership.com, deploy the new site, announce.
2. **Soon**: archive all three Squarespace sites.
3. **Next month or two**: rebuild show + art sites, decide loreedraude.com's role.
4. **Then**: transfer domains, flip DNS, cancel Squarespace.

Nothing breaks at any point: the old sites keep running until each new one is proven.
