# Contributing to Curiosity Lab

Thanks for helping make learning fun! This guide covers how the project is built and how
to add or change an activity.

## Philosophy

Every activity should:

1. **Teach one idea.** If you can't name the single "aha!" in a sentence, narrow it down.
2. **Let kids discover it.** Prefer interaction (tap, drag, build) over explanation.
3. **Be kind.** Mistakes get a gentle hint from Bit, never a punishment.
4. **Celebrate success.** A clear, joyful reward (sound + visual) on the win.
5. **Fit ages 8–12.** Short sentences, large type, big tap targets (min ~44px).

## How activities are built

- Each activity is one self-contained `*.dc.html` file that opens directly in a browser.
- Styling is **inline** so the page paints immediately as it loads.
- Logic lives in a `class Component` with a `renderVals()` method that feeds the markup.
- The shared runtime is `support.js` — **do not edit it**.

## Adding a new activity

1. Create `Your Activity.dc.html` following the structure of an existing one.
2. Add a card for it on `Landing.dc.html`. The card grid shows **3 per row on laptop**,
   wraps the 4th to the next row, and **stacks to one column on mobile** — just add another
   `<a>` card and the grid handles the rest.
3. Use the **Bit** robot mascot and the shared visual language (Fredoka + Nunito fonts,
   rounded cards, the warm cream→blue→lavender background).
4. If your activity plays sound, you **must** include the audio-unlock pattern described
   in `CLAUDE.md` so it works in Safari/iOS.

## Visual language

- **Fonts:** Fredoka (headings/numbers), Nunito (body).
- **Accent colors:** teal `#2ec4b6`, coral `#ff6b6b`, gold `#ffd23f`, purple `#b96bff`, blue `#5b8def`.
- **Cards:** white, ~32px radius, soft shadow.
- **Mascot:** Bit, a teal robot, expresses happy / neutral / sad / celebrate moods.

## Testing checklist

Before submitting a change, verify in **Chrome and Safari**:

- [ ] The activity loads with no console errors.
- [ ] It fits one screen comfortably; no awkward scrolling or jumpy resizing.
- [ ] Sound plays after the first tap (silent switch off on iPhone).
- [ ] Correct and incorrect interactions both behave and give appropriate feedback.
- [ ] Works on a narrow (mobile) width as well as laptop.

## Style conventions

See `CLAUDE.md` for project-wide defaults (including the required audio-unlock snippet).
