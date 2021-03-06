# Monitoring Tools
* jconsole - graphical console to monitor and manage Java apps
* jps - experimental:  list of instrumented JVMs on the target system
* jstat - experimental: monitors JMV statistics
* jstatd - experimental: monitors JVMs and enables remote monitoring tool to attach to JVM
* jmc - Java Mission Control


# Troubleshooting Commands
A list of common commands used during the troubleshooting process is mentioned below. 
Please check the syntax during the execution.

### Thread Count  
`cat /proc/<pid>/status | grep Threads`

`ps uH p <pid>`

### Heap Configuration
`java -XX:+PrintFlagsFinal -version | grep HeapSize`

### Thread Dump
`jstack <<pid>>` [Take Thread dumps in some interval say 15 secs for 1 min]

### Thread Stack Size
`java -XX:+PrintFlagsFinal -version | grep ThreadStackSize`

### Others
`pmap –x <<pid>>`

`top`

`nestat -a | grep <<port number>>`

`kill -9 <<pid>>`

`kill -3 <<pid>>`

`ps –ef| grep –i java`

`/bin/jstat –gc <pid>`

`jstat -gc <pid> | tail -l | awk '(split($0,a," "); sum=a[3]+a[4]+a[6]+a[8];`
`print sum " Kb")'`

`/bin/jmap –heap <pid>`
