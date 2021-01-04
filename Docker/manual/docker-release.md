# https://www.youtube.com/watch?v=ZkfBQh7ZVfo

<code><pre>

1. https://hub.docker.com/ 접속 / 회원 가입

Docker Desktop 설치해서 확인하는 것이 편함.

D:\workspace\lecture\Docker>docker login
Authenticating with existing credentials...
Login Succeeded
</pre></code>

<code><pre>
// D:\workspace\lecture\Docker>docker tag <image name>:tag <docker id /nickname>/<image name>:tag

D:\workspace\lecture\Docker>docker image ls
REPOSITORY             TAG       IMAGE ID       CREATED          SIZE
helloworld-node-test   0.0.1     bdce3b9bd896   17 minutes ago   166MB
alpine/git             latest    ed0ba0fc6585   9 days ago       28.4MB

D:\workspace\lecture\Docker>docker tag helloworld-node-test:0.0.1 hwajunlee/helloworld-node-test:0.0.1

D:\workspace\lecture\Docker>docker image ls
REPOSITORY                       TAG       IMAGE ID       CREATED          SIZE
hwajunlee/helloworld-node-test   0.0.1     bdce3b9bd896   19 minutes ago   166MB
helloworld-node-test             0.0.1     bdce3b9bd896   19 minutes ago   166MB
alpine/git                       latest    ed0ba0fc6585   9 days ago       28.4MB

D:\workspace\lecture\Docker>
</pre></code>


<code><pre>
D:\workspace\lecture\Docker>docker push hwajunlee/helloworld-node-test:0.0.1
The push refers to repository [docker.io/hwajunlee/helloworld-node-test]
c37f9911889e: Pushing [==================================================>]  2.012MB
52ac4054342f: Pushing [==================================================>]  5.297MB
1969e1d80cae: Pushing [==================================================>]   2.56kB
b5dcfc5a7109: Pushing  2.048kB
dd0b4fe6240f: Mounted from library/node
3d4bb39cd8ec: Waiting
eadc60a5beb9: Waiting
79c320b5a45c: Waiting
e4b1e8d0745b: Waiting


Docker Desktop / REMOTE REPOSITORY에서 이미지가  push된 것을 확인할 수 있음

</pre></code>