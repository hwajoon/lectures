# https://www.youtube.com/watch?v=YSKdWt4SwDw


<code><pre>

Docker Desktop 설치해서 확인하는 것이 편함.

1. npm 설치
2. http://expressjs.com/  => 시작하기
3. npm init
4. npm install express --save  => node_modules 폴더 생성
5. .gitignore 생성 및 node_modules 문구 작성
6. app.js 파일 추가
7. package.json 수정
    "scripts": {
    "start": "node app.js"   ==> npm start 할때, 실행되는 부분 
   }, 
8. dockerfile 추가
9. https://docs.docker.com/  /  https://docs.docker.com/get-started/nodejs/build-images/ 참고해서
   dockerfile에 내용 추가
</pre></code>

<code><pre>
D:\workspace\lecture\Docker\myapp>docker images ls
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
</pre></code>

<code><pre>
D:\workspace\lecture\Docker\myapp>docker build -t helloworld-node-test:0.0.1 .
[+] Building 33.0s (11/11) FINISHED
 => [internal] load build definition from Dockerfile                                                                                                            0.0s 
 => => transferring dockerfile: 352B                                                                                                                            0.0s 
 => [internal] load .dockerignore                                                                                                                               0.0s 
 => => transferring context: 2B                                                                                                                                 0.0s 
 => [internal] load metadata for docker.io/library/node:current-slim                                                                                            4.6s 
 => [auth] library/node:pull token for registry-1.docker.io                                                                                                     0.0s 
 => [1/5] FROM docker.io/library/node:current-slim@sha256:6ee0ac3ce36b5f018f63e55d55d7fb8ed62c6c11bc86fab6d433f3d40229f7b9                                     25.8s 
 => => resolve docker.io/library/node:current-slim@sha256:6ee0ac3ce36b5f018f63e55d55d7fb8ed62c6c11bc86fab6d433f3d40229f7b9                                      0.0s 
 => => sha256:6ee0ac3ce36b5f018f63e55d55d7fb8ed62c6c11bc86fab6d433f3d40229f7b9 776B / 776B                                                                      0.0s 
 => => sha256:16e827c805749ab5cb0cdb95c89d3390c1c33939552d0154d58afb05356bffe2 1.37kB / 1.37kB                                                                  0.0s 
 => => sha256:12c677931cc505da7e8401af8901886751e162306ee59936f86701b46f0e504a 7.09kB / 7.09kB                                                                  0.0s 
 => => sha256:e50c3c9ef5a201a24959788dcbc7ebf88d95c63e132a4d7396ce541127afd88e 22.53MB / 22.53MB                                                                8.5s 
 => => sha256:7d035f3b60685c603de659845d2b4006f2703337b95ef0c08ddf5c730c8a0db1 4.15kB / 4.15kB                                                                  1.5s 
 => => sha256:c136022735c1b292668cfd2df48ada79c81b97e2b0d3b5b3cf416b46702bba24 34.17MB / 34.17MB                                                               24.7s 
 => => sha256:45b6835ccf07f0d0efa362d2420fc2a53d723e765a7415d84a17e1a2d0ca4238 2.82MB / 2.82MB                                                                  5.4s 
 => => sha256:cec7c120776eb5d1a2d4dbf4d73ffcedf6b9b8a8001c55789ca60393befef158 295B / 295B                                                                      6.0s 
 => => extracting sha256:e50c3c9ef5a201a24959788dcbc7ebf88d95c63e132a4d7396ce541127afd88e                                                                       0.6s 
 => => extracting sha256:7d035f3b60685c603de659845d2b4006f2703337b95ef0c08ddf5c730c8a0db1                                                                       0.0s 
 => => extracting sha256:c136022735c1b292668cfd2df48ada79c81b97e2b0d3b5b3cf416b46702bba24                                                                       0.8s 
 => => extracting sha256:45b6835ccf07f0d0efa362d2420fc2a53d723e765a7415d84a17e1a2d0ca4238                                                                       0.1s 
 => => extracting sha256:cec7c120776eb5d1a2d4dbf4d73ffcedf6b9b8a8001c55789ca60393befef158                                                                       0.0s 
 => [internal] load build context                                                                                                                               0.3s 
 => => transferring context: 1.74MB                                                                                                                             0.3s 
 => [2/5] WORKDIR /app                                                                                                                                          0.1s 
 => [3/5] COPY package.json .                                                                                                                                   0.0s 
 => [4/5] RUN npm install                                                                                                                                       2.1s 
 => [5/5] COPY . .                                                                                                                                              0.1s 
 => exporting to image                                                                                                                                          0.2s 
 => => exporting layers                                                                                                                                         0.2s 
 => => writing image sha256:bdce3b9bd8964c2e3848bf4552b24bcf6ac41ad2e30382b8db7e9367ebfb1f49                                                                    0.0s 
 => => naming to docker.io/library/helloworld-node-test:0.0.1                                                                                                   0.0s 

D:\workspace\lecture\Docker\myapp>
</pre></code>


<code><pre>
D:\workspace\lecture\Docker\myapp>docker image ls
REPOSITORY             TAG       IMAGE ID       CREATED              SIZE
helloworld-node-test   0.0.1     bdce3b9bd896   About a minute ago   166MB
alpine/git             latest    ed0ba0fc6585   9 days ago           28.4MB

D:\workspace\lecture\Docker\myapp>
</pre></code>

<code><pre>
D:\workspace\lecture\Docker\myapp>docker run -d -p 80:3000 --name hnt helloworld-node-test:0.0.1
b2940b7b9cb2fbc34db1a87c5b52cde05cab803810c09ad13751e9696b4ba8db

D:\workspace\lecture\Docker\myapp>docker ps -a
CONTAINER ID   IMAGE                        COMMAND                  CREATED          STATUS                      PORTS                  NAMES
b2940b7b9cb2   helloworld-node-test:0.0.1   "docker-entrypoint.s…"   11 seconds ago   Up 10 seconds               0.0.0.0:80->3000/tcp   hnt
3e1298556b30   alpine/git                   "git clone https://g…"   29 hours ago     Exited (128) 29 hours ago                          repo

D:\workspace\lecture\Docker\myapp>

====> http://localhost:80 으로 접속해서 확인

Docker Desktop / LOCAL에서 이미지에 추가된 것을 확인할 수 있음

</pre></code>
