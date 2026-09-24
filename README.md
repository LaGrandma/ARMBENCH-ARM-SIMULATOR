ARMBENCH

A free, browser-based simulator of a 5-DOF robotic arm — for learning kinematics and control systems with nothing but a laptop.

Live demo: https://lagrandma.github.io/arm-simulator/

Why

Robotics is gatekept by hardware cost. Servos, controllers, and frames add up fast, which puts hands-on experimentation out of reach for a lot of people who want to learn it. ARMBENCH is a digital twin of a low-cost 5-DOF arm that runs entirely in the browser — no install, no purchase, no setup. If you can open a web page, you can move a robot arm and start learning how it works.

What it does right now
Renders a 5-DOF arm as a real kinematic chain (each joint parented to the last, so the arm moves the way a physical one does).
A slider per joint, each clamped to that joint's real servo limits — the sim can't show a pose the hardware couldn't reach.
Orbit, pan, and zoom to inspect the arm from any angle.
Roadmap
 P0 — 3D scene + kinematic chain + joint control
 P1 — Forward kinematics: live end-effector position readout
 P2 — Inverse kinematics: click a target, the arm solves to reach it
 P3 — Control layer: per-joint PID with tunable gains and live response plots
 P4 — Teaching UX: workspace visualization and guided tuning challenges
 P5 — Web Serial bridge: drive a real ESP32-based arm from the browser
Built with

Plain JavaScript and three.js — a single static page, no build step, no backend.

Run it locally

It needs to be served over HTTP (ES modules and the import map won't work from a file:// path):

bash
# with Python
python3 -m http.server 8000
# then open http://localhost:8000

Or use the VS Code Live Server extension and click Go Live.

The arm

ARMBENCH is modeled on a self-designed 5-DOF arm intended to be built for around $70. The simulator's joint axes, link lengths, and limits come from that design, so control code tuned here is meant to transfer to the physical build.

License

MIT
