# CPU-Scheduling-Simulator
CPU SCHEDULING SIMULATOR: FCFS, SJF, RR algorithms

## DEFINITION
CPU Scheduling is an operating system mechanism that decides which process gets the CPU and for how long when multiple processes are present in the ready queue.

## ABOUT
A CPU Scheduling Simulator is a program that imitates the working of different scheduling algorithms and calculates performance parameters such as:
1. Waiting Time (WT)
2. Turnaround Time (TAT)
3. Average Waiting Time
4. Average Turnaround Time

## TERMINOLOGIES
(a) Burst Time (BT):
The total time required by a process to execute on the CPU.
(b) Waiting Time (WT):
The total time a process waits in the ready queue before getting CPU.
WT = TAT − BT
(c) Turnaround Time (TAT)
Total time taken from process arrival to completion.
𝑇𝐴𝑇 = 𝐶𝑜𝑚𝑝𝑙𝑒𝑡𝑖𝑜𝑛 𝑇𝑖𝑚𝑒 − 𝐴𝑟𝑟𝑖𝑣𝑎𝑙 𝑇𝑖𝑚𝑒
(Arrival time is assumed as 0 in this simulator)

## ROUND ROBIN
Each process gets a fixed time quantum
After quantum expires, process goes back to ready queue

## ALGORITHM IMPLEMENTED
1. FCFS (First Come First Serve)
2. SJF  (Shortest Job First – Non-Preemptive)
3. Round Robin

## CONCEPTS USED
pid, burst time
Waiting Time & Turnaround Time calculation

<br>Author: Ritik
