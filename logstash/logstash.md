# --------------------  grok  ------------------------
Grok được sử dụng để phân tích cú pháp (parsing) và trích xuất thông tin từ dữ liệu không cấu trúc như logs, và gán nó vào các trường riêng biệt trong sự kiện Logstash. Điều này giúp bạn chuyển đổi dữ liệu không cấu trúc thành dữ liệu có cấu trúc

Ví dụ, nếu bạn có một dòng log như sau:
`2023-07-15 09:30:15 INFO This is a log message.`

filter {
  grok {
    match => { "message" => "%{TIMESTAMP_ISO8601:timestamp} %{LOGLEVEL:log_level} %{GREEDYDATA:message}" }
  }
}

trường TIMESTAMP_ISO8601 sẽ được đặt tên là timestamp trong logs, ...

