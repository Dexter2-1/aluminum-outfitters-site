# Aluminum Outfitters — Setup Guide

This site now has a real admin panel at `/admin` that lets you add, edit, and
delete products (with photos) and have the changes show up for every visitor
— not just your own browser.

It works by storing your product list in `data/products.json`. The admin
panel edits that file and saves the change to your GitHub repo. Netlify
automatically rebuilds and redeploys the site every time that happens.

## One-time setup (about 10–15 minutes)

### 1. Push this folder to GitHub
- Create a new repository on GitHub (e.g. `aluminum-outfitters-site`)
- Upload all the files in this folder to it (you can drag-and-drop them on
  GitHub's "Add file → Upload files" page, or use git if you're comfortable
  with it)

### 2. Connect the repo to Netlify
- In Netlify, go to **Add new site → Import an existing project**
- Choose GitHub, then select your new repository
- Leave the build settings empty (no build command, publish directory `/`)
  since this is a plain static site
- Click **Deploy**

### 3. Turn on Netlify Identity
- In your new Netlify site, go to **Site configuration → Identity**
- Click **Enable Identity**
- Under **Registration**, set it to **Invite only** (so random people can't
  sign up as admin)

### 4. Turn on Git Gateway
- Still in Identity settings, scroll to **Services → Git Gateway**
- Click **Enable Git Gateway**

### 5. Invite yourself as an admin user
- Go to the **Identity** tab for your site → **Invite users**
- Enter your own email address
- Check your email and click the invite link — it will ask you to set a
  password

### 6. Log in to the admin panel
- Go to `https://yoursite.netlify.app/admin`
- Log in with the account you just created
- You'll see a "Shop Products" section — open it, and you can add, edit, or
  delete products there, including uploading photos

That's it — from here on, you (and only people you invite) can manage the
shop directly from `/admin`, and changes go live automatically within a
minute or two of saving.

## Notes
- `data/products.json` is the single source of truth for the shop. The admin
  panel edits it through GitHub automatically — you never need to touch it
  by hand.
- If you ever want to add a second admin user (e.g. an employee), just
  invite their email the same way in step 5.
- Checkout still works by emailing order details to
  aluminumoutfittersshop@gmail.com — no payment processing is set up.
