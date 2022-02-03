# Containers
https://www.docker.com/resources/what-container

- Standard unit of software
- Packages code + all dependencies
- App runs quickly, reliably across multiple environments

## Docker container
- Code
- Runtime
- System tools
- Libraries
- Settings

- isolate software from its environment
- Works uniformly
  - Standard - runc, to the Open Container Initiative (OCI)
  - Lightweight
  - Secure   
- Run on Docker Engine

## Containers vs VMs
| Containers | VMs |
|---|---|
| Abstraction of App Layer | Abstraction of Hardware - 1 server as many| 
| Multiple containers can run on 1 machine | Hypervisor allows many VMS to run on 1 machine  |
| Less space | More space - copy of OS | 

