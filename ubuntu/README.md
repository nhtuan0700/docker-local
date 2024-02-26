This example is used for demo immutable of image
There are 2 case
1. Use origin image ubuntu
2. Run myubuntu built from origin image ubuntu

---
1. Use origin image ubuntu
- `docker pull ubuntu:20.04`
- `docker run -it ubuntu bash`
- `apt-get update && apt-get install`
- `apt-get install -y mysql-server nodejs`
- check: 
  - `node -v`
  - `mysql --version`
- Then stop container
- `docker run -it ubuntu bash`
- check again: 
  - `node -v`
  - `mysql --version`

2. Run myubuntu built from origin image ubuntu
- make Dockerfile
```dockerfile
FROM ubuntu:latest

RUN apt-get update \
  && apt-get install \
  && apt-get install -y mysql-server nodejs
```
- `docker build -t myubuntu:1.0 bash`
- check: 
  - `node -v`
  - `mysql --version`
