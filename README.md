# SchedSim — CPU Scheduling Algorithm Visualizer & Performance Analyzer

> Visual simulation of FCFS, SJF, Round Robin & Priority Scheduling · Python GUI · Performance metrics comparison

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![Matplotlib](https://img.shields.io/badge/Visualization-Matplotlib-orange?style=flat-square)
![Domain](https://img.shields.io/badge/Domain-Operating%20Systems-green?style=flat-square)
![GUI](https://img.shields.io/badge/Interface-Tkinter%20GUI-lightblue?style=flat-square)

---

## Overview

CPU scheduling is a core OS problem — how the kernel decides which process runs next directly impacts system throughput, response time, and fairness. This project implements and visually compares **4 classic scheduling algorithms** side-by-side, letting you observe how each behaves under different workloads in real time.

Built with a Python GUI (`interface.py`) and a full test suite (`test_rc.py`).

---

## Algorithms Implemented

| Algorithm | Type | Key Characteristic |
|---|---|---|
| **FCFS** — First Come First Served | Non-preemptive | Simple, no starvation, convoy effect |
| **SJF** — Shortest Job First | Non-preemptive | Optimal avg wait time, requires burst time knowledge |
| **Round Robin** | Preemptive | Fair time-sharing, tunable quantum |
| **Priority Scheduling** | Preemptive / Non-preemptive | Weighted importance, starvation risk |

---

## Metrics Tracked

For each algorithm, the simulator computes and visualizes:

- **Average Waiting Time** — time a process spends in the ready queue
- **Turnaround Time** — total time from arrival to completion
- **CPU Utilization** — percentage of time CPU is actively executing
- **Gantt Chart** — visual timeline of process execution order

---

## Screenshots

| FCFS Gantt Chart | Round Robin | Performance Comparison |
|---|---|---|
| ![FCFS](FCFS.png) | ![RR](R.png) | ![Summary](SM.png) |

---

## Project Structure

```
├── interface.py       # Main GUI application
├── image_rc.py        # Image resource handler
├── test_rc.py         # Test suite
├── doc.pdf            # Project documentation
├── *.png              # Gantt chart visualizations
└── README.md
```

---

## Quick Start

```bash
git clone https://github.com/Drashti0913/CPU-Scheduling-Simulator.git
cd CPU-Scheduling-Simulator

pip install matplotlib pandas

# Launch the GUI
python interface.py

# Run tests
python test_rc.py
```

---

## Key Implementation Details

**Process representation:** Each process carries arrival time, burst time, and priority — the scheduler maintains a ready queue and dispatches based on algorithm-specific logic.

**Round Robin quantum:** Configurable time quantum — observe how smaller quanta improve responsiveness but increase context-switch overhead, while larger quanta approach FCFS behavior.

**Preemption handling:** Priority scheduling supports both preemptive and non-preemptive modes — demonstrates the starvation problem and how aging can address it.

**Visualization pipeline:** After simulation, Matplotlib generates Gantt charts and bar comparisons of waiting/turnaround times across all algorithms — making tradeoffs immediately visible.

---

## OS Concepts Demonstrated

This simulator is a hands-on implementation of core operating systems concepts:

- **Process lifecycle** — ready, running, waiting states
- **Context switching** — cost of preemption in Round Robin
- **Starvation vs fairness** — Priority vs Round Robin tradeoffs
- **Convoy effect** — why FCFS performs poorly with mixed burst times
- **Optimal scheduling** — why SJF minimizes average wait time (provably)

---

## License

MIT
