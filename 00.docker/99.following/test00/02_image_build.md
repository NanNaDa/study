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


## Error 2
```
#6 2.414 Do you want to continue? [Y/n] Abort.
------
executor failed running [/bin/sh -c apt install imagemagick]: exit code: 1
```

### Solution
패키지 설치할지 여부를 묻고 있는데 입력을 해주지 않았기 때문에 에러 발생 : `-y` 추가   
| Before | | After |
|-|-|-|
| RUN apt install imagemagick | -> | RUN apt install -y imagemagick |



## Run
```bash
$ docker run -d my-imagemagick
```











