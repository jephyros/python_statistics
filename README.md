아나코드 도커 환경

1. 작업할 폴더를 만들고 해당폴더로 접근
    mkdir ~/docker/anaconda
    cd ~/docker/anaconda

2. 도커 이미지 실행

    docker run -d --name anaconda -p 8888:8888 -d -v $(pwd):/notebooks continuumio/anaconda3
    $(pwd):/notebooks 의미 -> 도커이미지내의 notebooks 데이터를 현재디렉토리에 저장

3. 도커이미지내의 bash shell 로 접근 및 주피터실행

    docker exec -it anaconda /bin/bash
    mkdir notebooks
    cd notebooks
    jupyter notebook --ip='*' --port=8888 --no-browser --allow-root
    여기까지하면 브라우저료 localhost:8888 로 접속하면 주피터 노트북을 사용할수있다.