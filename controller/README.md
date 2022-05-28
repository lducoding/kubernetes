# controller는 k8s에서 pod를 실행한다.
## controller의 종류
### ReplicationController
controller의 기본 형식 pod의 갯수를 보장한다.
### ReplicaSet
replication controller 와 기능은 같지만 보다 풍부한 selector 사용이 가능하다.
### Deployment
replicaset을 제어해 주는 부모 역할 무중단 버전업 다운이 가능 
### DaemonSet
전체노드에서 pod가 한개씩 실행되도록 보장한다.
### StatefulSet
pod의 이름, pod의 스토리지를 유지해주는 컨트롤러
### job
k8s는 pod를 running 중인 상태로 유지한다. <br>
job 컨트롤러는 batch 처리하는 pod의 작업이 완료되면 종료된다.
### cronJob
job 제어해서 사용자가 원하는 시간에 job 실행 예약 지원