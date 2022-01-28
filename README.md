# pacemaker

https://honglab.tistory.com/category/%EA%B3%B5%EB%B6%80/HA   
https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=kmk1030&logNo=221342318743


## PCS Command
https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/high_availability_add-on_reference/ch-pcscommand-haar

## 가이드 문서
https://clusterlabs.org/pacemaker/doc/deprecated/en-US/Pacemaker/2.0/html-single/Pacemaker_Administration/index.html#idm45698861372880


## qdevice 설정
qdevice는 sbd와 전혀 상관이 없다    
crmd 중에 master가 존재하는데, 그것을 DC(degignated Controller)하고, 장애 시 새로운 master를 선출할때 쿼럼 투표를 하기 위한것니다. 
cluster는 하나의 qdevice만 사용해야한다. 반대로 하나의 qdevice로 여러 cluster에 사용 할 수 있다. 

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/high_availability_add-on_reference/s1-quorumdev-haar   
You cannot use more than 
one quorum device in a cluster at the same time.
* 쿼럼 서버에서 상태 확인   
> pcs qdevice status net --full   


* cluster node에서 바라보고 있는 쿼럼서버 확인   
>pcs quorum config   
>pcs quorum status
