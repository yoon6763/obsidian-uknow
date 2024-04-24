#docker
#container
#ci/cd
#dev-ops

# 명령어 모음

Docker version 확인
`docker version`


Docker 실행 환경 확인
`docker system info`


Docker 디스크 이용 상황
`docker system df`



### 이미지

Docker 이미지 다운로드
`docker image pull {imageName} 이미지명{:태그명}`
`ex> docker pull centos:7`
- 태그 생략 시 최신판(lastest)


이미지 목록
`docker image ls [옵션] [레포지토리명]`
레포지토리명 생략 가능


이미지 상세 정보 확인
`docker image inspect
`docker image inspect centos:7`


이미지 검색
`docker search [옵션] <검색 키워드>`
`docker search nginx`


이미지 삭제
`docker image rm [옵션] 이미지명 [이미지명]`
`docker image rm nginx`




## 컨테이너

서버 기동
ex> Nginx
`docker container run --name webserver -d -p 80:80 nginx`
-- 브라우저를 키고 localhost:80을 치면 nginx 화면이 반겨준다.


컨테이너 확인
`docker container ps


컨테이너 정지
`docker container stop webserver`


컨테이너 기동
`docker container start webserver`


컨테이너 삭제
`docker container rm webserver`


컨테이너 일시 정지
`docker container pause`


컨테이너 재개
`docker container unpause`


컨테이너 재시작
`docker container restart`


컨테이너 생성 및 시작
`docker container run [옵션] 이미지명[:태그명][인수]`
`docker container run -it --name "test1" centos /bin/cal`


컨테이너 백그라운드 실행
`docker container run -d centos /bin/ping localhost`
-d, -detach : 백그라운드에서 실행 옵션


컨테이너 네트워크 설정
`docker container run [네트워크 옵션] 이미지명[:태그명] [인수]`
`docker container run -d -p 8080:80 nginx`
호스트의 포트번호 8080과 컨테이너 포트 80번 매핑


자원을 지정하여 컨테이너 생성 및 실행
`docker container run --cpu-shares=512 --memory=lg centos`


컨테이너 리스트
`docker container ls`


컨테이너 가동 확인
`docker container stats [컨테이너 식별자]`


