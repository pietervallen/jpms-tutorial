## Download, install and verify JDK

#### Download and install latest version of the JDK 10

- Download JDK 10 from Oracle
  
  - http://www.oracle.com/technetwork/java/javase/downloads/jdk10-downloads-4416644.html

- Install JDK 10 manually

    - Linux
       - `tar -xvf jdk-10.0.1_linux-x64_bin.tar.gz`
       - `mv -f jdk-10.0.1 [destination]`  
       - update your `.bashrc` with `export JAVA_HOME=[jdk destination]`
       - update your `.bashrc` with `export PATH=$JAVA_HOME/bin:$PATH`
       - `source ~/.bashrc` 
    
         `[destination]` I used: ~/bin/jdk-10.0.1
    
    - Tip: Put this in your bashrc for easy switching
    
    ````
     JDK8=/usr/lib/jvm/java-8-oracle/jre
     JDK10=/home/gp74xf/bin/jdk-10.0.1
     
     while true; do
       read -p "What JAVA_HOME do you want to set for this shell <8, 10>?" version
         case $version in
             [8]* )
                 export JAVA_HOME=$JDK8;break;;
             [10]*)
                 export JAVA_HOME=$JDK10;break;;
             *)
                 echo "You should fill in 8 or 10!"
             ;;
       esac
     done
     ````
 
##### Verify JDK installation

###### java

Say you have downloaded and installed the JDK 9 EA (build 165) binary from the above step, try the below commands:

```
    $ java -version
```

As output you should get something like this:

```
    java version "10.0.1" 2018-04-17
    Java(TM) SE Runtime Environment 18.3 (build 10.0.1+10)
    Java HotSpot(TM) 64-Bit Server VM 18.3 (build 10.0.1+10, mixed mode)
```

###### javac

```
    $ javac -version
```

As output you should get something like this:

```
    javac 10.0.1
```

###### jshell

Verify if `jshell` is available in your current environment:

```
    $ jshell --version
```

As output you should get something like this:

```
    jshell 10.0.1
```

###### jdeps

Verify if `jdeps` is available in your current environment:

```
    $ jdeps --version
```

As output you should get something like this:

```
    10.0.1
```
