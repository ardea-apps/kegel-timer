# Kegel Exercise Timer

A lightweight, mobile-friendly Kegel (pelvic-floor exercise) timer that runs in a web browser. It guides alternating contraction and relaxation periods with a visual countdown and audible cues.

**Current version:** v8.0.0

## Features

- Three exercise modes: **Slow only**, **Fast only**, or **Both** (slow followed by fast).
- Independent, adjustable contraction and relaxation durations and repetition counts for each set.
- Adjustable recovery time between sets, including the option of no recovery break.
- Three-beep announcement and a five-second preparation countdown before each set.
- Distinct high- and low-pitched tones for contraction and relaxation, respectively, and two beeps at the end of each set.
- Prominent countdown, active set and phase labels, repetition counter, and progress indicator.
- **Start**, **Pause/Resume**, **Reset**, **Start again**, and **Test beep** controls.
- Collapsible exercise settings that close automatically when a session starts or resumes.
- Browser-local storage of exercise settings for future visits on the same device and site.
- Welcome screen with concise instructions, an option to hide it on later visits, and an **About this timer** button to reopen it.
- Screen wake-lock support where available.
- Standalone HTML, CSS, and JavaScript; no external libraries or backend are required.

## Default session

The default mode is **Both** (slow/fast).

| Setting | Slow set | Fast set |
| --- | ---: | ---: |
| Contraction duration | 10 sec | 2 sec |
| Relaxation duration | 10 sec | 2 sec |
| Number of contractions | 10 | 10 |
| Relaxation intervals | 9 | 9 |
| Exercise time | 3:10 | 0:38 |

Default recovery between sets: **20 seconds**.

| Phase | Duration |
| --- | ---: |
| Three-beep opening announcement | 1.05 sec |
| Preparation for Set 1 | 5 sec |
| Slow contractions and rests | 190 sec |
| Two-beep set completion | 0.85 sec |
| Recovery | 20 sec |
| Three-beep Set 2 announcement | 1.05 sec |
| Preparation for Set 2 | 5 sec |
| Fast contractions and rests | 38 sec |
| Two-beep set completion | 0.85 sec |
| **Total (rounded)** | **4:22** |

Each set has one fewer relaxation interval than contractions. The application calculates total scheduled duration automatically, including announcements, preparation, completion signals, and recovery (in two-set mode).

### Adjustable ranges

- Contraction duration: **1–120 seconds**, independently for each set.
- Relaxation duration: **1–120 seconds**, independently for each set.
- Number of contractions: **1–100**, independently for each set.
- Recovery between sets: **0–600 seconds** (whole numbers; 0 skips the recovery interval).

Previously saved settings take precedence over defaults. If upgrading from an older release, set recovery to 20 seconds manually if desired.

## How to use

1. Open the timer in a modern browser. Read the welcome screen and tap **Go to timer**.
2. Expand **Exercise settings** to select the exercise mode and customize the durations, repetition counts, and recovery period.
3. Tap **Test beep** and adjust your device's media volume if needed.
4. Tap **Start**. Three beeps announce the first set, followed by a five-second preparation countdown.
5. Follow the audible cues and visual prompts listed below. In two-set mode, the second set follows automatically after recovery, with its own announcement and preparation countdown.
6. Use **Pause**, **Resume**, or **Reset** as needed. Reset before editing settings during a session.

### Audio signals

| Signal | Meaning |
| --- | --- |
| Three beeps | A set is about to begin; a five-second preparation countdown follows. |
| One high-pitched beep | Contract your pelvic floor muscles. |
| One low-pitched beep | Relax your muscles. |
| Two beeps | The current set is complete. |

There is no additional relaxation interval after the last contraction of a set. The final two-beep completion signal ends the routine. The Test beep control and resume acknowledgement are separate from the exercise cues.

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
| **v5.0.0** | Added slow/fast exercise modes, adjustable recovery, and refined two-set interface. |
| **v6.0.0** | Added welcome instructions and a three-beep session completion signal. |
| **v7.0.0** | Added preparation countdowns, standardized set completion cues, and 20-second default recovery. |
| **v8.0.0** | Added three-beep opening announcement before the first set and updated instructions. |

See [CHANGELOG.md](CHANGELOG.md) for release details.

## Health note

This is a timing aid, not a medical treatment plan. Follow the contraction duration, relaxation duration, repetition count, and exercise technique advised by your clinician or pelvic-floor physical therapist. Stop if exercising causes pain or strain.

## License

See the repository’s `LICENSE` file for applicable licensing terms. The intended license is MIT; include the MIT license text in the repository to establish the applicable permissions.
