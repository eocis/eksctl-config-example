# 배포시 특이사항

<br>

> Node Group
- eksctl config(yaml) file로 create시 CloudFormation Stack이 생성되고 리소스가 배포됩니다.  
- eksctl config file로 create시 nodegroup은 cluster의 version을 follow합니다.  
- eksctl config file로 delete시 생성된 CloudFormation Stack 및 시작 템플릿도 함께 삭제가 됩니다.  
- eksctl config file로 cluster version upgrade시 cloudformation stack에는 반영하지 않습니다.  