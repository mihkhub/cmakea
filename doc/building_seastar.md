@file: building_seastar.md

# Building Seastar

Seastar requires g++ >= 4.9.  Install g++-4.9 or later (use --compiler option).

## Building seastar on CentOS 7
- Installing required [install-dependencies.sh](install-dependencies.sh):

    ```$ sudo install-dependencies.sh```
    
- Active environment:

     ```$ source /etc/profile.d/scylla.sh```
     
- Validate `g++`:
   
   ```
   $ g++-7.2 --version
      g++-7.2 (GCC) 7.2.1 20170829 (Red Hat 7.2.1-1)

   $ g++ --version
      g++ (GCC) 4.8.5 20150623 (Red Hat 4.8.5-16)
     ```
     
- Building demo:
  
    ```ninja-build```
    
- Download seastar:
     ```
     $ git clone git@github.com:scylladb/seastar.git
     $ cd seastar/
     $ git submodule update --init --recursive
     ```
 - Checking out Tag `seastar-17.05.0`:
    ```
    $ git checkout -b seastar-17.05.0 seastar-17.05.0
    ```
 - configure:
   ```
   $ ./configure.py --compiler=/opt/scylladb/bin/g++-7.2 --static-stdc++

    ```
    
## Building seastar in Docker container

To build a Docker image:

```
docker build -t seastar-dev docker/dev
```

Create an shell function for building insider the container (bash syntax given):

```
$ seabuild() { docker run -v $HOME/seastar/:/seastar -u $(id -u):$(id -g) -w /seastar -t seastar-dev "$@"; }
```

(it is recommended to put this inside your .bashrc or similar)

To build inside a container:

```    
$ seabuild ./configure.py --static
$ seabuild ninja-build
```
## References
- [Building Seastar on CentOS](https://github.com/scylladb/seastar/blob/master/doc/building-centos.md)
- [Building seastar in Docker container](https://github.com/scylladb/seastar/blob/master/doc/building-docker.md)

