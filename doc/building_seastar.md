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
 - configure:
   ```
   $ ./configure.py --compiler=/opt/scylladb/bin/g++-7.2 --static-stdc++

    ```



