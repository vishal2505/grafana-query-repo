# OS Metrics 

### Node Memory -

1. Node Memory

```
node_memory_MemAvailable_bytes{instance=~"wh-1234567.svr.us.jpmchase.net:9100"}/1024/1024/1024
```


2. Node Memory < 64 GB for multiple host

```
ceil(node_memory_MemAvailable_bytes{instance=~"wh-1234567.svr.us.jpmchase.net:9100|wh-09876541.svr.us.jpmchase.net:9100"}/1024/1024/1024) <=64
```

3. Host having RAM > 90%

```
sort_desc(((1 - (node_memory_MemAvailable_bytes{instance=~"(${hostname}):9100"} / (node_memory_MemTotal_bytes{instance=~"(${hostname}):9100"}))) *100) > 90)
```


### Disk Usage

1. DIsk used more than 80%

```

```
