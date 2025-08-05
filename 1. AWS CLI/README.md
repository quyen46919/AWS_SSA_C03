### Install AWS CLI

```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

### AWS Configure

Đăng ký account AWS (có add credit card)
Đăng nhập
Truy cập vào https://us-east-1.console.aws.amazon.com/iam/home?region=ap-southeast-2#/users
Create User -> Create Group "Admin" -> Full access
Truy cập vào aws-examples -> Security credentials -> Access keys -> Command Line Interface -> Create access key

Nhập vào terminal

```code
export AWS_ACCESS_KEY_ID=SAMPLE
export AWS_SECRET_ACCESS_KEY=SAMPLE
export AWS_DEFAULT_REGION=us-east-1
```

Check connection

```
aws sts get-caller-identity

Result:
{
    "UserId": "AIDA3KOS6SVMFNT72V4TV",
    "Account": "778368357720",
    "Arn": "arn:aws:iam::778368357720:user/aws-examples"
}
```

Bật gõ lệnh tự động

```
export AWS_CLI_AUTO_PROMPT=on-partial
```
