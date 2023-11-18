# Day 6 - Linux and Shell Scripting

## Operating System

- acts as an interface between Software and Hardware
- Basically each software is a set of programs, each program is a set of instructions, each instruction is a set of 0s and 1s, each 0 or 1 is just an electrical signal that runs in hardware
- Thus running a software is basically managing the hardware/ resources which is done by OS

## Functions of Operating System

- Memory Management
- Process Management
- Device Management
- Handling System Calls
- File Management
- User Interface
- Security
- Network Management and many more

## Why Linux ?

- Open source, Free
- Highly secure
- Many distributions (based on use case)
- Very fast

## Architecture of Linux

```text
				 -----------------------------------
				| System    | User      | Compilers |
				| Software  | Processes |           | 
				 -----------------------------------
				|        System Libraries           |
				 -----------------------------------
				|             Kernel                |
				 -----------------------------------
				|        Operating System           |
				 -----------------------------------
```

### Kernel

- The heart of Linux Operating System, actually manages the resources of a system
- Operating System = Kernel + System Libraries (Device Drivers, System Utilities, etc)
- The core features of OS are actually done by Kernel

## Shell Scripting

- Shell is an interface between User and Operating System
- Using shell commands in a command line shell, we interact with the OS

### Popular Shell Commands

```sh
# List all contents (files and folders) in the current directory
ls

# Display current location (Absolute Path)
pwd

# Create a Directory
mkdir bundle

# Change Directory (go into bundle)
cd bundle

# Change directory (move back one directory)
cd ..
# cd ../..

# List all contents with metadata
ls -ltr

# Create a file
touch myfile

# Edit a file, create if file doesn't exist
## Escape + i => Insert Mode
## Make changes as desired
## Esc, then !wq => Exit
vi myfile

# Print the contents of a file
cat myfile

# Delete a file
rm myfile

# Delete a Directory
rm -r bundle
```

### Checking CPU, Memory and Disk Size

```sh
# For Memory details
free -g

# Number of CPUs
nproc

# For Disks Size
df -h

# Complete Information (Memory, CPU, Disks)
top
```