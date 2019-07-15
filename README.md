# Format-String Vulnerability

## Descripition of the scenario
The format-string vulnerability is caused by code like printf(user_input), where the contents of variable of user_input is provided by users. When this program is running with privileges (e.g., Set-UID program), this printf statement becomes dangerous, because it can lead to one of the following consequences: (1) crash the program, (2) read from an arbitrary memory place, and (3) modify the values of in an arbitrary memory place. 

## Target Audience

### Instructors
If you're an instructor in cypersecurity concepts or a field related, this would be a great opportunity to teach your students on the vulnerability from a hands-on approach. Specififically, the uses of the vulnerability and how to protect against it. 

### Students
A student in cybersecurity concepts or a field related could use this lab to see how programming can be exploited. This could also give them the chance to get a head start in their classes if they have not covered the format-string vulnerability yet.

## Design and Architecture
This lab only has one container, which is the hacker. It provides all of the tools you might need. Jupyter offers a text editor/terminal, which offers keybindings (like for vim) if you prefer them. 


## Installation and Usage

### Installation
To build the container via docker:

```bash
cd hacker
docker build -t <hacker image tag of your choice> .
```

Jupyter is also used for the user's interaction with the container. To get the container running for the user:

```bash
docker run -d -p  --cap-add=SYS_PTRACE --security-opt seccomp=unconfined 80 <hacker image tag of your choice>
```
### Usage
CHEESEHub has the instructions provided by the [SEED Project](https://seedsecuritylabs.org/index.html). For this container, be sure to compile vul_prog.c as vul_prog. This will make sure you can run it with sudo.
