# pod는 k8s의 최소 실행 단위이다.
기본적인 kubectl run 명령어로 pod 생성이 가능하다. <br>
pod 안에는 1개 이상의 container가 존재한다. <br>
## 멀티 container 내부 접속방법
kubectl exec multipod(pod이름) -c container1(컨테이너 이름) -it — /bin/bash
## yaml 파일로 pod를 실행
yaml파일을 실행하는 방법으로도 pod 생성이 가능하다. <br>
--dry-run 명령어를 통해 yaml 형식으로 확인이 가능하며 파일로 변환하는 것도 가능하다. <br>
kubectl run webserver --image=nginx:1.14 --port 80 --dry-run -o yaml > webserver-pod.yaml
## pod를 외부로 포트포워딩
kubectl port-forward webserver 8778:80
