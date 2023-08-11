# learning-cloudformation

🕵️‍♀️🕵️‍♀️🕵️‍♀️ CloudFormation使ってみる！  

![成果物](./docs/img/fruit.gif)  

## 実行方法

```shell
# Ref: https://docs.aws.amazon.com/ja_jp/AWSCloudFormation/latest/UserGuide/using-cfn-cli-creating-stack.html
aws cloudformation deploy \
    --stack-name <stack-name> \
    --template <template>

# 例)
aws cloudformation deploy \
    --stack-name learning-cloudformation \
    --template ./template.yml
```

`Output`で指定した値を取得するには、以下のコマンドを実行します。  

```shell
aws cloudformation describe-stacks --stack-name <stack-name> --query <query> --output <output> --no-cli-pager

# 例) バケット名を取得
aws cloudformation describe-stacks --stack-name learning-cloudformation --query "Stacks[].Outputs[?OutputKey=='S3BucketName'].OutputValue" --output text --no-cli-pager

# 例) エンドポイントを取得
aws cloudformation describe-stacks --stack-name learning-cloudformation --query "Stacks[].Outputs[?OutputKey=='S3BucketDomainName'].OutputValue" --output text --no-cli-pager
```

```shell
aws s3 ls s3://<S3BucketName>

# 例)
aws s3 ls s3://learning-cloudformation-s3-bucket
```

削除するには、以下のコマンドを実行します。  

```shell
aws cloudformation delete-stack --stack-name <stack-name>

# 例)
aws cloudformation delete-stack --stack-name learning-cloudformation
```

## S3の操作

NodeでS3を操作する簡単なコードを用意しています。  
`yarn install`してから、以下のコマンドを実行してください。  

```shell
yarn start
```

このプログラムを実行する前に、`.env.example`を`.env`にリネームして、環境変数を設定してください。  
