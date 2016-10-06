## Quy tắc viết Typescript


### 1. Đặt tên:

#### a. Class/Interface/Const/Enum:

- Xài PascalCase cho tên lớp, interface, hằng và enum.
  ví dụ: `UserPage`, `User`, `UserManager`...
- Sử dụng danh từ cho tên Lớp/Hằng và enum. Sử dụng danh từ hoặc tính từ cho interface.
  ví dụ: `Readable`, `Cancellable`
- Đặt tên file trùng với tên lớp public chứa trong module đó.

#### b. Biến

- Xài camelCase cho tên biến. Ví dụ: `currentUser`
- Sử dụng danh từ cho tên biến. Đối với biến boolean xài `has/is`. Ví dụ: `hasHiv`.
- Không sử dụng các từ viết tắt không thông dụng. Xem thừ viết tắt như 1 từ bình thường. 
Ví dụ: `innerHtml` thay vì `innerHTML`, `userId` thay vì `userID`


#### c. Phương thức/hàm:

- Sử dụng camelCase và bắt đầu bằng một động từ.
- Không viết lại tên lớp trong tên hàm. Ví dụ trong lớp `Building`, xài tên `getInfo()` thay vì `getBuildingInfo()`.
- Nếu không cần thiết, không khai cần báo kiểu trả về cho hàm.
- Một hàm chỉ nên có một lệnh return.

### 2. Khoảng trắng và dòng trắng

- Sử dụng khoảng trắng sau các từ khoá điều khiển để phân biệt với hàm.

```
if (điều kiện) {
}

function(thamSố1, thamSố2);
```

- Sử dụng dòng trắng để phân cách các phần khác nhau của code 
(giữa 2 member, giữa 2 class, giữa 2 đoạn code có ý nghĩa khác nhau).

- Không sử dụng khoảng trắng  trong khi set property cho component

```
<Component property={value} />
```

### 3. Các nguyên tắc chung:

- Sử dụng `const` và `let` để khai báo biến. Tránh sử dụng `var`.
- Sử dụng `for (const item in collection)` để duyệt qua một tập hợp.
```
for (const user of users) {
}
```

- Sử dụng `collection.map(item => convert(item))` để chuyển kiểu dữ liệu.
- Sử dụng `event={() => this.method(parameters)}` trong jsx thay vì sử dụng `bind()`.
- Sử dụng `async` và `await` lúc cần thiết thay vì xài promise `then` và `catch`.
- Nếu một dòng dài hơn 80 kí tự thì xuống dòng. Ví dụ:

```
   <Component parameter1="parameter1"
              parameter2="parameter2"
              parameter3="parameter3" />
```

### 4. React:

- Chia nhỏ ra các component với các chức năng cơ bản.
- Hạn chế sử dụng các biến trong state. Một biến đặt là state của một component sai khi: 
không thay đổi trong quá trình chạy, được truyền từ bên ngoài vào hoặc có thể tính toán từ các biến state khác (sử dụng getter để tính biến này).
- Sử dụng map để render 1 danh sách các đối tượng.

```
<div class="Buildings">
  {this.buildings.map(building => (
    <Building building={building} />
  )}
</div>
```


### 5. UX:

- Luôn luôn xử lý lỗi trong mã nguồn.

```
try {
   // do something
} catch (error) {
   // thông báo với người dùng
   // đề xuất giải quyết
   // không được đưa người dùng vào thế bí.
}
```

- Luôn có giao diện cho trường hợp xấu (không có dữ liệu).
- Luôn có loading khi thực hiện một hành động Async.


