## 1. What is REST

- REST là viết tắt của REpresentational State Transfer, là một số quy tắc ràng buộc khi thiết kế hệ thống mạng, REST giúp client tương tác với server mà không cần biết server hoạt động ntn
- REST có một số ràng buộc:

  - Uniform interface: giao diện thống nhất
  - Stateless: không trạng thái
  - Cacheable: Dữ liệu có thể lưu vào bộ nhớ cache
  - Client - Server: Máy khách, máy chủ
  - Layered system: Hệ thống phân lớp
  - Code on demand: Code theo yêu cầu

## 2. What is API

- API là cơ chế cho phép 2 thành phần phần mềm giao tiếp với nhau bằng 1 tập hợp các định nghĩa và giao thức

## 3. What is RESTful API

- Là một API chuẩn REST < sử dụng các phương thức http để request có nghĩa
  - > GET : Đọc tài nguyên
  - > PUT : Cập nhật tài nguyên
  - > DELETE : Xoá tài nguyên
  - > POST : Tạo mới tài nguyên

## 4. Cung cấp tên cho tài nguyên hợp lí

- Sử dụng id định danh cho url chứ không dùng query_string
  - Nên: users/123
  - Không nên: /api?type=user&id=23
- Sử dụng số nhiều để có tính nhất quán
  - Nên: /customer/33245/orders/8769/lineitems/1
  - Không nên: /customer/33245/order/8769/lineitem/1

## 5. Dùng các HTTP response code để xác định trạng thái API trả về

- 200 OK: Thành công
- 201 CREATED: Tạo thành công (POST,PUT)
- 204 NO CONTENT: Thành công nhưng k trả gì về body cả(DELETE,PUT)
- 400 Bad Request: Lỗi có thể nguyên nhân từ validaye lỗi, thiếu data,...
- 401 UNAUTHORIZED: Lỗi liên quan đến thiếu hoặc sai authentication token
- 403 FORBIDENT: Lỗi liên quan đến không có quyền truy cập
- 404 Not Found: Lỗi liên quan đến tài nguyên không tìm thấy
- 405 Method not allowed Lỗi liên quan đến method không được chấp nhận. vd API chỉ cho phép dùng POST,GET,PUT nhưng bạn dungf DELETE
- 500 INTERNAL SERVER ERROR: lỗi liên quan đến servẻ bị lỗi khi xử lí 1 tác vụ gì đó(SV không cố ý trả về lỗi này cho bạn)

## 6. Sử dụng JSON hoặc XML(ít phổ biến hơn) để giao tiếp clien-server
