# docker + Python3.7 + Flask + nginx + uwsgi + MySQL5.7 + 

## Install Docker
### Ubuntu
```
    sudo apt install -y apt-transport-https ca-certificates software-properties-common
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable test edge"
    sudo apt update
    sudo apt install -y docker-ce
    sudo gpasswd -a ${USER} docker
    sudo chmod 666 /var/run/docker.sock
    export compose='1.21.1'
    docker -v # check
    docker-compose -v # check
```

## Usage
### Start
```
# make run
```

### Stop
```
# make stop
```


## 構成
```
.
├── Makefile
├── README.md
├── docker-compose.yml
├── app
│   ├── Dockerfile
│   ├── requirements.txt
│   ├── src
│   │   ├── config
│   │   │   ├── __init__.py
│   │   │   └── default.py
│   │   ├── run.py
│   │   ├── server
│   │   │   ├── __init__.py
│   │   │   └── hoge
│   │   │       ├── __init__.py
│   │   │       └── hoge_api.py
│   │   └── tests
│   │       ├── __init__.py
│   │       └── test_hoge.py
│   └── uwsgi.ini
├── nginx
│    ├── Dockerfile
│    └── nginx.conf
├── db
│    ├── Dockerfile
│    └── charset.cnf
└── storage
      └── Dockerfile
```

## ref)

 - [Flaskスケルトン](https://github.com/lboavde1121/flaskapp)
 - [Django Development With Docker Compose and Machine](https://github.com/fujimisakari/django-docker)

