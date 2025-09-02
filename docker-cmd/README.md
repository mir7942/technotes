# Docker 명령어 모음
Docker에서 자주 사용하는 명령어를 설명한다.

# Image 실행
아래 옵션들을 조합할 수 있다.
- Image를 실행하고 그 Image에서 Command를 실행
```powershell
docker run <Image> [Command]
```
- Image를 interactive 모드로 실행
```powershell
docker run -it <Image>
```
- Image를 실행하고 종료될 때 Container를 삭제
```powershell
docker run -rm <Image>
```
- Image를 백그라운드 모드로 실행
```powershell
docker run -d <Image>
```

## Container 목록 확인
- 현재 실행 중인 Container 목록을 출력
```powershell
docker ps
또는
docker container ls
```
- 종료된 Container까지 확인하기 위해서는 -a 옵션을 사용
```powershell
docker ps -a
```

## 실행 중인 Container 종료
- 실행 중인 Container 종료. 이때, Container는 ID 또는 이름으로 지정한다.
```powershell
docker stop <Container>
또는
docker container kill <Container>
```
- 실행 중인 Container 강제 종료
```powershell
docker kill <Container>
```

## Container 삭제
종료된 Container 삭제
```powershell
docker rm <Container>
또는
docker container rm <Container>
```
실행 중인 Container 삭제
```powershell
docker rm -f <Container>
또는
docker container rm -f <Container>
```
중지된 모든 Container 삭제
```powershell
docker container prune
```

## Image 목록 확인
- Image 목록 출력
```powershell
docker images
또는
docker image ls
```

## Image 가져오기
- Docker Hub에서 최신 이미지 가져오기
```powershell
docker pull <Image>
또는
docker pull <Image>:latest
```
- Docker Hub에서 특정 버전 또는 Tag의 이미지 가져오기
```powershell
docker pull <Image>:<Tag>
```

## Image 삭제
Image를 삭제하기 전에 관련된 모든 Container를 종료해야 한다.
- Image 삭제
```powershell
docker rmi <Image>
또는
docker image rm <Image>
```