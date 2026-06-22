# Project notes

## Audio: always unlock Web Audio for Safari/iOS (apply by default)

Any design that plays sound via the Web Audio API (AudioContext) MUST unlock audio on
the first user gesture. Safari/iOS keep the AudioContext "suspended" until it is created
AND a silent buffer is played inside a real user gesture. Without this, kids hear nothing
in Safari.

Add this to every project that has sound:

- On mount, install a one-time unlock listener:
  ```js
  installAudioUnlock() {
    const unlock = () => {
      this.ensureAudio();
      const a = this.actx; if (!a) return;
      try { const b = a.createBuffer(1,1,22050); const s = a.createBufferSource(); s.buffer=b; s.connect(a.destination); s.start(0); } catch(e) {}
      if (a.state === 'suspended') a.resume();
    };
    this._unlock = unlock;
    ['pointerdown','touchstart','mousedown','keydown'].forEach(ev => window.addEventListener(ev, unlock, { passive: true }));
  }
  ```
- Call `this.installAudioUnlock()` in `componentDidMount`, and remove the listeners in `componentWillUnmount`.
- `ensureAudio()` should create `this.actx = new (window.AudioContext || window.webkitAudioContext)()` and call `resume()` if suspended.

This same approach also satisfies Chrome, Edge, and Firefox autoplay policies (they
unlock on any user gesture too), so one implementation covers all browsers.
