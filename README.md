#### psredhatentlinuxshfunda
#####diff types of shell
######current
```
ps -p $$            //get current shell's progress
echo $0         //which program starts echo program?
```
######shells
parent shell and child shell
PID and PPID(parent pid)
```
ps -ef
pstree
```
######login shells
```
ls -lh /bin/ |grep bash
```

```
hexdump -C /bin/bash
```
###### edit login shell
in /etc/passwd
```
/bin/bash->/sbin/nologin
```

get shell variable
```
echo $SHELL
```

#####standard streams
######what
```
whoami
who am i
```

######no clobber
```
set -o noclobber   //can not use > to overrite,must use   like `echo xx >| file`
```
restore
```
set +o noclobber
```
######
we start two terminals,connecting to same machine
machine1:
```
file /dev/pts/*
ls -l /etc >/dev/pts/2
echo "x" > /dev/pts/2
```
######stderr
```
ls -l /dev/std*
```

#####shell env
######intro
```
echo $HOSTNAME $BASH_VERSION
```
get all vars:
```
set
```
######expanding var
a = 3
```
echo $a  //3
echo '$a' //$a
echo "$a"  //3
echo \$a  //$a
```

######customize
```
/etc/profile ->/etc/profile.d
```
#####shell commands
######command history
```
env |grep HIST
```
######backgroundding
```
jobs
```
create a bg job:
```
sleep 600 &   //sleep 10 min
```
and again
```
jobs
```
if shows plus sign, means we can use
```
fg
```
to retrieve it, and ctrl z to suspend.
