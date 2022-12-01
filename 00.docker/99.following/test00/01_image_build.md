# image build

```bash
$ docker build -t my-imagemagick . 
```

## Error
```
E: Unable to locate package imagemagick
The command '/bin/sh -c apt-get install imagemagick' returned a non-zero code: 100
```

### Solution
update package list
```
RUN apt update
```
