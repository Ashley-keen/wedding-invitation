# Wedding Invitation Site

🔗 **[Live demo]([https://your-site-name.netlify.app](https://wedding-invitation-demo-abc.netlify.app/))**

A single-page wedding invitation and RSVP site, built from scratch with plain HTML, CSS and
JavaScript. No frameworks, no build step, no dependencies — open the HTML file and it runs.

Guests land on an invitation card, enter the password printed on their physical invite, and get
access to the venue details, a running order for the day, an FAQ accordion and an RSVP form that
posts responses straight to the couple's inbox.

> **Note:** this repository contains a demo version with placeholder names, dates and contact
> details. The live site used for real guests is not published here.

## Features

- **Gated entry screen** — a cover card that hides the page contents until a password is entered
- **Invitation hero** — stamp-and-wax-seal styling, with names, date, time and venue
- **Details cards** — venue address with a Google Maps link, plus accommodation booking info
- **Timeline** — a vertical running order of the day (ceremony, cocktail hour, reception)
- **FAQ accordion** — click to expand; opening one question closes the others
- **RSVP form** — attendance, party size, a conditional second-guest name field, dietary
  requirements and a free-text message, submitted via [Formspree](https://formspree.io) with an
  inline success state
- **Responsive** — a mobile breakpoint at 540px

## Built with

- HTML5
- CSS3 — custom properties for the sage/gold/cream palette, flexbox, `clamp()` for fluid type
- Vanilla JavaScript — DOM manipulation, `fetch` for form submission
- Formspree for form handling

Typefaces are *Great Vibes*, *Cormorant Garamond* and *EB Garamond*.

## Running it locally

Clone the repo and open the file:

```bash
git clone https://github.com/Ashley-keen/wedding-invitation.git
cd wedding-invitation
open index.html          # macOS
# start index.html       # Windows
# xdg-open index.html    # Linux
```

Or serve it over HTTP, which more closely matches how it behaves when deployed:

```bash
python3 -m http.server 8000
```

Then visit <http://localhost:8000>.

The demo password is `password`.

## Configuration

Everything configurable lives at the bottom of `index.html`:

| What | Where | Change it to |
|------|-------|--------------|
| Site password | `const SITE_PASSWORD` | Whatever is printed on the invitations |
| RSVP destination | the `fetch()` URL in `submitRsvp()` | Your own Formspree endpoint |

Names, dates, venue, FAQ answers and contact numbers are all plain text in the markup — search and
replace them directly.

## A note on the password

The password check runs entirely in the browser, so it keeps the page tidy rather than genuinely
private: anyone who opens developer tools can read the password and reveal the hidden content. That
was an acceptable trade-off here — the aim was to stop the details being stumbled upon, not to
defend against anyone determined. Real access control would need a server.

## Deploying

The site is static, so anything that serves files will host it — GitHub Pages, Netlify, Cloudflare
Pages. For GitHub Pages: **Settings → Pages → Deploy from a branch → `main` / root**.

## Licence

[MIT](LICENSE)
