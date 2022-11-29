# Study Docker

## run
```bash
$ docker run -d -p 80:80 docker/getting-started
```

- `-d` : 백그라운드에서 분리 모드로 컨테이너를 실행합니다.
- `-p 80:80` : 호스트의 포트 80을 컨테이너의 포트 80에 매핑합니다.
- `docker/getting-started` : 사용할 이미지를 지정합니다. 


# Docker

## container
```ssh
$ docker ps
```

### create a container
```ssh
$ docker create -it --name [container name][image name]
$ docker create -it --name python_container -p 8888:8888 leesebin/setup_python:02
```

### start a container
```ssh
$ docker start [container name]
```

### stop a container
```ssh
$ docker stop [container id]
```

### delete a container
```ssh
$ docker rm [container id]
```

### attach container 
```ssh
$ docker attach [container name]
```

### 진입한 컨테이너 종료 하지 않고 빠져나오기
```ssh
 ctrl + p, q
```

## images
```ssh
$ docker images
```

### download image
```ssh
$ dockr pull [image name]
```


## Example
```ssh
$ docker run --gpus all --rm -it -p 8282:8888 -v $HOME/ai-basics:/tf --workdir=/tf --name ai-basics tensorflow/tensorflow:latest-gpu-jupyter
```

-- gpus all : gpu 모두 할당 (컨테이너에서 서버 gpu를 모두 사용할 수 있도록 함)
-- rm : 컨테이너 종료 시 자동으로 삭제
-it : 해당 컨테이너의 쉘(shell)과 직접 상호작용 하면서 명령어 실행 가능
-p : (8282:8888) 서버의 포트 8282와 컨테이너의 포트 8888연결
-v : ($HOME/ai-basics:/home) 서버의 HOME/ai-basics와 컨테이너의 home 연결
--workdir : (=/home) 컨테이너의 작업폴더를 /home으로 설정
--name : (ai-basics) 컨테이너의 이름을 ai-basics로 설정
tensorflow/tensorflow:latest-gpu-jupyter : 사용할 이미지 이름


## 컨테이너에서 jupyter notebook 실행
```ssh
$ jupyter notebook --ip='0.0.0.0' --port=8888 --allow-root
```
