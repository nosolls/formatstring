# Format String Vulnerability

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
