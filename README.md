# Process Scheduling Simulator

This project is a C++ program that simulates various CPU scheduling algorithms. It reads a list of processes from an input file, determines the best scheduling algorithm to use based on the process information, and then simulates the execution of the processes using different scheduling algorithms. The results, including average waiting time, average turnaround time, and a Gantt chart for each algorithm, are written to an output file.

## Features

- **Scheduling Algorithms Implemented**:
  - Shortest Job First (SJF)
  - Longest Job First (LJF)
  - Shortest Remaining Time First (SRTF)
  - Round Robin (RR)

- **Prediction**:
  - The program predicts the best scheduling algorithm to use based on process information.

- **Output**:
  - Average waiting time and turnaround time for each algorithm.
  - Gantt chart illustrating the execution order of processes.

## Files

- `main.cpp`: Contains the main code for the program.
- `input1.txt`: Input file where process details are provided.
- `output1.txt`: Output file where results are written.

## Input File Format

The input file should be named `input1.txt` and should contain lines with the following format:

```
<Process ID> <Burst Time> <Arrival Time>
```

Each line represents a process, with:
- `Process ID`: A unique identifier for the process.
- `Burst Time`: The total time required by the process.
- `Arrival Time`: The time at which the process arrives.

### Example:

```
1 6 0
2 8 1
3 7 2
4 3 3
```

## Output File Format

The output file `output1.txt` will contain:
- The best algorithm predicted based on the process information.
- Results for each scheduling algorithm, including average waiting time, average turnaround time, and a Gantt chart.

### Example:

```
Best algorithm predicted is SJF

SJF Scheduling:
Average Waiting Time: 3.75
Average Turnaround Time: 8.75
Gantt Chart:
| P1 | P4 | P3 | P2 |
0	6	9	16	24

LJF Scheduling:
Average Waiting Time: 7.75
Average Turnaround Time: 12.75
Gantt Chart:
| P2 | P3 | P1 | P4 |
0	8	15	21	24

SRTF Scheduling:
Average Waiting Time: 3.0
Average Turnaround Time: 8.0
Gantt Chart:
| P1 | P2 | P3 | P4 |
0	3	6	11	14

Round Robin Scheduling (Quantum = 2):
Average Waiting Time: 5.25
Average Turnaround Time: 10.25
Gantt Chart:
| P1 | P2 | P3 | P4 | P1 | P2 | P3 |
0	2	4	6	8	10	12	14
```

## How to Compile and Run

### Prerequisites

- A C++ compiler (e.g., g++, clang++)
- A terminal or command prompt

### Compilation

Use the following command to compile the code:

```sh
g++ main.cpp -o scheduler
```

### Running

Run the compiled executable:

```sh
./scheduler
```

Ensure that `input1.txt` is in the same directory as the executable. The results will be written to `output1.txt`.

## Function Overview

- **calculate_wait_turn_time(vector<Process>& processes)**: Calculates the waiting and turnaround times for processes.
- **print_avg_time(vector<Process>& processes, ofstream& outputFile)**: Prints the average waiting and turnaround times to the output file.
- **print_gantt(vector<Execution>& executions, ofstream& outputFile)**: Prints the Gantt chart to the output file.
- **sjf(vector<Process> processes, ofstream& outputFile)**: Simulates Shortest Job First scheduling.
- **ljf(vector<Process> processes, ofstream& outputFile)**: Simulates Longest Job First scheduling.
- **srtf(vector<Process> processes, ofstream& outputFile)**: Simulates Shortest Remaining Time First scheduling.
- **roundRobin(vector<Process> processes, int quantum, ofstream& outputFile)**: Simulates Round Robin scheduling.
- **predictBestAlgorithm(vector<Process>& processes)**: Predicts the best scheduling algorithm based on process information.
- **runScheduler()**: Main function to read input, run predictions and simulations, and write output.

## Notes

- Ensure the input file `input1.txt` is properly formatted.
- The output file `output1.txt` will be overwritten each time the program runs.
