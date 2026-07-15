# harmonies of the world

A journey through nested scales of harmony: darkness → galaxy → solar system →
moons → Earth's surface → living geometry (sunflower, honeycomb, DNA, snowflake).
The solar system runs on real dates — scrub time, jump to 1619, or hear the chord
of your own birthday. Ends where it began: *the harmony did not disappear; you
moved beyond the scale at which you could hear it.*

## Originally: Harmonices Mundi — a singing solar system

An interactive 3D data-sonification of the solar system, after Johannes Kepler's
*Harmonices Mundi* (1619). Each planet is a musical voice: its pitch tracks how fast
it sweeps around the Sun, so elliptical orbits become pitch-bends. Click planets to
build a chord and hear the harmony (or dissonance) between them.

Inspired by [phber/harmonices-mundi](https://github.com/phber/harmonices-mundi).

## Run it

Open `index.html` in any modern browser (Three.js and Tone.js load from CDN — needs
internet). Or serve it: `python3 -m http.server` and visit `http://localhost:8000`.

## How it works

- **Motion** is physically exact: each frame solves Kepler's equation
  `M = E − e·sin E` by Newton–Raphson, converts to true anomaly, and places the
  planet at `r = a(1 − e·cos E)` with the **Sun at the focus** of each ellipse.
  Planets visibly speed up at perihelion and slow at aphelion.
- **Pitch** maps the angular sweep seen from the Sun (∝ 1/r²) to frequency:
  `f = f_base · (r_aphelion / r)²`. Each planet spans exactly
  `((1+e)/(1−e))²` — Venus (e = 0.007) holds nearly one steady note while
  Mercury (e = 0.206) swoops across ×2.307.
- **The Real Sky** (default) plays the true, unrounded microtonal glides — faintly
  dissonant, never repeating. **Kepler's Dream** quantizes each voice to a
  just-intonation major scale: the romanticized music of the spheres.
- **Bonus scene:** Io–Europa–Ganymede in their gravity-locked 4:2:1 resonance —
  genuine consonance with no rounding needed.

## Nested zoom — universes inside universes

Clicking a planet falls *into* it, revealing a smaller harmonic world running on the
same sonification engine. Jupiter's Galilean moons sing their gravity-locked 4:2:1
Laplace resonance as exact octaves (Callisto honestly drifts outside it); Saturn's
moons sound their real resonances (Mimas–Tethys 2:1, Enceladus–Dione 2:1,
Titan–Hyperion 4:3); Mars's Phobos and Deimos are audibly *almost* 4:1 but not
locked. Click Earth again from its moon level to descend to a stylized surface where
only real, documented harmonies live: phyllotaxis and the golden angle (137.5°), the
pentagon's φ in five-petaled flowers, Palladian 3:2 room proportions, and the
honeycomb's minimal-perimeter hexagon (a 5:6 minor third by Kepler's own circle
division). Click empty space or *← back* to rise a level.

## Controls

Drag to orbit the camera, scroll to zoom. At the solar-system level, click a planet
to enter its world and use the legend to build chords; at moon level, click moons to
add voices. *play all* sounds everything; toggle *the real sky / kepler's dream*.
All UI is lowercase Helvetica, no boxes, with a shine that sweeps the menu text on
hover.

Built with [Three.js](https://threejs.org) and [Tone.js](https://tonejs.github.io). No build step.
