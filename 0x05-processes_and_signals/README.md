# Processes and Signals

[What is a Process?](./What is a Process?):
A process can be thought of as an instance of a program in execution. We called this an ‘instance of a program’, because if the same program is run lets say 10 times then there will be 10 corresponding processes.

Moving ahead, each process has its own unique process ID through which it is identified in the system. Besides it own ID, a parent’s process ID is also associated with a process.

The main() Function
A ‘C’ program always starts with a call to main() function. This is the first function that gets called when a program is run.

The prototype of a main() function is :

int main(int argc, char *argv[]);

[What is a signal?](./What is a signal?): Signals are software interrupts.

A robust program need to handle signals. This is because signals are a way to deliver asynchronous events to the application.

A user hitting ctrl+c, a process sending a signal to kill another process etc are all such cases where a process needs to do signal handling.

Linux Signals
In Linux, every signal has a name that begins with characters SIG. For example :

* A SIGINT signal that is generated when a user presses ctrl+c. This is the way to terminate programs from terminal.
* A SIGALRM  is generated when the timer set by alarm function goes off.
* A SIGABRT signal is generated when a process calls the abort function.
etc

Learning Objectives
At the end of this project, you are expected to be able to explain:

 * What is a PID
 * What is a process
 * How to find a process’ PID
 * How to kill a process
 * What is a signal
 * What are the 2 signals that cannot be ignored

## General Requirements

- Allowed editors: vi, vim, emacs
- All your files will be interpreted on Ubuntu 20.04 LTS
- All your files should end with a new line
- A README.md file, at the root of the folder of the project, is mandatory
- All your Bash script files must be executable
- You are not allowed to use awk
- Your Bash script must pass Shellcheck (version 0.7.0) without any error
- The first line of all your Bash scripts should be exactly #!/usr/bin/env bash
- The second line of all your Bash scripts should be a comment explaining what is the script doing
