# cfn-windows-userdata-sample

CloudFormationでWindows Serverを構築して、UserDataを使ってスクリプトを実行するサンプル。  
Ansibleを実行可能にするため、WinRMを有効化します。  
Ansible Playbookは別リポジトリとなる予定。

## Environment setup

```sh
aws cloudformation create-change-set \
    --template-body file://templates/stack-vpc.yml \
    --cli-input-json file://parameters/sample01/stack-vpc.json \
    --change-set-type CREATE

aws cloudformation create-change-set \
    --template-body file://templates/stack-security-group.yml \
    --cli-input-json file://parameters/sample01/stack-security-group.json \
    --change-set-type CREATE

aws cloudformation create-change-set \
    --template-body file://templates/stack-ec2.yml \
    --cli-input-json file://parameters/sample01/stack-ec2.json \
    --change-set-type CREATE
```
