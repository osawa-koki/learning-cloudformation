# learning-cloudformation

🕵️‍♀️🕵️‍♀️🕵️‍♀️ CloudFormation使ってみる！  

## 実行方法

```shell
# Ref: https://docs.aws.amazon.com/ja_jp/AWSCloudFormation/latest/UserGuide/using-cfn-cli-creating-stack.html
aws cloudformation create-stack \
    --stack-name <stack-name> \
    --template-body <template-body> \
    --parameters <parameters>

# 例)
aws cloudformation create-stack \
    --stack-name learning-cloudformation \
    --template-body file://./template.yml
```
