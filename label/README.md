# label 적용범위
pod, deploy, service 뿐만 아니라 worker node에도 적용가능
# label 정보보기
kubectl get pod --show-labels
# label로 찾기
kubectl get pod -l name=mainui
# label 삭제
kubectl label pod cmdpod run(label이름)-
# label을 가졌는지 확인
kubectl get nodes -L disk
# label 추가
kubectl label nodes node01 disk=ssd