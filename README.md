[README.md](https://github.com/user-attachments/files/33488874/README.md)
# Wedding Invitation Templates

Three animated, mobile-friendly digital wedding invitation websites written in Bahasa Melayu. Guests open a virtual envelope, see the event details and a live countdown, send an RSVP, leave wishes and, in some templates, claim gifts from a registry or scan a QR code.

Built with plain **HTML, CSS and JavaScript**. There is no framework and no build step. Google Sheets and Google Apps Script act as a lightweight backend.

<!-- Add screenshots here, for example:
<p align="center">
  <img src="docs/screenshots/template1.png" width="220" alt="Template 1" />
  <img src="docs/screenshots/template2.png" width="220" alt="Template 2" />
  <img src="docs/screenshots/template3.png" width="220" alt="Template 3" />
</p>
-->

**Live demo:** _add your GitHub Pages link here_

## Templates

| | Template 1 | Template 2 | Template 3 |
|---|---|---|---|
| Look | Photo background with sakura details | Looping video background | Looping video background with cloud details |
| Envelope intro | Yes | Yes | Yes |
| Countdown | Yes | Yes | Yes |
| RSVP and contact | Yes | Yes | Yes |
| Guest wishes | Yes | Yes | Yes |
| Gift registry with claiming | Yes | No | No |
| Bank QR code | No | Yes | No |
| Background music toggle | Yes | Yes | Yes |

## Features

- **Envelope-opening intro:** a video envelope with an interactive wax seal button that opens the invitation.
- **Live countdown** to the event date and time.
- **Scroll animations** using [AOS](https://github.com/michalsnik/aos).
- **Event details** with a link to Google Maps.
- **RSVP and contact page** with one-tap WhatsApp links to the hosts.
- **Guest wishes wall:** messages are read live from a published Google Sheet, so new wishes appear without redeploying the site.
- **Gift registry (Template 1):** guests browse items, claim one with their name, and the claim is saved through a Google Apps Script web app. A link to the shop is shown for each item.
- **Background music** with a floating on and off button.

## Tech stack

| Area | Technology |
|---|---|
| Front end | HTML5, CSS3, vanilla JavaScript |
| Animation | CSS keyframes, AOS, `IntersectionObserver`, video backgrounds |
| Backend | Google Apps Script web app, published Google Sheets (CSV) |
| Fonts | Google Fonts (Cormorant Garamond, Montserrat, Kaushan Script) |

## Project structure

```
Template1/   Sakura theme with gift registry
Template2/   Video background with bank QR code
Template3/   Video background with cloud details
```

Each folder is self-contained: `index.html` plus its own images, videos and audio.

## Run locally

No installation is needed. Open a template's `index.html` in a browser. For the best result, serve the folder so that video and audio load correctly:

```bash
cd Template1
python -m http.server 8000
```

Then open `http://localhost:8000`. Browsers block autoplay audio until the guest taps, so the music starts after the envelope is opened.

## Customise a template

Edit `index.html` in the template you want to use:

1. **Names, parents and event details:** change the text in the hero, couple and event sections.
2. **Photos:** replace `bride_placeholder.png` and `groom_placeholder.png` with your own photos.
3. **Countdown:** change the date in `targetWeddingTimestamp`, for example `new Date("August 30, 2026 11:00:00")`.
4. **Contacts:** replace the `wa.me` WhatsApp links with your own numbers.
5. **Location:** replace the Google Maps link.
6. **Music:** replace the `<source>` inside the `<audio>` tag with your own audio file.
7. **Wishes:** create a Google Sheet, publish it as CSV, and set `googleSheetCsvUrl` to its link.
8. **Gift registry (Template 1):** deploy a Google Apps Script web app connected to a sheet and set `giftDatabaseUrl` to its URL. Edit the `irfanGiftsData` list for your items.
9. **Bank QR (Template 2):** replace `qrbank.png` with your own QR code.

> **Before you publish:** the repository ships with placeholder content. Use only photos, music and QR codes you have the right to share, and do not commit real phone numbers or bank details to a public repository.

## Deploy for free

1. Push this repository to GitHub.
2. Go to **Settings, then Pages**, choose the `main` branch and the root folder, and save.
3. Your templates will be available at `https://<your-username>.github.io/Wedding-Invitation-Templates/Template1/`, and the same for `Template2` and `Template3`.

## Author

**Uthman 'Affan** · Computer Science (Multimedia Computing), UTHM
[GitHub](https://github.com/uthmanaffan4578-dot) · [LinkedIn](https://linkedin.com/in/uthman-affan)
