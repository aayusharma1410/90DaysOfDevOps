# Linux Architecture Notes

## 1. Core Components of Linux

### Kernel
- The kernel is the core of the Linux operating system.
- It acts as a bridge between hardware and software.
- It manages CPU, memory, disk, and network resources.
- User programs interact with hardware through system calls provided by the kernel.

### User Space
- User space is where user applications and commands run.
- Examples include the shell (bash), utilities (ls, ps), and other programs.
- User space programs cannot directly access hardware; they communicate via the kernel.

### init / systemd
- systemd is the first process that starts when the system boots.
- It is responsible for starting and managing system services.
- systemd ensures that services start in the correct order.

---

## 2. Processes in Linux

### What is a Process
- A process is an instance of a running program.
- Each process has a unique Process ID (PID).

### Process Creation
- A new process is created using the `fork()` system call.
- The `exec()` system call is used to run a new program inside a process.

### Process States
- **Running**: The process is currently executing on the CPU.
- **Sleeping**: The process is waiting for input or a resource.
- **Stopped**: The process has been paused, usually by a signal.
- **Zombie**: The process has finished execution, but its parent has not yet read its exit status.

---

## 3. systemd Overview

- systemd is the init system and service manager in modern Linux systems.
- It controls system startup, services, and background processes.
- It can automatically restart services if they fail.
- system logs are managed centrally using the systemd journal.

Why systemd matters:
- Helps in quick recovery during service failures
- Makes service management easier
- Essential for managing production Linux servers

---

## 4. Commonly Used Linux Commands

- `ps` – Displays a list of currently running processes.
- `top` – Shows real-time CPU and memory usage.
- `systemctl` – Used to start, stop, and manage systemd services.
- `journalctl` – Used to view system logs.
- `kill` – Sends a signal to terminate a process.
