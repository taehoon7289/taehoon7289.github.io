## 인스턴스 Asia/Seoul 로 시간 설정
<pre>
  <code>
    $ ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime
  </code>
</pre>


## docker-compose 설치 및 사용방법
- centOS 기준이며 yum 으로 패키지 설치 과정
- yum 사용시 root권한이 필요하므로 $ sudo -s 으로 root권한으로 진행 
0. git 설치
<pre>
  <code>
    $ yum update
    $ yum install -y git
  </code>
</pre>

1. docker-ce, docker-compose 설치 (docker-compose 는 https://github.com/docker/compose/releases 에서 버전 확인후 원하는 버전으로 설치)

<pre>
  <code>
    $ yum install yum install -y yum-utils device-mapper-persistent-data lvm2
    $ yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    $ yum install -y docker-ce
    $ usermod -aG docker $USER
    $ id $USER
    $ curl -L https://github.com/docker/compose/releases/download/1.25.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
    $ chmod 755 /usr/local/bin/docker-compose
    $ ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
    $ service docker start
    $ docker ps
  </code>
</pre>

2. /home 디렉토리로 이동
<pre>
  <code>
    $ cd /home
  </code>
</pre>

3. 현재 github clone
<pre>
  <code>
    $ git clone https://github.com/taehoon7289/docker-compose.git
  </code>
</pre>

4. /home 에서 docker-compose 디렉토리 생성되며, docker-compose 로 이동
<pre>
  <code>
    $ cd /home/docker-compose
  </code>
</pre>

5. .env 파일에 각 환경에 맞는 변수값 지정(.env-gcp, .env-local 참고)
<pre>
  <code>
    $ vi /home/docker-compose/.env
  </code>
</pre>

6. docker-compose.yml 변경할 값이 있는경우 변경
<pre>
  <code>
    $ vi /home/docker-compose/docker-compose.yml
  </code>
</pre>

7. httpd 의 conf 값 설정 및 Dockerfile EXPOSE 값 변경
- apache2 디렉토리 내부의 conf값 설정시 포트를 변경되었을 경우
Dockerfile 의 EXPOSE 값도 함께 변경해줘야함.
<pre>
  <code>
    $ cd /home/docker-compose/build/httpd/apache2 // httpd 디렉토리 
    $ vi /home/docker-compose/build/httpd/apache2/conf/extra/vhosts.conf // 가상호스트 설정
    $ vi /home/docker-compose/build/httpd/apache2/conf/extra/ssl.conf // ssl 가상호스트 설정
    $ vi /home/docker-compose/build/httpd/apache2/conf/extra/listen.conf // 포트 설정
  </code>
</pre>

8. 시작/종료/재시작 (/home/docker-compose 위치에서 아래 명령어 실행해야함.) 
<pre>
  <code>
    $ cd /home/docker-compose
    $ docker-compose up -d --build
    $ docker-compose kill
    $ docker-compose restart // Dockerfile변경 없는경우
  </code>
</pre>
