2 Kinds of probes
- [[readiness-probe]]
- [[liveness-probe]]
- [[startup-probe]]

## 3 different ways to configure these probes
#### HTTP Probes
Any code **greater than or equal to 200 and less than 400** indicates success. Any other code indicates failure.
```yaml
spec:
  containers:
  - name: liveness
    livenessProbe:
      httpGet:
        path: /healthz
        port: 8080
```

#### Command Probes
If the command return `exit code: 0` then the container is healthy else it isn't.
Use case: When you dont like http. XD
```
spec:
  containers:
  - name: liveness
    livenessProbe:
      exec:
          command:
          - myprogram
```

#### TCP Probes
Establish TCP connection, If if connects the the probe is healthy, else it isn't.
Use case: gFPC or FTP
```yaml
spec:
  containers:
  - name: liveness
    livenessProbe:
      tcpSocket:
        port: 8080
```

>see more: [[configuring-probes]]