Short-Term Scheduler for Operating Systems
This project simulates a short-term scheduler for an operating system. The scheduler determines the time quantum for processes in the ready queue based on dynamic calculations. It also simulates context switching between processes to demonstrate how CPU scheduling operates in real-world systems.

Features
Dynamic Ready Queue Management:
The number of processes in the ready queue is determined based on the current simulation step.
Time Quantum Calculation:
Time quantum for each process is calculated using a combination of:
Process execution time.
Total execution time.
A unique identifier (e.g., last digit of a roll number).
Process Context Switching:
Simulates processes moving between the RUNNING and READY states.
Flexible Parameters:
Parameters like ALPHA, process times, and total execution time can be adjusted for different scenarios.
How It Works
Processes in the Ready Queue:

The number of processes is dynamically determined by the formula:
c
Copy
Edit
(step % MAX_READY_QUEUE_SIZE) + 1
MAX_READY_QUEUE_SIZE is the maximum number of processes allowed in the ready queue.
Time Quantum Calculation:

The time quantum for each process is calculated as:
c
Copy
Edit
pow(ALPHA, (n_process + d))
Where:
n_process = process_time / total_execution_time
d = last digit of a roll number (simulated with ROLL_NO).
Context Switching:

Each process in the ready queue transitions between the RUNNING and READY states, simulating a real CPU scheduler.
Code Structure
processes_in_ready_queue(int step):

Determines the number of processes in the ready queue for the given simulation step.
calculate_n(float process_time, float total_execution_time):

Calculates the ratio of process execution time to total execution time.
get_last_digit():

Returns the last digit of the roll number (ROLL_NO) as an integer.
Main Function:

Simulates 5 steps of scheduling.
For each step:
Calculates the number of processes in the ready queue.
Performs context switching for each process.
Computes the time quantum for processes A and B.
Displays the results.
Example Output
plaintext
Copy
Edit
Step 1 - Number of processes in the ready queue: 2
Step 1 - Time quantum for Process A: 1.28
Step 1 - Time quantum for Process B: 1.32

Step 2 - Number of processes in the ready queue: 3
Step 2 - Time quantum for Process A: 1.28
Step 2 - Time quantum for Process B: 1.32

...
How to Run
Requirements:

A C compiler (e.g., GCC).
Basic knowledge of C programming.
Steps:

Clone or download the project files.
Open a terminal in the project directory.
Compile the code:
bash
Copy
Edit
gcc scheduler.c -o scheduler -lm
Run the program:
bash
Copy
Edit
./scheduler
Customization
Adjustable Parameters:
Modify constants like ALPHA, total_execution_time, process_A_time, and process_B_time in the main function for different scenarios.
Ready Queue Size:
Change MAX_READY_QUEUE_SIZE to alter the maximum number of processes in the ready queue.
Limitations
The simulation assumes predefined constants like ROLL_NO and ALPHA.
Context switching (change_process_context) is a placeholder and does not perform actual state management.
The scheduler does not simulate advanced scheduling algorithms (e.g., priority or round-robin).
Future Improvements
Add support for more complex scheduling algorithms (e.g., Round-Robin, Priority Scheduling).
Simulate real-time process execution with delays or timers.
Integrate with a GUI for visualizing the scheduler's operations.
Expand context-switching logic to manage actual process states.
License
This project is licensed under the MIT License. See the LICENSE file for details.
