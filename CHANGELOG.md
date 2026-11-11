# Changelog

Changes to the standalone Kegel Exercise Timer, from the initial release through Version 6.

## [6.0.0] — Welcome screen

### Added
- A welcome screen on first use explaining the timer's capabilities and how to configure exercise parameters.
- A "Don't show this welcome screen again" option, saved in `localStorage`.
- An **About this timer** button to reopen the instructions at any time.

### Preserved
- All Version 5 functionality.

## [5.0.0] — Two-set sessions

### Added
- Slow (Set 1) and fast (Set 2) contraction sets, each with its own contraction duration, relaxation duration, and repetition count.
- Exercise modes: Both sets, Slow only, and Fast only.
- Adjustable recovery period between sets (0–600 seconds, default 30), used in Both sets mode.
- Automatic transitions between exercise phases and sets, with distinct audio cues for recovery and the start of the fast set.

### Changed
- Improved session labels (for example "Set 1 of 2") and the settings layout, which now groups options per set.
- Default session is now slow (10 s / 10 s × 10) + 30 s recovery + fast (2 s / 2 s × 10), 4 minutes 18 seconds in total.
- Settings are saved under a new `localStorage` key; v2-format settings are still read as a fallback.

### Preserved
- Audio controls (Test beep) and locally saved preferences.

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
feat: add welcome screen and first-use instructions
```

Suggested tags: `v1.0.0`, `v2.0.0`, `v3.0.0`, `v4.0.0`, `v5.0.0`, `v6.0.0`.

Note: This changelog documents observable differences between the preserved HTML files, not a record of historical Git commits. Browser audio may still be restricted when a phone is locked or a tab is in the background.
