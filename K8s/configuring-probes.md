- initialDelaySeconds
- periodSeconds
- timeoutSeconds
- successThreashold
- failureThreashold


## IMPORTANT while configuring livenessProbe
>**you MUST configure the `initialDelaySeconds`** in livenessProbe

this is because, if you dont there can be the following problem(s)
- livenessProbe will start checking the container even before the app is ready(it takes some time for the app to be ready)
- if it is "not ready" then the container is restarted, this can lead to the container never starting at all.

>**P99** as buffer time, or **average startup time** can be used for `initialDelaySeconds`