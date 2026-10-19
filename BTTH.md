# (Bài tập tổng hợp) Hồ Sơ Đồ Án Hệ Thống Quản Lý Thư Viện Trường
## Phần 1 –Hoàn thiện SRS bằng Heading Styles và Auto TOC
## 1. Danh sách tiêu đề 3 cấp
```
# 1. Giới thiệu dự án 
## 1.1. Mục tiêu
## 1.2. Đối tượng sử dụng

# 2. Chức năng hệ thống
## 2.1. Quản lý mượn sách
### 2.1.1. Luồng mượn sách qua thẻ sinh viên
## 2.2. Quản lý trả sách

# 3. Yêu cầu bảo mật
```



## 2. Nội dung mô tả yêu cầu
Mục 2. Chức năng hệ thống – Yêu cầu chức năng
Hệ thống cho phép sinh viên tra cứu sách và tạo phiếu mượn theo mã sinh viên. Thủ thư có thể xác nhận mượn, cập nhật trạng thái trả sách và theo dõi các phiếu quá hạn.
Mục 3. Yêu cầu bảo mật – Yêu cầu phi chức năng
Hệ thống phải yêu cầu đăng nhập và phân quyền theo từng vai trò người dùng. Dữ liệu sinh viên và lịch sử mượn trả phải được bảo vệ, tránh truy cập trái phép.

## 3. Tạo mục lục tự động
1.  Gán Heading Styles cho các tiêu đề.
2.  Đặt con trỏ ở đầu tài liệu, chọn References → Table of Contents.
3.  Chọn mục lục tự động.
4.  Thêm nội dung để mục 3 chuyển sang trang sau.
5.  Nhấp phải vào mục lục, chọn Update Field → Update entire table
6.  Chụp ảnh mục lục sau khi cập nhật để nộp bài.
# Phần 2 – Chuẩn hóa dữ liệu và AutoFilter
## 1. Ba lỗi vi phạm quy tắc dữ liệu
| Lỗi | Vị trí (hàng) | Quy tắc bị vi phạm |
|---|---|---|
| Gộp ô tiêu đề A1:E1 | Hàng 1 | Không merge ô trong vùng dữ liệu |
| Có hàng trống hoàn toàn | Hàng 5 | Không để hàng trống xen giữa dữ liệu |
| Dòng Tổng cộng nằm trong bảng | Hàng 6 | Không đặt dòng tổng kết trong vùng dữ liệu |
## 2. Bảng dữ liệu sau khi chuẩn hóa
| MSSV | Họ Tên | Mã Sách | Ngày Mượn | Tình Trạng |
|---|---|---|---|---|
| SV001 | Nguyễn Văn An | S001 | 01/10/2026 | Đang mượn |
| SV002 | Trần Thị Bình | S002 | 03/10/2026 | Quá hạn |
| SV003 | Lê Văn Cường | S003 | 10/10/2026 | Đã trả |
| SV004 | Phạm Thu Hà | S099 | 12/10/2026 | Đang mượn |

## 3. Phân biệt Record và Field
-   Record (bản ghi): Một dòng dữ liệu của một sinh viên, ví dụ: `SV001 – Nguyễn Văn An – S001`.
-   Field (trường dữ liệu): Một cột mô tả thuộc tính, ví dụ: `MSSV`, `Mã Sách` hoặc `Tình Trạng`.
    
## 4. Bật AutoFilter
1.  Chọn một ô trong bảng dữ liệu đã chuẩn hóa.
2.  Nhấn `Ctrl + Shift + L`.
3.  Nhấn mũi tên lọc tại cột Tình Trạng.
4.  Chỉ chọn Quá hạn.
## Phần 3 – Nối dữ liệu bằng VLOOKUP
1. Công thức VLOOKUP tại F2
```=VLOOKUP(C2,DanhMucSach!$A$2:$C$4,2,FALSE)```
2. Xử lý mã S099
```=IFERROR(VLOOKUP(C5,DanhMucSach!$A$2:$C$4,2,FALSE),"Không tìm thấy sách")```

## Phần 4 – Slide báo cáo tiến độ
## Nội dung một slide duy nhất
```Áp dụng Rule 10/20/30```
-   10 slide: Slide này chiếm 1/10 tổng số slide.
-   20 phút: Dành khoảng 2 phút trình bày slide này nếu phân bổ đều thời gian.
-   30 pt: Cỡ chữ nội dung tối thiểu khoảng 30 pt theo quy tắc được yêu cầu.
```Title: “Dữ liệu mượn sách đã được chuẩn hóa và sẵn sàng tra cứu tự động”```
Content Area:
-   Đã chuẩn hóa 4 phiếu mượn sách.
-   Có 1 phiếu quá hạn, 2 phiếu đang mượn và 1 phiếu đã trả.
-   Bổ sung VLOOKUP để tự động lấy tên sách; mã `S099` được nhận diện là chưa có trong danh mục.
Biểu đồ đề xuất: Bar Chart (biểu đồ cột).



