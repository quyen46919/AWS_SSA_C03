## AWS CLI Configuration

Origin: https://www.youtube.com/watch?v=ZYkLQOcWf8E&list=PLBfufR7vyJJ6FhBhJJSaMkI-m2wyoPy-G&index=6

### Install AWS CLI Ubuntu

```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

### AWS Configure

1. Đăng ký account AWS  
   (có add credit card, nếu cẩn thận thì sau khi add card thì disable credit card đi cho chắc kẻo bị trừ tiền khi thao tác nhầm)

2. Đăng nhập

3. Tạo account IAM (Identity and Access Management) (free)  
   Truy cập vào https://us-east-1.console.aws.amazon.com/iam/home?region=ap-southeast-2#/users  
   Create User -> Create Group "Admin" -> Full access  
   Truy cập vào aws-examples -> Security credentials -> Access keys -> Command Line Interface -> Create access key

   Lưu ý nguyên tắc khi tạo account: **"least privilege"** - chỉ cấp quyền tối thiểu cần thiết

4. Lấy key từ IAM, nhập vào terminal

   ```code
   export AWS_ACCESS_KEY_ID=SAMPLE
   export AWS_SECRET_ACCESS_KEY=SAMPLE
   export AWS_DEFAULT_REGION=us-east-1
   ```

5. Check connection

   ```
   aws sts get-caller-identity
   ```

   Result:

   ```
   {
   "UserId": "AIDA3KOS6SVMFNT72V4TV",
   "Account": "778368357720",
   "Arn": "arn:aws:iam::778368357720:user/aws-examples"
   }
   ```

6. Bật gõ lệnh tự động (optional)

   ```
   export AWS_CLI_AUTO_PROMPT=on-partial
   ```

### IAM Overview

![introduction](../images/iam/iam.png)

### Managed vs Customer vs inline Policy

![introduction](../images/iam/iam-managed-vs-customer-vs-inline-policy.png)

### Anatomy of an IAM Policy

![introduction](../images/iam/iam-anatomy.png)
