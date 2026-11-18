# Changelog

Changes to the standalone Kegel Exercise Timer, from the initial release through Version 8.

## [8.0.0] — Opening set announcement

### Added
- Three-beep announcement at the start of a new session, for all exercise modes, using the same signal as the second-set announcement.

### Changed
- The opening announcement precedes the existing five-second preparation countdown.
- Display SET STARTING during the initial announcement; retain SET 2 NEXT for the second set.
- Update welcome instructions to explain that three beeps announce any set.
- Include the opening announcement in the automatically calculated session duration (approximately 4:22 with default settings).
- Preserve two-beep set completion, high/low contraction and relaxation cues, 20-second default recovery, saved preferences, and existing controls.

## [7.0.0] — Preparation countdowns and standardized audio signals

### Added
- Five-second preparation countdown before the first contraction of each set.
- Dedicated three-beep second-set announcement, followed by its own five-second preparation countdown.
- Visual preparation and set-completion phases.

### Changed
- Standardize two beeps at the end of every set, including the final set, replacing the previous three-beep session completion signal.
- Use a high-pitched contraction tone and a low-pitched relaxation tone consistently, including the first contraction of the second set.
- Include preparation and signaling periods in the calculated session duration.
- Reduce the default recovery interval from 30 to 20 seconds, without overwriting saved preferences.
- Simplify the welcome text and add practical instructions explaining the audio signals.

## [6.0.0] — Welcome screen and completion signal

### Added
- Welcome screen explaining the timer and how to configure exercise settings.
- Go to timer control, an option to hide the welcome screen on future visits, and an About this timer button to reopen it.
- Local storage of the welcome-screen preference.

### Changed
- Use three beeps at completion of the selected exercise session.
- Preserve the two-set exercise modes, adjustable settings, and timer controls from V5.

## [5.0.0] — Two-set exercise timer

### Added
- Slow-only, fast-only, and combined slow/fast exercise modes.
- Independent contraction duration, relaxation duration, and repetition count for both sets (default slow: 10/10 seconds; fast: 2/2 seconds; 10 contractions each).
- Adjustable recovery between sets, entered as a whole number from 0 to 600 seconds (default 30 seconds).
- Automatic transition through the selected sets and recovery, with audio cues for transitions.
- Local persistence of settings for both sets and recovery.

### Changed
- Refine the collapsible settings layout with a separate green recovery heading between the two set groups.
- Highlight active session labels in bold green at the same font size as the repetition summary.
- Clarify the combined-session label as Two-set session (slow/fast).
- Recalculate duration for the selected mode, set parameters, and recovery.

### Release numbering
- Official V5 incorporates the intermediate V5.1–V5.3 interface refinements; official V6 incorporates the former V5.4 welcome screen and subsequent completion-tone adjustment. Intermediate builds are not separate official releases.

## [4.0.0] — Collapsible settings

### Changed
- Converted the Exercise settings panel into a collapsible section that starts closed.
- Automatically collapse the settings panel when a session starts or resumes, leaving more room for the timer on small screens.
- Added a tap-to-edit label and an expand/collapse indicator.

### Preserved
- Adjustable contraction and relaxation intervals, repetition count, saved preferences, and existing timer/audio controls.

## [3.0.0] — Configurable exercise sessions

### Added
- Separate contraction and relaxation durations (1–120 seconds each).
- Configurable number of contractions (1–100), defaulting to 10.
- Browser-local persistence of preferences using `localStorage`.
- Automatic calculation and display of total session duration.
- Status text for audio interruptions and responsive styling for smaller screens.

### Changed
- Reworked the phase schedule to support unequal contraction and relaxation lengths, with a relaxation period only *between* contractions.
- Updated progress/countdown text to reflect the configured routine.
- Prevented changing settings mid-session; Reset is required before editing.

## [2.0.0] — More reliable audio and restart behavior

### Added
- A **Test beep** button for checking sound before exercise.
- An audible acknowledgement when resuming a paused session.

### Fixed / improved
- Initialize/resume Web Audio synchronously from the Start/Test beep tap, reducing missed first beeps on iOS.
- Schedule oscillator sounds slightly ahead of the audio clock and clean up audio nodes after playback.
- Strengthened reset/restart and screen-wake-lock handling so previous session state does not interfere with a new run.
- Restore audio handling when the page becomes visible again.

### Changed
- Updated on-screen guidance about screen visibility, phone audio, and Silent Mode.

## [1.0.0] — Initial timer

### Added
- Single-file HTML/CSS/JavaScript timer, designed for mobile and desktop browsers.
- Fixed routine: 10 contractions of 10 seconds each, separated by 9 relaxation intervals of 10 seconds (3 minutes 10 seconds total).
- Audible cues at the start and at each contraction/relaxation transition, plus a double beep at completion.
- Large countdown, phase labels, repetition progress, and progress bar.
- Start/Pause/Resume and Reset controls.
- Optional vibration cues and screen wake-lock support where available.

---

## Suggested Git commit messages

Commit each historical version separately, in order:

**v1**
```text
feat: add initial fixed-interval Kegel timer
```

**v2**
```text
fix: improve audio reliability on start and restart
```

**v3**
```text
feat: add configurable intervals, repetitions, and saved settings
```

**v4**
```text
feat: make exercise settings collapsible on mobile
```

**v5**
```text
feat: add two-set Kegel timer with customizable intervals
```

**v6**
```text
feat: add welcome screen and three-beep completion signal
```

**v7**
```text
feat: add preparation countdowns and standardized audio signals (v7)
```

**v8**
```text
feat: add three-beep announcement at session start (v8)
```

Suggested tags: `v1.0.0` through `v8.0.0`.

Note: This changelog documents observable differences between the preserved HTML files, not a record of historical Git commits. Browser audio may still be restricted when a phone is locked or a tab is in the background.
