# Python for Engineering 

A collection of my Python assignments from the programming course in the summer semester 2026
(B.Sc. Computer Science, Technische Universität Berlin). The assignments are Jupyter notebooks
covering simulations from engineering and science, from a simple energy grid to sound
propagation with the finite-difference method.

**Author:** Franck Yagoue · Computer science student, TU Berlin (3rd semester)  
**Contact:** franckyagoue0@gmail.com  
**Focus:** Python, NumPy, Matplotlib, numerical simulation  
**Interests:** IT security, software engineering, AI / machine learning, statistics

---

## Overview

| Notebook | Topic | What is implemented |
|----------|-------|---------------------|
| [`HA1.ipynb`](HA1.ipynb) | Stand-alone energy grid | Hour-by-hour simulation of solar, wind, battery and diesel generator; cost calculation; text bar chart and formatted table for several battery capacities |
| [`HA2.ipynb`](HA2.ipynb) | Kerosene tank in an aircraft wing | Geometry and volume functions, numerical integration, tank-emptying simulation based on Torricelli's law, table and text display |
| [`PA3.ipynb`](PA3.ipynb) | Cruise control with a PID controller | Vehicle model from a force balance, slope profile, PID speed control, plots |
| [`PA4.ipynb`](PA4.ipynb) | Noise reduction with a barrier | 2D sound field with the FDTD method, discrete Laplace operator, stability condition, damping mask, level reduction |
| [`PA5.ipynb`](PA5.ipynb) | Traffic simulation | Microscopic traffic model on a ring road (50 vehicles, 1200 m), optimal velocity model, traffic jam waves |

---

## Assignment details

### HA1 – Stand-alone energy grid
A micro-grid for a community without a grid connection must cover its daily demand with
solar and wind power, a battery system and a diesel generator.
- Hour-by-hour simulation over one day with battery charge and discharge logic
- Cost calculation per hour and per day
- Text output of the battery charge as a bar (`07: ########`)
- Simulation over seven days and comparison of several battery capacities in one table

*Practiced:* loops, conditions, formatted output, building a small simulation.

### HA2 – Kerosene tank in an aircraft wing
The tank is modelled as a tilted truncated pyramid. The goal is to compute how long it
takes to empty it through a drain valve.
- Function `oberflaeche(h, L, H, W)` for the liquid surface at fill height `h`, with case distinctions (empty tank, sloped base, vertical end wall, full tank)
- Function `volumen(h, L, H, W)` using numerical integration of the surface over the fill height
- Outflow speed from Torricelli's law and time per volume step
- Step-by-step simulation of the emptying until the tank is empty, output as a table (90 % down to 0 %)
- Cockpit display as text bars for fill level and volume
- Refined model with a rounded tank bottom
- Automatic plausibility tests with `assert`

*Practiced:* functions, loops, numerical integration, physical formulas, testing, formatted output.

### PA3 – Cruise control (PID controller)
A vehicle should keep a constant speed on a road with uphill and downhill sections.
- Vehicle model: drive force, rolling resistance, air resistance, gravity on slopes
- Function `steigung(x)` that also accepts NumPy arrays
- Time-stepping simulation and design of a PID controller
- Labelled plots with Matplotlib

*Practiced:* NumPy arrays, time-stepping methods, control engineering basics, visualization.

### PA4 – Noise reduction with the FDTD method
A sound pulse spreads in a rectangular room. A barrier reduces the sound at the receiver position.
1. Simulation domain and stability condition
2. Discrete Laplace operator
3. FDTD time step
4. Sound source, receiver and damping mask
5. Simulation function
6. Direct sound time and visualization of the sound field
7. Inserting a barrier and determining the level reduction

*Practiced:* vectorized computation with NumPy, numerical methods, visualization of 2D fields.

### PA5 – Traffic simulation
Microscopic simulation of vehicles on a ring road (`L = 1200 m`, `N = 50`,
`dt = 0.1 s`, `t_max = 600 s`). Traffic jams appear from driving behaviour alone, even with a single lane.
1. Initialization of the state arrays
2. Optimal velocity model
3. Influence of the distance on the velocity
4. One simulation step
5. Simulation and plots over time
6. Visualization of the jam waves
7. Influence of the reaction strength on the traffic flow

*Practiced:* modelling, state arrays, parameter studies, evaluation and presentation of results.

---

## Technologies

| Tool | Use |
|------|-----|
| Python 3 | Programming language |
| NumPy | Arrays, vectorized computation |
| Matplotlib | Plots and visualization |
| Jupyter Notebook | Documentation and execution |

---

## How to run

Requirements: Python 3 with the packages `numpy`, `matplotlib` and `jupyter`.

```bash
pip install numpy matplotlib jupyter
jupyter notebook
```

Then open a notebook (for example `PA5.ipynb`) and run the cells in order.

---

## Note

The task descriptions come from a course at TU Berlin
(task texts partly licensed under CC BY 4.0, Gert Herold).