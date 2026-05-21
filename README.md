# Relationshapez: Gravity Chaos

Files:
- `index.html`
- `README.md`

This is a mobile-friendly, single-file HTML tool for exploring the planar three-body problem.

## Interface

### View tab
- Exact / Simulated toggle
- example dropdown
- Play / Pause
- Reset
- orbit canvas
- lower-right `+` and `−` zoom buttons
- drag to pan
- mouse wheel / trackpad zoom where supported
- pinch zoom on touch devices

### Bodies tab
- Body A, Body B, Body C
- each body has mass `m`, position `(x, y)`, and velocity `(vx, vy)`
- Step Size

## Behavior

- The path is always shown as a full path.
- In **Exact** mode, the example dropdown is active and body values / Step Size are read-only.
- Changing the example in **Exact** mode reloads the selected preset, refreshes body data, clears the path, recenters the view, and pauses at the start ready for **Play**.
- In **Simulated** mode, body values and Step Size are editable, and the example dropdown stays inactive.
- Editing a body value or Step Size in **Simulated** mode immediately stages a fresh setup, pauses playback, clears the path, recenters the view, and leaves **Play** ready.
- Switching back to **Exact** performs a full preset reset and re-enables the example dropdown.

## Exact data and sources

**Exact** mode includes both formula-based special solutions and embedded replay-based reference trajectories. The replay examples are self-contained in the HTML file, so the app does not need to download orbit data at runtime.

### Formula-based exact cases

The Lagrange circular and Euler circular presets are generated directly from classical closed-form special solutions of the Newtonian three-body problem.

### Replay-based periodic cases

The labels `Periodic I.A.1` through `Periodic I.A.6` follow the naming convention from published three-body periodic-orbit tables. These are reference trajectories for equal masses with:

- `G = 1`
- masses `1, 1, 1`
- initial positions `(-1,0)`, `(1,0)`, `(0,0)`
- initial velocities `(v1,v2)`, `(v1,v2)`, `(-2v1,-2v2)`

The source family is the Li–Liao/SJTU catalog of Newtonian periodic planar collisionless three-body orbits:

- Xiaoming Li and Shijun Liao, **More than six hundreds new families of Newtonian periodic planar collisionless three-body orbits**:  
  https://arxiv.org/abs/1705.00527
- SJTU Numerical Tank three-body orbit website referenced by the paper:  
  http://numericaltank.sjtu.edu.cn/three-body/three-body.htm

The app embeds selected replay data directly in the HTML file for offline use. These embedded data are used as trusted reference paths in **Exact** mode rather than being recomputed live.

### Free-fall source context

For free-fall families, the relevant setup uses positions `(-0.5,0)`, `(0.5,0)`, `(x,y)` with all velocities zero and `G = 1`. Free-group words are classification labels, not extra simulation input parameters.

Related free-fall source context:

- Xiaoming Li and Shijun Liao, **Collisionless periodic orbits in the free-fall three-body problem**:  
  https://arxiv.org/abs/1805.07980

## License

Copyright (c) 2026 Alan Miller.

This project is released under the **MIT License**.

See the [`LICENSE`](LICENSE) file for the full license text.
