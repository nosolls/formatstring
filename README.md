# Format-String Vulnerability

## Descripition of the scenario
The format-string vulnerability is caused by code like printf(user_input), where the contents of variable of user_input is provided by users. When this program is running with privileges (e.g., Set-UID program), this printf statement becomes dangerous, because it can lead to one of the following consequences: (1) crash the program, (2) read from an arbitrary memory place, and (3) modify the values of in an arbitrary memory place. 

## Target Audience

### Instructors
If you're an instructor in cypersecurity concepts or a field related, this would be a great opportunity to teach your students on the vulnerability from a hands-on approach. The lab covers how to weaken a system for the vulnerability to be possible. This lab will have the students attempt to crash the program and modify secret values that are stored in memory.

### Students
A student in cybersecurity concepts or a field related could use this lab to see how this kind of programming can be exploited. This could also give them the chance to get a head start in their classes if they have not covered the format-string vulnerability.

## Design and Architecture
This lab only has one container, which is the hacker. It provides all of the tools you might need. This lab will run off of VNC. The user will run all commands needed on the terminal provided by LXDE. This includes having to disable randomization, compiling the programs, etc.

## Installation and Usage

### Installation
To build the container via docker:

```bash
cd hacker
docker build -t <image tag name> .
```

To get the container running for the user:

```bash
docker run -d -p 80 --cap-add=SYS_PTRACE --security-opt seccomp=unconfined <image tag name>
```
### Usage
After going to the URL, you'll find a VNC client to greet you. CHEESEHub has the instructions provided by the [SEED Project](https://seedsecuritylabs.org/index.html). 
