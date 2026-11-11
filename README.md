# Kegel Exercise Timer

A lightweight, mobile-friendly Kegel (pelvic-floor exercise) timer that runs in a web browser. It guides alternating contraction and relaxation periods, in one or two sets (slow and fast), with a visual countdown and audible cues.

**Current version:** v6.0.0

## Features

- Two exercise sets: **Set 1 — slow contractions** and **Set 2 — fast contractions**, each with its own adjustable contraction duration, relaxation duration, and number of contractions.
- Three exercise modes: **Both sets**, **Slow only**, or **Fast only**.
- Adjustable **recovery** period between the two sets (0 means no break); it applies only in Both sets mode.
- Automatic transitions between sets and phases, with distinct audio cues for the recovery period and the start of the fast set.
- No rest period after the final contraction of a set.
- A welcome screen explaining the timer, with a "Don't show this again" option and an **About this timer** button to reopen it.
- A prominent countdown, current phase, repetition counter, and progress indicator.
- Audible cues for phase changes and session completion, plus a **Test beep** button.
- **Start**, **Pause/Resume**, **Reset**, and **Start again** controls.
- Collapsible exercise settings to give the timer more room on a phone screen; the panel closes when a session starts.
- Settings saved in the browser's local storage for future visits on the same device and site.
- Screen wake-lock support where provided by the browser.
- A standalone HTML file: no external JavaScript libraries or backend are required.

## Default session

Default mode: **Both sets**.

| Setting | Set 1 (slow) | Set 2 (fast) |
| --- | ---: | ---: |
| Contraction duration | 10 seconds | 2 seconds |
| Relaxation duration | 10 seconds | 2 seconds |
| Number of contractions | 10 | 10 |
| Relaxation intervals | 9 | 9 |
| Set duration | 3 min 10 sec | 38 sec |

Recovery between sets: 30 seconds. **Total time: 4 minutes 18 seconds.**

The length of each set is calculated as:

`(contraction seconds × contractions) + (relaxation seconds × (contractions − 1))`

### Adjustable ranges

- Contractions: **1–120 seconds** each (per set)
- Relaxation: **1–120 seconds** each (per set)
- Number of contractions: **1–100** (per set)
- Recovery between sets: **0–600 seconds**

## How to use

1. Open the hosted timer in your browser. On first use, read the welcome screen and tap **Go to timer**; tick the checkbox to skip it next time. **About this timer** reopens it.
2. Optionally expand **Exercise settings**, choose an **Exercise mode** (Both sets, Slow only, Fast only), and adjust the durations, repetitions, and recovery time.
3. Tap **Test beep** and adjust the device's media volume if needed.
4. Tap **Start**. Follow the **Contract**, **Relax**, and **Recover** prompts; the timer moves between phases and sets automatically.
5. Use **Pause**, **Resume**, or **Reset** as needed. To change the settings, reset first.

Each set ends after its last contraction, without a final relaxation interval.

## Run locally

Download or clone the repository, then open `index.html` in a modern browser. On some phones, local `.html` files may open in a document viewer instead of a browser; hosting the page is more convenient.

## Publish with GitHub Pages

1. The latest application file (currently v6) is the repository's root **`index.html`**; the versioned `Kegel_Timer_v*.html` files are preserved copies.
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
| **v5.0.0** | Added slow and fast contraction sets, slow-only/fast-only/both modes, and adjustable recovery between sets. |
| **v6.0.0** | Added a welcome screen with first-use instructions, a hide-on-future-visits option, and an About button. |

See [CHANGELOG.md](CHANGELOG.md) for release details.

## Health note

This is a timing aid, not a medical treatment plan. Follow the contraction duration, relaxation duration, repetition count, and exercise technique advised by your clinician or pelvic-floor physical therapist. Stop if exercising causes pain or strain.

## License

Released under the MIT License. See [LICENSE](LICENSE).
