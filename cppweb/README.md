# Introduction

This is the codes when I learn the course [Web Server and APIs using C++](https://www.linkedin.com/learning-login/share?account=3322&forceAccount=false&redirect=https%3A%2F%2Fwww.linkedin.com%2Flearning%2Fweb-servers-and-apis-using-c-plus-plus%3Ftrk%3Dshare_ent_url%26shareId%3DZLbDKBIcSCem8g8Gyrjczw%253D%253D)
## Install Tools

### Write the Dockerfile

The [Dockerfile](./cppbox/Dockerfile)

### Build the Dockerfile

```bash
cd cppbox
docker build -t cppbox .
```

### Run the Dockerfile

```bash
docker run -it cppbox bash
find /usr -name libboost*.*
```

### Add volume

```bash
docker run -it -v <host>:<container> <image> bash
```

### Build Crow

Add directory `hello_crow`, add `CMakeLists.txt` and `hello_crow.cpp`

build the project

```bash
docker run -it -v $(pwd)/hello_crow:/home/cppbox/hello_crow cppbox bash
cd hello_crow
mkdir build
cd build
cmake ..
make
```

To run the app, we need to add the port mapping: 

```bash
docker run -it -v <host>:<container> -p <host>:<container> <image> bash
```

Run the app

```bash
docker run -it -v $(pwd)/hello_crow:/home/cppbox/hello_crow -p 8080:8080 cppbox bash
cd build
./hello_crow
```
