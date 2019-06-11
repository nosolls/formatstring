# Format-String Vulnerability

## Descripition of the scenario
The format-string vulnerability is caused by code like printf(user_input), where the contents of variable of user_input is provided by users. When this program is running with privileges (e.g., Set-UID program), this printf statement becomes dangerous, because it can lead to one of the following consequences: (1) crash the program, (2) read from an arbitrary memory place, and (3) modify the values of in an arbitrary memory place.

## Target Audience

### Instructors
If you're an instructor in cypersecurity or computer programming, this would be a great opportunity to teach your students on the vulnerability from a hands-on approach. Specififically, the uses of the vulnerability and how to protect against it. 

## Installation and Usage

### Installation
Only one container is needed for this lab. To build it via docker:

```bash
cd hacker
docker build -t <hacker image tag of your choice> .
```

Jupyter is also used for the user's interaction with the container. To get the container running for the user:

```bash
docker run -d -p 8888 <hacker image tag of your choice
```
