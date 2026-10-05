# Franers website: working guide for Claude

## Who you are working with

The people editing this site (mainly Nour) are not developers. They describe the change they want in plain language and rely on you for everything technical: git, branches, pull requests, running the site locally.

- Explain what you are doing in everyday words. Avoid git and web jargon, or explain it in one short phrase when it can't be avoided.
- Run the commands yourself. Don't ask them to type things in a terminal unless there is no other way (for example, a browser sign-in).
- Ask one clear question when a request is ambiguous rather than guessing at wording or design. Text on this site is business copy, so never invent claims, prices, phone numbers or names.
- Amjad is the technical reviewer. Anything you are unsure is safe goes into the pull request description for Amjad to look at.

## The site

- `index.html` is the whole site: one page containing the HTML, CSS and JavaScript. There is no build step and no dependencies.
- `assets/` holds logos, the brand mark, the favicon and the team photo.
- Hosted on Netlify from the GitHub repo `mtabshi-franers/franers-website`. Every pull request gets its own Netlify preview link; `main` is what goes live.

### Two languages, always

The site is bilingual, English and Arabic (right-to-left). Any visible text exists twice:

- In HTML: `<span class="en">…</span><span class="ar">…</span>` side by side.
- In JavaScript: `T('English','العربية')`, or `[en, ar]` pairs inside the survey definitions.

When text is added or changed, update both languages. If the user gives only one language, draft the other and ask them to confirm the wording before finishing. Check layout changes in both directions, since Arabic flips the page.

### The enquiry form (Netlify Forms): handle with care

Enquiries are how the business gets leads, so a broken form is the costliest mistake possible here.

- Netlify finds the form by reading the static HTML at deploy time: the `<form id="svStatic" name="franers-survey" data-netlify="true" …>` element. Keep that form, its name, its `data-netlify` attribute and the `bot-field` honeypot.
- The survey pop-up (`#svForm`) is built by JavaScript from the `SURVEYS` object and submits with `fetch('/')` using `form-name=franers-survey` (the `FORM_NAME` constant). The name must stay identical in both places.
- All of a visitor's answers are packed into the `message` field as readable text, which is what the team reads. Netlify only keeps fields that are declared in the static form, so if a new answer needs to appear as its own column in Netlify, add a matching `<input type="hidden" name="…">` to `#svStatic`. Never rename or remove `name`, `phone`, `email`, `role`, `survey` or `message`.
- The form cannot be tested locally: submitting on a local preview shows the "could not submit automatically" fallback, which is expected. Real testing happens on the Netlify preview link of the pull request. Tell the user this, and suggest they put "TEST" in the name field so the team can ignore the notification email.
- Email notifications and form settings live in the Netlify dashboard, not in this repo.

## How every change goes

Follow these steps without being asked, and tell the user where you are in them.

1. **Start clean.** Check `git status` first. If there is unfinished work from before, ask the user whether to keep or drop it; never discard it on your own. Then switch to `main`, pull the latest version, and create a new branch with a short descriptive name (for example `update-services-text`). Never commit directly to `main`.
2. **Plan first.** Before editing, describe in plain language what will change and where on the page the user will see it. Mention anything risky or anything they may not have thought of (Arabic version, mobile layout, the form). Wait for their go-ahead. A tiny change such as fixing a typo doesn't need a plan.
3. **Make the change.** Keep it limited to what was asked. Match the existing style of the page; don't reorganise or reformat code that isn't part of the request.
4. **Show it.** Serve the folder locally (for example `python3 -m http.server 8000`) and give the user the link to open, or use the app's preview. Tell them exactly what to look at: the changed section, in English and Arabic, and at phone width.
5. **Send for review.** Once the user is happy, commit, push the branch, and open a pull request against `main`. Write the title and description in plain language: what changed, why, and what to check. Give the user the pull request link to send to Amjad, and remind them the Netlify preview link will appear on that page after a minute or two.
6. **Stop there.** Do not merge the pull request and do not push to `main`. Merging happens on GitHub after Amjad approves, and publishing happens in Netlify.

If the user asks for changes after the pull request is open, add them to the same branch and push again; the pull request and preview update on their own.

## GitHub access

Pushing needs the GitHub CLI (`gh`) signed in on this computer. If `gh auth status` shows it isn't, walk the user through `gh auth login` (GitHub.com, HTTPS, sign in with the browser). They approve it in their browser; they should never type or paste a password or token into the chat. If pushing fails because the repo's remote uses SSH and no key is set up, switch the remote to the HTTPS address and run `gh auth setup-git`.

## Things not to do

- Don't force-push, rewrite history, or delete branches.
- Don't add frameworks, build tools or package managers; the site is deliberately a single file.
- Don't add third-party scripts, trackers or embeds without the user explicitly asking and it being called out in the pull request.
- Don't put passwords, tokens or private contact details in the repo.
