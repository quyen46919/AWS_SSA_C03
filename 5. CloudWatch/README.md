## Cloudwatch

### Pillars of observability (Ba trụ cột của khả năng quan sát)

![Image](../images/cloudwatch/cloudwatch-pillars-of-observability.png)

**Observability là gì?**ffều ứng dụng/dịch vụ, giúp xác định vị trí sự cố hoặc vấn đề hiệu năng.

📌 **Alarm (Cảnh báo)** đôi khi được xem là trụ cột thứ tư của khả năng quan sát.

### Introduction to Cloudwatch

![Image](../images/cloudwatch/cloudwatch-introduction-1.png)

AWS CloudWatch là giải pháp giám sát (monitoring solution) cho các tài nguyên AWS của bạn.

CloudWatch là một dịch vụ “ô dù” (umbrella service), nghĩa là nó thực chất là tập hợp của nhiều công cụ giám sát, bao gồm:

- Logs — mọi loại dữ liệu log tùy chỉnh, log ứng dụng, log Nginx, log Lambda.
- Metrics — tập hợp dữ liệu được sắp xếp theo thời gian; một biến cần theo dõi (ví dụ: mức sử dụng bộ nhớ).
- Events — kích hoạt sự kiện dựa trên điều kiện (ví dụ: snapshot máy chủ mỗi giờ — hiện được gọi là Amazon EventBridge).
- Alarms — gửi thông báo khi các chỉ số (metrics) vượt ngưỡng đã định.
- Dashboards — tạo biểu đồ trực quan dựa trên các chỉ số.
- ServiceLens — trực quan hóa và phân tích tình trạng, hiệu năng, và khả năng sẵn sàng của ứng dụng trong một nơi duy nhất.
- Container Insights — thu thập, tổng hợp và tóm tắt các chỉ số và log từ ứng dụng container và microservice.
- Synthetics — kiểm tra ứng dụng web để xem có bị lỗi không.
- Contributor Insights — xem các yếu tố hàng đầu ảnh hưởng đến hiệu suất của hệ thống và ứng dụng trong thời gian thực.

### Cloudwatch Logs

![Image](../images/cloudwatch/cloudwatch-introduction-2.png)

CloudWatch Logs là nền tảng cho hầu hết các dịch vụ CloudWatch khác.  
Tức là: dữ liệu log được thu thập trước → chuyển thành metric → từ đó các dịch vụ khác như dashboard, alarm, events... có thể hoạt động. Toàn bộ hệ thống CloudWatch đều xoay quanh Logs.

![Image](../images/cloudwatch/cloudwatch-logs.png)

CloudWatch Logs được sử dụng để giám sát (monitor), lưu trữ (store) và truy cập (access) các tệp log của bạn.
CloudWatch là một dịch vụ quản lý log tập trung (centralized log management service).

**Export Logs to S3**  
Bạn có thể xuất log sang S3 để thực hiện các tác vụ như phân tích tùy chỉnh.

**Stream to Elasticsearch Service (ES)**  
Bạn có thể truyền log đến một cụm ES gần như theo thời gian thực để có khả năng tìm kiếm toàn văn mạnh mẽ hơn hoặc sử dụng với ELK stack.

**Stream CloudTrail Events to CloudWatch Logs**  
Bạn có thể bật CloudTrail để truyền dữ liệu sự kiện đến một Log Group của CloudWatch.

_AWS CloudTrail là dịch vụ ghi lại toàn bộ hoạt động (event logs) xảy ra trong tài khoản AWS của bạn (bạn đã làm gì, ở đâu và khi nào?)_

**Log Security**  
Theo mặc định, các Log Group được mã hóa khi lưu trữ bằng SSE (Server-Side Encryption). Bạn có thể sử dụng Customer Master Key (CMK) riêng của mình với AWS KMS.

**Log Filtering**  
Log có thể được lọc bằng cú pháp lọc (Filtering Syntax), và CloudWatch Logs có dịch vụ con là CloudWatch Insights.

_CloudWatch Logs Insights là công cụ truy vấn (query tool - tương tự SQL) mạnh mẽ trong AWS CloudWatch, được dùng để tìm kiếm, phân tích và trực quan hóa dữ liệu log một cách nhanh chóng._

**Log Retention**  
Theo mặc định, log được giữ vô thời hạn và không bao giờ hết hạn. Bạn có thể điều chỉnh chính sách lưu trữ cho từng Log Group :

- Giữ vô thời hạn
- Chọn thời gian lưu trữ từ 1 ngày đến 10 năm

### Cloudwatch Log Group

![Image](../images/cloudwatch/cloudwatch-log-group.png)

Một tập hợp các luồng nhật ký (log streams). Thông thường, các nhóm nhật ký được đặt tên bằng cú pháp dấu gạch chéo:

Ví dụ:

```
/exampro/prod/app
/exampro/prod/db
/exampro/dev/app
/exampro/dev/db
```

Bạn có thể đặt thời gian lưu trữ cho một Log Group trong khoảng từ _Không bao giờ hết hạn (Never expire)_ đến _120 tháng (10 năm)_.

### Cloudwatch Log Stream

![Image](../images/cloudwatch/cloudwatch-log-stream.png)

Một log stream đại diện cho một chuỗi các sự kiện (sequence of events) từ một ứng dụng hoặc instance đang được giám sát.

Bạn có thể tạo Log Stream thủ công, nhưng thông thường dịch vụ bạn đang sử dụng sẽ tự động tạo ra.

Ví dụ:

**Log Group cho hàm Lambda**  
Các Log Streams được đặt tên theo instance đang chạy.
Do Lambda thường chạy trên các instance mới, nên tên log stream sẽ chứa dấu thời gian (timestamp).

**Log Group cho ứng dụng chạy trên EC2**  
Các Log Streams được đặt tên theo ID của instance đang chạy (Instance ID).

**Log Group cho AWS Glue**  
Các Log Streams được đặt tên theo Glue Jobs.

### Cloudwatch Log Events

![Image](../images/cloudwatch/cloudwatch-log-events.png)

Log Events là đại diện cho một sự kiện riêng lẻ trong một tệp log. Các sự kiện log có thể được nhìn thấy trong một Log Stream.

Bạn có thể sử dụng bộ lọc sự kiện để lọc ra các log dựa trên cú pháp đối sánh Đơn giản hoặc đối sánh Mẫu (Pattern matching syntax)

### Cloudwatch Log Insights

![Image](../images/cloudwatch/cloudwatch-logs-insights.png)

CloudWatch Logs Insights cho phép bạn tìm kiếm và phân tích dữ liệu log CloudWatch của mình một cách tương tác và có các ưu điểm sau:

- Lọc mạnh mẽ hơn so với việc sử dụng tính năng Sự kiện Lọc đơn giản trong Luồng Log (Log Stream).
- Ít gánh nặng hơn so với việc phải xuất log ra S3 và phân tích chúng qua Athena.

CloudWatch Logs Insights hỗ trợ tất cả các loại log.

CloudWatch Logs Insights thường được sử dụng qua console để thực hiện truy vấn ad-hoc (truy vấn tức thời) đối với các nhóm log (log groups).

CloudWatch Insights có ngôn ngữ riêng gọi là: Cú pháp Truy vấn CloudWatch Logs Insights

```
filter action="REJECT"
| stats count(*) as numRejections by srcAddr
| sort numRejections desc
| limit 20
```

Đặc điểm:

- Một yêu cầu truy vấn có thể truy vấn tối đa 20 nhóm log.
- Các truy vấn sẽ hết thời gian sau 15 phút, nếu chúng chưa hoàn thành.
- Kết quả truy vấn được lưu trong 7 ngày.

![Image](../images/cloudwatch/cloudwatch-logs-insights-example.png)

AWS cung cấp các truy vấn mẫu có thể giúp bạn bắt đầu với các tác vụ phổ biến, và giúp việc học Query Syntax dễ dàng hơn.

Bạn có thể tạo và lưu các truy vấn của riêng mình để giúp các công việc lặp đi lặp lại trong tương lai dễ dàng hơn.

### Cloudwatch Insights - Discovered Fields

![Image](../images/cloudwatch/cloudwatch-insights-discovered-fields-1.png)

Khi CloudWatch Insights đọc log, nó sẽ phân tích các sự kiện log và cố gắng cấu trúc nội dung bằng cách tạo ra các trường (fields) mà sau đó bạn có thể sử dụng trong truy vấn của mình.

CloudWatch Logs Insights chèn ký hiệu @ vào đầu các trường mà nó tạo ra.

Năm trường hệ thống (Five system fields) sẽ được tự động tạo:

- **@message** — sự kiện log thô, chưa được phân tích cú pháp.
- **@timestamp** — dấu thời gian sự kiện có trong trường dấu thời gian của sự kiện log.
- **@ingestionTime** — thời gian mà sự kiện log được nhận bởi CloudWatch Logs.
- **@logStream** — tên của luồng log mà sự kiện log được thêm vào.
- **@log** — là một định danh nhóm log (log group identifier) dưới dạng `account-id:log-group-name`.

![Image](../images/cloudwatch/cloudwatch-insights-discovered-fields-2.png)

Logs Insights tự động khám phá các trường cho log từ các dịch vụ AWS phổ biến:

Amazon VPC Flow Logs  
`@timestamp, accountId, action, bytes, dstAddr, srcPort, v.v.`

Amazon Route 53  
`@timestamp, edgeLocation, queryName, responseCode, v.v.`

AWS Lambda  
`@requestId, @duration, @billedDuration, @maxMemoryUsed, @xrayTraceId, v.v.`

AWS CloudTrail  
`eventVersion, eventTime, eventName, sourceIPAddress, userAgent, v.v. `

JSON Logs  
`Các cặp key-value trong log JSON sẽ được chuyển thành các trường (fields).`

Xử lý Các Loại Log Khác  
Đối với các trường mà Logs Insights không tự động khám phá. Bạn có thể sử dụng lệnh `parse` để trích xuất và tạo các trường tạm thời (ephemeral fields) để sử dụng trong truy vấn đó.

![Image](../images/cloudwatch/cloudwatch-insights-discovered-fields-3.png)

Thay vì gõ thì bạn có thể chọn field được liệt kê sẵn.

### Cloudwatch Metrics

![Image](../images/cloudwatch/cloudwatch-metrics.png)

Một CloudWatch Metric đại diện cho một tập hợp các điểm dữ liệu được sắp xếp theo thời gian (time-ordered set of data points). Đó là một biến được theo dõi theo thời gian.

CloudWatch đi kèm với nhiều chỉ số được xác định trước mà thường được phân loại theo tên miền (Namespace) của Dịch vụ AWS.

### Cloudwatch - Custom Metrics and High Resolutions

![Image](../images/cloudwatch/cloudwatch-custom-metrics-and-high-resolution.png)

Bạn có thể tùy chỉnh metrics (publish Custom Metrics) của riêng mình bằng cách sử dụng AWS CLI hoặc SDK.

```
aws cloudwatch put-metric-data \
--metric-name Enterprise-D \
--namespace Starfleet \
--unit Bytes \
--value 231213412 \
--dimensions HullIntegrity=100,Shield=70,Thrusters=maximum
```

**Resolution**: Tần suất thu nhập hoặc gửi dữ liệu (thông qua API,...)

Khi bạn tùy chỉnh metrics, bạn có thể xác định Resolution là một trong hai:

- Standard resolution (1 phút)
- High resolution (> 1 phút đến 1 giây)

Với High Resolution, bạn có thể theo dõi trong các khoảng thời gian:

- 1 giây
- 5 giây
- 10 giây
- 30 giây
- bội số của 60 giây.

### Cloudwatch Availability of Data

![Image](../images/cloudwatch/cloudwatch-availability-of-data.png)

Khi một Dịch vụ AWS gửi dữ liệu đến CloudWatch, tần suất thu thập dữ liệu (Availability of data) sẽ khác nhau tùy thuộc vào Dịch vụ AWS đó:

|                       | Elastic Compute Cloud (EC2) | Các Dịch vụ Khác (Other Services) |
| :-------------------- | :-------------------------- | :-------------------------------- |
| **Giám sát Cơ bản**   | Khoảng thời gian 5 phút     | 1 phút / 3 phút / 5 phút          |
| **Giám sát Chi tiết** | Khoảng thời gian 1 phút     | Không áp dụng (N/A)               |

_Ghi chú: Phần lớn các dịch vụ AWS có khả năng sẵn có của dữ liệu là 1 phút._

### Cloudwatch Log Collection - Agent and Host level metrics

![Image](../images/cloudwatch/cloudwatch-agent-and-host-level-metrics.png)

Một số chỉ số mà bạn có thể nghĩ rằng đã được theo dõi mặc định cho các phiên bản EC2 lại không phải, và đòi hỏi phải cài đặt CloudWatch Agent.

**Các Chỉ số Mức Máy chủ (Host Level Metrics)**

Đây là những chỉ số bạn nhận được mà không cần cài đặt Agent:

- CPU Usage (Mức sử dụng CPU)
- Network Usage (Mức sử dụng mạng)
- Disk Usage (Mức sử dụng Đĩa)
- Status Checks (Kiểm tra trạng thái)
  - Trạng thái của Hypervisor đang chạy bên dưới máy ảo.
  - Trạng thái phiên bản EC2 đang chạy bên dưới máy ảo.

**Các Chỉ số Mức Agent (Agent Level Metrics)**

Đây là những chỉ số bạn nhận được khi cài đặt Agent:

- Memory utilization (Mức sử dụng Bộ nhớ)
- Disk Swap utilization (Mức sử dụng Disk Swap - còn gọi là RAM ảo của Linux)
- Disk Space utilization (Mức sử dụng Dung lượng đĩa - còn gọi là RAM ảo của Windows)
- Page file utilization (Mức sử dụng tệp Trang)
- Log collection (Thu thập Log)
