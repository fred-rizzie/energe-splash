# EnergE splash page (energe.app)

Static, single-page site. No build step.

```
index.html            page, styles, and scripts
favicon.ico
apple-touch-icon.png
assets/wordmark.svg   Signal Cyan wordmark for dark backgrounds
assets/icon.svg       cyan E on navy
assets/og-image.png   1200×630 link-preview image
```

## 1. Connect the waitlist (Formspree, about 3 minutes)

1. Create a free account at formspree.io and click **New Form**. Name it "EnergE waitlist" and use your email for notifications.
2. Copy the form ID, the part after `/f/` in the endpoint (for example `xyzabcde`).
3. In `index.html`, replace `YOUR_FORM_ID` with that ID. It appears once, in the `<form action="…">` line.
4. Under the form's **Settings**, add `energe.app` to allowed domains. This blocks submissions from other sites.

Sign-ups arrive by email and are listed in the Formspree dashboard, where you can export them as CSV. The free tier allows 50 submissions a month.

Spam protection: the form includes a hidden `_gotcha` honeypot field, which Formspree drops automatically.

## 2. Move over existing sign-ups

If the current v0 site collected emails, export them from wherever it stored them (Vercel, Supabase, or v0's form integration) **before** you replace the deployment.

## 3. Deploy

**Vercel (where energe.app lives today):** create a new project, upload or import this folder with Framework Preset set to "Other" and no build command, then open **Domains** and move `energe.app` from the old v0 project to this one.

**Netlify or Cloudflare Pages** also work: drag the folder in and point the domain at it.

## Test after deploying

- Submit a real email. You should see "You're on the list…" and a notification email from Formspree.
- Paste `https://energe.app` into LinkedIn's Post Inspector to check the link preview.
