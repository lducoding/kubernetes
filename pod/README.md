# pod는 k8s의 최소 실행 단위이다.
기본적인 kubectl run 명령어로 pod 생성이 가능하다. <br>
pod 안에는 1개 이상의 container가 존재한다. <br>
## 멀티 container 내부 접속방법
kubectl exec multipod(pod이름) -c container1(컨테이너 이름) -it — /bin/bash
## yaml 파일로 pod를 실행
yaml파일을 실행하는 방법으로도 pod 생성이 가능하다. <br>
--dry-run 명령어를 통해 yaml 형식으로 확인이 가능하며 파일로 변환하는 것도 가능하다. <br>
kubectl run webserver --image=nginx:1.14 --port 80 --dry-run -o yaml > webserver-pod.yaml
## initContainer
initContainer 설정을 하면 initContainer가 실행되어야 Container가 실행된다.
## pod를 외부로 포트포워딩
kubectl port-forward webserver 8778:80
## pod 실행패턴
sidecar 패턴 : 로그를 찍는 역할의 컨테니어가 실행이 되는 다른 컨테이너를 하나의 pod에서 올린다. <br>
기반이 되는 컨트롤러가 있어야 실행하는 initController와 비슷하다. <br>
adapter 패턴 : 웹서버 컨테이너에 adapter가 외부의 데이터를 가지고 와서 웹서버에 전달한다. <br>
프론트 컨테이너에 백엔드 컨테이너가(adapter역할) 외부 DB에 있는 정보를 가져와서 프론트에 전달하는 것 <br>
ambassador 패턴 : 웹서버에서 만들어진 데이터를 외부로 뿌리는 adapter와 방향이 반대이다.