# service는 여러개의 pod를 하나의 ip로 단일 진입접을 생성한다.
## service의 종류
### ClusterIP
pod 그룹의 단일 진입점 생성 <br>
selector의 label을 동일한 pod들의 그룹으로 묶어서 단일 진입점 생성한다. <br>
클러스터 내부에서만 사용가능, type 생략시 1.96.x.x 범위에서 랜덤으로 할당
### NodePort
clusterIP 포함하고 있다. 모든 워커노드에서 접속가능한 포트를 노출시킨다. <br>
모든 노드를 대상으로 외부 접속 가능한 포트를 예약한다. <br>
default nodeport의 범위: 30000~32767 <br>
clusterIP 를 생성 후 NodePort를 예약한다.
### LoadBalancer
워커노드에 적절하게 분배가능한 로드밸런서 <br>
클라우드 서버에서 제공을 해준다.
### ExternalName
pod의 도메인을 설정해준다.
### Headliss Service
ClusterIP가 없는 서비스로 단일 진입점이 필요 없을 때 사용