# Process Scheduling Simulator

## Project's Title

**Process Scheduling Simulator**

## Project Description

This project is a C++ program that simulates various CPU scheduling algorithms. It reads a list of processes from an input file, predicts the best scheduling algorithm to use based on process information, and then simulates the execution of the processes using different scheduling algorithms. The results, including average waiting time, average turnaround time, and a Gantt chart for each algorithm, are written to an output file.

## How to Run the Project

### Dependencies

- A C++ compiler (e.g., `g++`, `clang++`)
- A terminal or command prompt

### Compilation

1. Ensure you have a C++ compiler installed on your system.
2. Download or clone the project files.
3. Open a terminal and navigate to the directory containing the project files.
4. Use the following command to compile the code:

```sh
g++ cpu_scheduler.cpp -o scheduler
```

### Running

1. Ensure the input file `input1.txt` is in the same directory as the compiled executable. The input file should contain process details.
2. Run the compiled executable with the following command:

```sh
./scheduler
```

3. The results will be written to `output1.txt` in the same directory.

### Input File Format

The input file `input1.txt` should contain lines with the following format:

```
<Process ID> <Burst Time> <Arrival Time>
```

Example:

```
1 6 0
2 8 1
3 7 2
4 3 3
```

### Output

The output file `output1.txt` will contain:

- The best algorithm predicted based on the process information.
- Results for each scheduling algorithm, including average waiting time, average turnaround time, and a Gantt chart.

## Internal Working of the Project

### Theory

CPU scheduling is the basis of multiprogrammed operating systems. By switching the CPU among processes, the operating system can make the computer more productive. Several scheduling algorithms determine the order of process execution. This project implements and compares the following scheduling algorithms:

1. **Shortest Job First (SJF)**: Selects the process with the smallest burst time.
2. **Longest Job First (LJF)**: Selects the process with the largest burst time.
3. **Shortest Remaining Time First (SRTF)**: Preemptive version of SJF that selects the process with the smallest remaining time.
4. **Round Robin (RR)**: Each process is assigned a fixed time slice (quantum), and processes are rotated in a circular queue.

### Prediction Logic

The program predicts the best scheduling algorithm by analyzing the process information:
- If all burst times are the same, it suggests FCFS (First-Come, First-Served).
- If burst time and arrival time variances are low, it suggests SJF.
- If burst time variance is low but arrival time variance is high, it suggests SRTF.
- If there are many long burst time processes, it suggests LJF.
- Otherwise, it suggests Round Robin.

### Implementation

The project includes functions to simulate each scheduling algorithm and calculate average waiting and turnaround times. It also generates a Gantt chart for each algorithm to visualize the execution order.

- **calculate_wait_turn_time**: Calculates waiting and turnaround times for processes.
- **print_avg_time**: Prints average waiting and turnaround times to the output file.
- **print_gantt**: Prints the Gantt chart to the output file.
- **sjf**: Simulates Shortest Job First scheduling.
- **ljf**: Simulates Longest Job First scheduling.
- **srtf**: Simulates Shortest Remaining Time First scheduling.
- **roundRobin**: Simulates Round Robin scheduling.
- **predictBestAlgorithm**: Predicts the best scheduling algorithm based on process information.
- **runScheduler**: Main function to read input, run predictions and simulations, and write output.

## Learning Takeaways from the Project

- **Understanding CPU Scheduling Algorithms**: Gained a deep understanding of various CPU scheduling algorithms and their implementation details.
- **Algorithm Analysis**: Learned how to analyze process information to determine the most suitable scheduling algorithm.
- **File I/O in C++**: Improved skills in handling file input and output operations in C++.
- **Code Organization**: Practiced organizing code into functions for modularity and readability.
- **Gantt Chart Visualization**: Learned how to represent process execution visually using Gantt charts.

## Resources/References

- [GeeksforGeeks: CPU Scheduling Algorithms](https://www.geeksforgeeks.org/cpu-scheduling-in-operating-systems/)
- [Wikipedia: CPU Scheduling](https://en.wikipedia.org/wiki/Scheduling_(computing))
