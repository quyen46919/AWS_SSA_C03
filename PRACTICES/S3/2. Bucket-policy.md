## Thực hành phân quyền Bucket thông qua API

### Tạo bucket

```
aws s3 mb s3://bucket-policy-example-quyennc
```

### Chỉnh sửa policy

Chỉnh sửa quyền cho những account khác khi truy cập vào bucket của mình theo policy.json

```
aws s3api put-bucket-policy --bucket bucket-policy-example-quyennc --policy file://policy.json
```

### Dùng một account khác (đã được cấp quyền) truy cập vào bucket

```
touch sample.txt
aws s3 cp sample.txt s3://bucket-policy-example-quyennc
aws s3 ls s3://bucket-policy-example-quyennc
```

### Clean up

```
aws s3 rb s3://bucket-policy-example-quyennc/sample.txt
aws s3 rb s3://bucket-policy-example-quyennc
```
