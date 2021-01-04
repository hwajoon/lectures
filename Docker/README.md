# Ubuntu 참고 자료
<code><pre>
https://goddaehee.tistory.com/251
https://ghostweb.tistory.com/979
</pre></code>

# ubuntu & Virtualbox 다운로드
<code><pre>
* ubuntu 이미지 다운로드 (확장자가 ova)
* 버츄얼 박스 다운로드 (https://www.virtualbox.org/wiki/Downloads) / select the Windows hosts.
</pre></code>

# 2.  
▶ 1. 도커란?
도커 설치와 관련된 포스팅 이기에 아주 간단히 도커가 어떤 것이지  살펴만 보고 바로 설치 하는 방법을 알아보자.
- 도커 공식 홈페이지에는 "Docker는 컨테이너(Container) 이동을 주도하는 회사, 하이브리드 클라우드의 모든 애플리케이션을 처리할 수 있는 유일한 컨테이너 플랫폼 제공 업체" 라고 되어 있다.

 - 도커는 컨테이너 기반의 오픈소스 가상화 플랫폼 이다.
 - 컨테이너란 "다양한 OS에 여러 application이 올려져 있는 것 이라고 볼 수 있다.
 - 도커에서 의미하는 컨테이너란
    택배나 화물선 위에 수출 용품을 싣는 컨테이너를 대신하여 프로그램(소프트웨어)을 담는 격리된 공간을 의미 한다.
 - 각각의 격리된 여러개의 소프트웨어 컨테이너에는 ubuntu, centos등의 운영체제,
   그리고  java, python, 아파치 웹서버나, mysql 같은 dbms 등의 프로그램들 까지도 담기게 된다.
 - 그리고 각 컨테이너는 격리된 공간이기 때문에 한 컨테이너가 해킹을 당하던, 한 컨테이너에 문제가 생기더라도 컨테이너간에 영향을 끼치지 않는다.

이러한 도커의 특성 때문에 다음과 같은 장점이 있다고 정리할 수 있다.

▶ 2. 도커의 장점?
1) 빠르고 가벼운 가상화 솔루션 
 - 호스트의 운영체제를 공유하여 필요한 최소한의 리소스만 할당받아 동작하는 방식 이기때문에 가볍다. 
 - 즉 ,기존 Hypervisor 엔진을 사용하지 않고, Docker Engine을 통해 Guest OS 없이 실행 가능하다. Guest OS가 없기 때문에 가상머신보다 훨씬 빠른 실행 속도를 보장할 수 있다. 
 - 하드웨어 가상화를 하지 않기 때문에, 메모리 엑세스, 파일 시스템, 네트워크 실행 성능도 뛰어나다.

2) 개발언어에 종속되지 않는다.
 - 개발 언어나 툴에 상관없이 어떠한 애플리케이션이라도 만들 수 있으며, Docker에서 만들어진 애플리케이션은 이동성이 뛰어나며 어디서나 실행될 수 있다.

3) 뛰어난 보안성
 - 서비스가 해킹시에도 각 컨테이너들은 격리되어있기 때문에 원래의 서버에 영향을 미치지 않는다.

▶ 3.  Window10 도커 설치하기
1) 도커 설치전 환경 설정
 - 도커를 사용하기 위해서 가상화 기술인 Hyper-V를 활성화시켜야한다.
 - 우선 작업 관리자에서 가상화를 사용함으로 설정했는지 확인 한다. (안되어 있는 경우 BIOS 에서 사용함으로 설정해야 한다.)
 - 제어판 > 프로그램 설치 및 제거 > Window 기능 켜기/끄기 클릭 > Hyper-V 체크 확인 후 리부팅

2) 도커 설치파일 다운로드 및 설치
 - 다음 사이트 접속 > Get Docker 클릭 하여 다운로드
 - https://hub.docker.com/editions/community/docker-ce-desktop-windows/
 - 다운로드 완료한 도커 설치 파일을 실행한다.
 - Use Windows containers instead of Linux containers(this can be changed after installation)  : 리눅스 컨테이너 대신 윈도우 컨테이너를 사용할껀지 물어보는 항목이다.
 - 이 항목은 언제든지 설치 후에도 바꿀 수 있으니 그냥 넘어 간다. (OK 클릭)
 - 참고 (2.2.0.5 Version)
 - 참고 (3.0.0 Verision) (동일하게 OK 클릭)
 - 도커 설치가 진행 중이다.
 - 설치가 완료 되면 "Close and restart" 를 클릭하여 재부팅 하여 준다.
 - 재부팅 하면 도커를 사용할 준비 중이고, 사용할 준비가 완료 되면 우측 하단에 다음과 같은 메뉴가 생기는 것을 확인할 수 있다.
 - 도커실행시 다음과 같은 오류 메세지가 나오는 분들은 해당 링크로 가서 관련 파일을 설치해 준 후 재기동 하면 된다.
 - 도커를 사용하기 위해 회원 가입이 안되어 있는 경우 회원 가입을 진행 해주자.
 - ID, Email, Password 입력하고 Sign Up 하여 진행.
 - 나와 같은 경우에는 무료로 사용 하는 플랜을 선택 하였다.
 - 플랜 선택 완료 후 이메일 인증을 진행 한다.
 - 이메일 확인 후 "Get started with Docker Desktop"을 클릭 하여 준다.
 - 사용할 준비는 완료 되었고, 튜토리얼을 볼 수 있는데, 따라 해보면 된다.
 - 튜토리얼이 완료 되면 다음과 같은 화면을 볼 수 있다.
 - CMD 에서 "docker -v" 실행해보면 올바르게 도커가 설치된 것도 볼 수 있다.

▶ 4.  Kitematic 설치 (도커를 쉽게 GUI로  사용 가능하다)
1) 다운로드 하여 실행만 하면 현재 시점에서 별도의 설치는 필요없다.
 - 다음 URL 접속하여 각자의 OS (이번 포스팅에선 Window)에 맞게 다운로드 후 압축 해제 하여 주자.
 - www.github.com/docker/kitematic/releases

2) 실행하면 다음과 같은 화면을 볼 수 있다.
 - 회원 가입하였던 ID로 로그인 한다.
 - 다음과 같은 화면이 나온다면 이제 도커를 사용할 기본적인 준비는 완료 되었다.


# Ubuntu 명령어
<code><pre>
sudo -i
sudo apt-get update
sudo apt install docker.io   //----------->   docker 설치
docker  //------------------> docker 도움말
docker search tomcat
docker run -d -p 8080:8080 --name tc console/tomcat-7.0   // -d:background
브라우저 실행 후 127.0.0.1:8080
</code></pre>

# Docker 컨테이너 찾기
<code><pre>
https://hub.docker.com/
</code></pre>

# Docker에서 원하는 이미지 다운로드하기
<code><pre>
docker pull <다운로드 받고자 하는 이미지> ex) mysql
docker images // ------------>  다운로드 받은 이미지 목록 확인
</code></pre>


# 도커 이미지 다운로드와 삭제
<code><pre>
sudo docker pull consol/tomcat-7.0
sudo docker rmi consol/tomcat-7.0
</pre></code>

# 도커 컨테이너 생성
<code><pre>
sudo docker run -d -name tc tomcat # 톰캣 생성 및 실행
</pre></code>

# 실행중인 컨테이너 확인
<code><pre>
sudo docker ps   # 톰캣 컨테이너 확인
</pre></code>

# 모든 컨테이너 확인
<code><pre>
sudo docker ps -a  # 모든 컨테이너 확인
</pre></code>

# 컨테이너 중지
<code><pre>
sudo docker stop <container id> f6e513b399a6   # 컨테이너 실행 중지
</pre></code>

# 컨테이너 삭제
<code><pre>
sudo docker rm <container id> f6e513b399a6   # 컨테이너 삭제
</pre></code>


# docker 예제
<code><pre>
docker pull nginx   // registry -> image
docker create -p 80:80 --name nx nginx   // image -> container
docker ps -a   //  모든 컨테이너 확인
docker start 25ff4529ee4c<CONTAINER ID>  or nx<NAME>   // memory에 nx 실행
확인은 127.0.01 실행해서 ....
docker run -d -p 83:80 --name nx2 nginx
docker rm <continer id>  // continer에서 삭제
docker stop nx  //  memory에서 nx을 stop
docker restart nx  // memory에서 nx을 재시작
docker images   //  모든 이미지 확인
docker rmi nginx   //  nginx 이미지 삭제
</pre></code>

# 도커 이미지 정보 확인
<code><pre>
sudo docker pull nginx
sudo docker inspect nginx
</pre></code>

# 도커 이미지 저장소 위치 확인
<code><pre>
sudo docker info
sudo -i
cd /var/lib/docker/overlay2
</pre></code>

# 레이어 저장소 확인
<code><pre>
</pre></code>

# 도커 히스토리 확인
<code><pre>
docker history nginx
</pre></code>

# 이미지의 사이즈 정보 확인
<code><pre>
du -sh image
</pre></code>

#  저장소 사이즈 정보 확인
<code><pre>
du -sh overlay2
</pre></code>

# 포트포워딩으로 톰캣 실행하기
<code><pre>
sudo docker run -d --name tc -p 80:8080 tomcat
firefox 127.0.0.1:80
</pre></code>

# 컨테이너 내부 셀 실행
<code><pre>
sudo docker exec -it tc /bin/bash
</pre></code>

# 컨테이너 로그 확인
<code><pre>
sudo docker logs tc   # stdout, stderr
</pre></code>

# 호스트 및 컨테이너 간 파일 복사
<code><pre>
sudo docker cp <path> <to container>:<path>
sudo docker cp <from container>:<path> <path>
sudo docker cp <from container>:<path> <to container>:<path>

ex) 
ls
echo test1234 > test.txt
cat test.txt
docker cp test.txt tc:/
docker exec -it tc cat /test.txt
docker cp tc:/test.txt ./test2.txt
cat test2.txt
</pre></code>

# 임시 컨테이너 생성
<code><pre>
sudo docker run -d -p 80:8080 --rm --name tc tomcat
</pre></code>

