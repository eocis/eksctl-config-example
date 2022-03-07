# 배포시 특이사항

<br>

> Node Group
- eksctl config(yaml) file로 create시 CloudFormation Stack이 생성되고 리소스가 배포됩니다.  
- eksctl config file로 create시 nodegroup은 cluster의 version을 follow합니다.  
- eksctl config file로 delete시 생성된 CloudFormation Stack 및 시작 템플릿도 함께 삭제가 됩니다.  
- eksctl config file로 cluster version upgrade시 cloudformation stack에는 반영하지 않습니다.

<br>

> etc
- CloudFormation Stack 별로 생성 되기 때문에 IAM > SG ... 순으로 생성되지 않고, 각 Product 별로 생성됩니다.  
예를 들어 cluster service role은 nodegroup worker role과 함께 생성되지 않습니다.  
- eksctl 0.1.31 버전 기준 vpc nat 옵션을 넣어도 기존 사용중인 vpc에 클러스터 생성시 nat가 자동으로 생성되지 않습니다.  
- Cluster Upgrade 시 Cluster는 config파일을 지정하여 업그레이드가 가능하나 Nodegroup은 cli command를 수동으로 입력해야 합니다.