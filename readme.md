# CPU Scheduling Simulator

A lightweight, interactive command-line simulator written in C that demonstrates core Operating System CPU scheduling algorithms. It supports both manual process burst time entry and randomized automatic generation, calculates key performance metrics, and logs all simulation results to an external file.

---

## 📋 Table of Contents
- [Features](#-features)
- [Supported Algorithms](#-supported-algorithms)
- [Prerequisites](#-prerequisites)
- [Installation & Compilation](#-installation--compilation)
- [Usage](#-usage)
- [Output & Logging](#-output--logging)
- [Code Structure](#-code-structure)

---

## ✨ Features
- **Multiple Scheduling Algorithms:** Compare FCFS, SJF, and Round Robin on the exact same dataset within a single session.
- **Flexible Data Input:** 
  - **Manual Mode:** Enter custom burst times for each process.
  - **Auto Mode:** Automatically generates randomized burst times (`0` to `10` units) with simulated processing delays.
- **Performance Metrics:** Calculates and displays **Waiting Time (WT)**, **Turnaround Time (TT)**, **Average Waiting Time**, and **Average Turnaround Time**.
- **Persistent Logging:** Automatically formats and saves every simulation run into a local `simulator.txt` file for easy review and comparison.

---

## ⚙️ Supported Algorithms
1. **First-Come, First-Served (FCFS):** Non-preemptive scheduling where processes are executed in the exact order they arrive.
2. **Shortest Job First (SJF):** Non-preemptive scheduling that sorts processes in ascending order of their burst times to minimize average waiting time.
3. **Round Robin (RR):** Preemptive scheduling that assigns a fixed user-defined **Time Quantum** to each process in a cyclic queue.

*(Note: All simulations assume an arrival time of `0` for all processes.)*

---

## 🛠️ Prerequisites
- **Operating System:** Windows (uses `<windows.h>` for the `Sleep()` function during automatic data generation).
- **Compiler:** A standard C compiler such as **GCC** (via MinGW/MSYS2) or **MSVC**.

---

## 🚀 Installation & Compilation

1. **Clone the repository** (or download the source file):
   ```bash
   git clone https://github.com/yourusername/cpu-scheduling-simulator.git
   cd cpu-scheduling-simulator
   ```

2. **Compile the program** using GCC:
   ```bash
   gcc main.c -o scheduler.exe
   ```
   *(Replace `main.c` with the actual name of your C source file.)*

3. **Run the executable:**
   ```bash
   ./scheduler.exe
   ```

---

## 💻 Usage

1. Launch the program and enter the total **number of processes**.
2. Choose your data input method:
   - Enter `3` for **Manual data** (you will be prompted to enter the burst time for each process `P1`, `P2`, etc.).
   - Enter `5` for **Auto data** (randomly generates burst times).
3. Use the interactive menu to run simulations on your dataset:
   - `2` — Run **FCFS** simulation
   - `3` — Run **SJF** simulation
   - `5` — Run **Round Robin** simulation (prompts for Quantum size)
   - `6` — **Exit** the simulator

### Example Console Output
```text
 --- CPU scheduling simulator --- 
Enter number of processes:
3
Choose any one: 
3. Manual data 
5. Auto data 
3
Enter burst time for process P1:
5
Enter burst time for process P2:
3
Enter burst time for process P3:
8
2. FCFS simulation 
3. SJF simulation 
5. RR simulation 
6. Exit simulation 
Enter choice: 
2
FCFS
Simulation result:
pid     wt      bt      tt
P1      0       5       5 
P2      5       3       8 
P3      8       8       16 
Simulation end
Average waiting time: 4.333333
Average turnaround time: 9.666667
```

---

## 📄 Output & Logging
At the start of each session, the program initializes/clears `simulator.txt` in the root directory. Every time you run an algorithm from the menu, the resulting table (`PID`, `WT`, `BT`, `TT`) is appended to `simulator.txt` so you can compare results across different algorithms without losing previous runs.

---

## 🗂️ Code Structure
- `struct structure` (`pro`): Holds process attributes (`pid`, `wt`, `bt`, `tt`).
- `fcfs()` / `sjf()` / `rr()`: Core scheduling logic operating on temporary copies of the process array to preserve original data across multiple runs.
- `fcfs_sjf()`: Shared helper function to compute waiting and turnaround times for non-preemptive algorithms.
- `burst()`: Generates random burst times using `rand()` and `Sleep()`.
- `save()` / `clear()`: Handles file I/O operations for `simulator.txt`.
- `display()` / `average()`: Formats console table output and calculates average metrics.
