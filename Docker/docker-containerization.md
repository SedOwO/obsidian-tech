### Directives
#### `FROM` :
Builds this image from the specified images
```dockerfile
FROM python:3.12.3
```

#### `RUN` :
```dockerfile
RUN 
```

#### `COPY`:
**Copy** the files from the host and paste them into the container
```dockerfile
COPY <src> <dest>
```

#### `WORKDIR`:
Sets the **working directory** for all the following commands, like `cd ..` etc.
```dockerfile
WORKDIR <dir_name>
```

#### `CMD`:
The **final** command to be run, 
```dockerfile
CMD ["", ""]
```

containerize the application: [[docker-commands#`build` the docker file|docker build]]
