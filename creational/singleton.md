# Singleton Pattern

Singleton nằm trong bộ creational design pattern. Singleton là rất dễ để nhớ.
Như tên gọi của nó, nó hạn chế tạo instance một type, chỉ tạo một instance duy
nhất trong toàn bộ program

Bạn sẽ sử dụng mẫu Singleton trong nhiều tình huống khác nhau. Ví dụ:

* Khi bạn muốn sử dụng cùng một kết nối với database để thực hiện mọi truy vấn
* Khi bạn mở kết nối Secure Shell (SSH) đến server để thực hiện một số tác vụ và
  không muốn mở lại kết nối cho từng tác vụ
* Nếu bạn cần giới hạn quyền truy cập vào một số variable hoặc space, bạn sử dụng
  Singleton làm cửa để truy cập cho variable này (chúng ta sẽ thấy trong các
  chương sau đây có thể đạt được điều này trong Go bằng cách sử dụng các channel)
* Nếu bạn cần giới hạn số lượng cuộc gọi đến một số địa điểm, bạn tạo một Singleton
  để thực hiện các cuộc gọi.

## Implementation

#### Singleton not safe

Trong một vài languages như Java, C++ chúng ta có `static` keyword được sử dụng
để implement singleton. Nhưng thật không may trong Go không có `static` keyword,
nhưng chúng ta có thể tận dụng scope của package và pointer để imlement
singleton:

```go
package singleton

type singleton struct{
 count int
}

var instance *singleton

func GetInstance() *singleton {
 if instance == nil {
 instance = new(singleton)
 }
 return instance
}
```

Trong go bạn không thể tạo một struct giá trị là `nil`. Vì vậy một pointer
singleton struct được định nghĩa `var instance *singleton` (pointer trong Go có zelo value là `nil`). Vì vậy chúng ta có thể kiểm tra bên trong function
`GetInstace` variable đã được khởi tạo hay chưa.

#### Singleton safe

Trong các ứng dụng trong thế giới thực, các tài nguyên như kết nối Database hoặc
Enterprise Information Systems (EIS) bị hạn chế và nên được sử dụng một cách khôn
ngoan để tránh bất kỳ khủng hoảng tài nguyên nào. Dưới đây chúng ta sẽ sử sync.Once
để imlement singleton safe giữa các goroutines

```go
package singleton

import "sync"

type singleton map[string]string

var (
	once     sync.Once
	instance singleton
)

func GetInstance() singleton {
	once.Do(func() {
		instance = make(singleton)
	})

	return instance
}
```
`once.Do` cho phép thực thi function đúng một lần đầu cho instance của `sync.Once{}`. Nếu `once.Do(f)` được gọi nhiều lần bởi các goroutines khác, chỉ
một lần đầu tiên gọi `f`
