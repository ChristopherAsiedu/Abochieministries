# Abochie Ministries

Responsive Astro website for Abochie Ministries, prepared for static deployment on Netlify.

## Local development

```sh
npm install
npm run dev
```

Create a production build with `npm run build`; the static site is written to `dist/`.

## Booking requests (Netlify Forms)

The invitation form at `/bookings/` and general enquiry form at `/contact/` are registered Netlify Forms with required-field validation, consent, and honeypot fields. Netlify stores submissions in the site's Forms area. Their confirmation pages are configured redirects after successful submissions; a local development preview does not save requests.

The live site is `https://abochieministries.netlify.app/`. Form detection is enabled, and the `booking` and `contact` forms are listed in the Netlify Forms dashboard. Email notifications are configured for new submissions from any form and go to the ministry's designated notification email.

Netlify Forms is a managed form-submission inbox, not a general-purpose database. Limit access to the Netlify site dashboard to authorized administrators, set a retention policy appropriate to the ministry, and do not request sensitive information in the form.

## Content management

The `/admin/` area uses Decap CMS with Netlify Identity and Git Gateway. It edits ministry details, event records, music releases, outreach stories, and their uploaded media in the site's Git repository.

Before inviting an editor:

1. Connect the site to its Git repository in Netlify and confirm the production branch is `main` (or update `public/admin/config.yml` to match).
2. Enable Netlify Identity and Git Gateway in the Netlify site settings.
3. Restrict Identity registration to invited users and invite only trusted ministry administrators.
4. Confirm the Git Gateway role is limited to the required repository and branch.
5. Visit `/admin/` on the deployed site and test an edit through the editorial workflow.

Content records live in `src/data/site.json` and `src/content/`. The CMS writes changes to the connected repository; a Netlify build publishes them. Do not add unverified contact details, dates, venue information, music links, or personal biography.

## Before launch

- The supplied official logo is used in the site header, footer, and favicon.
- Add ministry-approved photos and video through the CMS.
- Supply and verify official contact details, social links, and music platform links.
- Review the Netlify Forms privacy/retention settings and configure booking notifications.
- Use an approved domain and add its canonical social-sharing metadata when supplied.
