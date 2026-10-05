# How to change the Franers website with Claude

You describe what you want in plain words; Claude does the technical work. The website folder contains a file called `CLAUDE.md` that Claude reads automatically, so it already knows the rules of the site and the steps below. You don't need to save or paste any instructions yourself.

Nothing you do with Claude can break the live site. Changes only go live after Amjad approves them and they are published in Netlify.

## One-time setup

1. Open the Claude desktop app and switch to the **Code** tab (not the normal chat).
2. Choose the website folder, `franers-website`, as the folder to work in.
3. Tell Claude: *"Check that I'm signed in to GitHub, and help me sign in if I'm not."*
   A browser window opens and you approve the sign-in there. Never type your GitHub password into the chat.

## Every time you want a change

### 1. Ask
Start a new conversation for each new change, and describe what you want. Be specific about where on the page and what the text should say. Screenshots help.

> "In the Services section, change the title of the third card to '…'. Here is the Arabic: '…'."

The site is in English and Arabic. Give Claude both versions if you have them; otherwise it will draft the other language and ask you to confirm.

### 2. Check the plan
Claude tells you what it is going to change before it touches anything. Read it. If something is off, say so. Good questions to ask:

> "Is there anything risky about this? Anything I haven't thought of?"

For bigger visual changes you can also ask: *"Show me a mockup before you build it."*

When the plan looks right, tell it to go ahead.

### 3. Look at the result
Claude gives you a link to open in your browser (it starts with `localhost`). This is a private copy on your computer only. Check:

- the part you changed
- the Arabic version (use the language button)
- how it looks on a phone (make the browser window narrow)

The enquiry form does not send from this private copy; it will show a "could not submit" message. That's normal. You test the form in step 5.

Not happy? Tell Claude what to fix and look again. Repeat until it's right.

### 4. Send it for review
Tell Claude:

> "I'm happy with it. Send it for review."

Claude gives you a link to a GitHub page called a pull request. Send that link to Amjad.

### 5. Test the preview (for bigger changes, and anything touching the form)
A minute or two after step 4, a Netlify preview link appears on the pull request page ("Deploy Preview"). It is a real online copy of the site with your change that the public can't find.

If you changed anything about the form, submit it once here and write **TEST** as the name, so the team knows to ignore the email.

### 6. Go live
1. Amjad approves the pull request.
2. On the pull request page, click **Merge pull request**.
3. Open Netlify, go to the Franers project, open **Deploys**, and wait for the newest one to finish.
4. If it isn't already marked as published, open it and click **Publish deploy**.
5. Open franers.com and check your change is there.

## If something goes wrong

- **Claude seems confused or stuck:** start a new conversation and say *"Check the state of the project and tell me in simple words where things stand."*
- **You changed your mind halfway:** say *"Undo everything from this conversation that hasn't been sent for review."*
- **Something is wrong on the live site after publishing:** in Netlify, open **Deploys**, pick the previous deploy, and click **Publish deploy**. The site goes back to how it was. Then tell Amjad.
- **Anything else:** send Amjad a screenshot.
