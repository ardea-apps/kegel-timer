# Kegel Exercise Timer

A lightweight, mobile-friendly Kegel (pelvic-floor exercise) timer that runs in a web browser. It guides alternating contraction and relaxation periods with a visual countdown and audible cues.

**Current version:** v4.0.0

## Features

- Separate, adjustable **contraction** and **relaxation** durations.
- Adjustable number of contractions; there is no rest period after the final contraction.
- A prominent countdown, current phase, repetition counter, and progress indicator.
- Audible cues for phase changes and session completion, plus a **Test beep** button.
- **Start**, **Pause/Resume**, **Reset**, and **Start again** controls.
- Collapsible exercise settings to give the timer more room on a phone screen; the panel closes when a session starts.
- Settings saved in the browser's local storage for future visits on the same device and site.
- Screen wake-lock support where provided by the browser.
- A standalone HTML file: no external JavaScript libraries or backend are required.

## Default session

| Setting | Default |
| --- | ---: |
| Contraction duration | 10 seconds |
| Relaxation duration | 10 seconds |
| Number of contractions | 10 |
| Relaxation intervals | 9 |
| **Total time** | **3 minutes 10 seconds** |

The total session length is calculated as:

`(contraction seconds × contractions) + (relaxation seconds × (contractions − 1))`

### Adjustable ranges

- Contractions: **1–120 seconds** each
- Relaxation: **1–120 seconds** each
- Number of contractions: **1–100**

## How to use

1. Open the hosted timer in your browser.
2. Optionally expand **Exercise settings** to change the durations or number of contractions.
3. Tap **Test beep** and adjust the device's media volume if needed.
4. Tap **Start**. Follow the **Contract** and **Relax** prompts.
5. Use **Pause**, **Resume**, or **Reset** as needed. To change the settings, reset first.

The timer automatically ends after the last contraction, without a final relaxation interval.

## Run locally

Download or clone the repository, then open `index.html` in a modern browser. On some phones, local `.html` files may open in a document viewer instead of a browser; hosting the page is more convenient.

## Publish with GitHub Pages

1. Place the latest application file at the repository root, named **`index.html`**.
2. In GitHub, go to **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. Once GitHub publishes the site, open the Pages URL on your phone or computer.
5. On iPhone, open the URL in Safari and use **Share → Add to Home Screen** for app-like access.

GitHub Pages requires a repository and settings that support Pages publishing. It may take a short time for a newly configured site to become available.

## Browser and audio limitations

This timer uses the browser's Web Audio API. Mobile browsers, particularly on iOS, can suspend audio or timing when a page is backgrounded or the screen locks. For the most reliable alerts:

- Keep the page visible and your phone screen awake.
- Check media volume and use **Test beep** before exercising.
- If beeps stop, return to the page and tap **Test beep** or restart the session.

The application attempts to keep the screen awake on browsers that support the Screen Wake Lock API; support is not universal and wake locks can be released by the system.

## Version history

| Version | Main change |
| --- | --- |
| **v1.0.0** | Initial timer with fixed 10-second contract/rest intervals and 10 contractions. |
| **v2.0.0** | Improved audio activation and restart behavior; added a test beep. |
| **v3.0.0** | Added adjustable timings, contraction count, automatic duration calculation, and locally saved settings. |
| **v4.0.0** | Added collapsible exercise settings and automatic collapse on Start. |

See [CHANGELOG.md](CHANGELOG.md) for release details.

## Health note

This is a timing aid, not a medical treatment plan. Follow the contraction duration, relaxation duration, repetition count, and exercise technique advised by your clinician or pelvic-floor physical therapist. Stop if exercising causes pain or strain.

## License

No license is specified in this README. If you want others to have explicit permission to reuse, modify, or distribute the code, add a `LICENSE` file to the repository.
