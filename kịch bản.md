# KỊCH BẢN SỬ DỤNG

## 1. THÔNG TIN CƠ BẢN
### 1.1 Thông tin đơn hàng
#### Các thành phần khi tạo đơn hàng:
- Sản phẩm: chọn mặt hàng
- Tên sản phẩm -> Gen từ chọn mặt hàng 
- Đơn giá
- Số lượng
- Số lượng còn trong kho
- Đơn vị tính

#### Hóa đơn:
- Thành tiền  
- Thuế: khó ktra ?
- Tổng trước thuế
- Khuyến mãi: chọn khuyến mãi  
- Tổng sau thuế:
- (Cam kết chất lượng)

#### Chốt đơn
- Địa chỉ nhận hàng
- SĐT
- Mail
- Thông tin chung: 
    - Mã báo giá
    - Thời gian hiệu lực ~ Priority ~ chế độ giao hàng
- Các sản phẩm:
    - STT
    - Mã SP
    - Tên SP
    - Đơn vị tính
    - Giá niêm yết
    - Giá tính tiền
    - Số lượng
    - Khuyến mãi
    - Thành tiền
    - Thuế
    - Tổng tiền
    - Cam kết chất lượng
    - Ghi chú
- Giao hàng: 
   - Phí giao hàng
   - Thời gian giao dự kiến

- Khuyến mãi toàn đơn
    - Mã Khuyến mãi
    - Sử dụng xu

### 1.2 Thông tin quản lý sản xuất
#### Kế hoạch sản xuất 
- STT
- Mã kế hoạch
- Người tạo
- Người phê duyệt
- Ngày tạo
- Ngày bắt đầu
- Ngày dự kiến hoàn thành 
- Trạng thái
- Hành động  

#### Lịch sản xuất  
- Mã xưởng
- Tên xưởng  
- Ca làm việc: 1 -> 25
- Trạng thái: 
    - Chưa có lệnh
    - Mới tạo
    - Đang chờ duyệt
    - Đã phê duyệt
    - Đang thực hiện
    - Đã hoàn thành
## 2. KỊCH BẢN
Ý tưởng: Biến bài toán từ 1 kho thành nhiều kho. User/Customer đặt đơn hàng, hệ thống sẽ tìm các kho bất kỳ đáp ứng được các đơn hàng.  
--> Vận dụng được giải pháp VRP multi-depot của anh Công thay vì chỉ sử dụng 1 kho duy nhất. 
##### Input  
Đơn hàng:  
- Mã SP (hoặc tên SP): tự gen ra các thông tin còn lại:
    - Đơn giá  
    - (Khối lượng 1SP): có thể show ra cho người dùng xem hoặc là tự biết
- Số lượng  
    - Đơn vị tính
    - (Tổng khối lượng): có thể show ra cho người dùng xem hoặc là tự biết
    - Tổng giá
- Nhu cầu, cho người dùng tích chọn: 
    - Xử lý, tự vận chuyển được
    - Đã được xử lý, bây giờ cần vận chuyển
    - Cả hai
- Thời gian:  
    - Khởi tạo đơn hàng
    - (Hoàn thành mong muốn): Nếu khách hàng có nhu cầu giao hàng trước ngày
        - Nếu có thời gian hoàn thành thì sẽ chia priority như ở dưới:
            - Deadline trong 5 ngày: Cao
            - Deadline trong 10 ngày: Trung bình
            - Deadline trên 10 ngày hoặc không có: Thấp
- (Priority): 
    - Các cấp
        - Thấp ~ Giao hàng tiêu chuẩn
        - Trung bình ~ Giao hàng trung bình
        - Cao ~ Giao hàng nhanh

### 2.1 Kịch bản hoạt động đơn lẻ  
#### 2.1.1. Xử lý đơn  
|Bước|Điều hướng|Nội dung|  
|--|--|--| 
|1|Quản lý đơn hàng > Đơn hàng|Tích chọn các đơn hàng muốn lập lịch >> Nhấn lập lịch|  
|2|Kiểm tra đơn hàng|Tất cả các đơn được đáp ứng bởi các kho -> Bước 3|  
|2'|Kiểm tra đơn hàng - báo lỗi|Có ít nhất 1 đơn không kho nào đáp ứng được -> Báo lỗi|  
|3|Màn hình|Display biểu đồ so sánh các lịch đã được tính, cùng danh sách các lịch trình|
|4|Chi tiết lịch trình|Chi tiết lịch tại từng kho và từng đơn trong kho: thời gian hoàn thành dự kiến, chi phí dự kiến, nhân viên tham gia. Với mỗi kho sẽ có 1 bảng phân công chi tiết: nhân viên nào làm tác vụ nào cho đơn nào trong kho|
|5|Lưu lịch trình mong muốn|Bấm nút lưu lịch trình|
|5'|Tiếp tục vận chuyển|User muốn sử dụng lịch trình đã dựng làm đầu vào cho lịch vận chuyển, thì có thể vào mục Quản lý vận chuyển để tiếp tục|  

##### Output Xử lý đơn
- Từng kho nhận xử lý đơn 
- Thời gian hoàn thành của từng đơn 

#### 2.1.2. Vận chuyển
### 2.2 Kịch bản hoạt động tích hợp
Quản lý đơn hàng
> Đơn hàng
> Lịch trình
    > Lịch trình xử lý: tìm được các lịch đã Lưu
    > Lịch trình vận chuyển: tìm 

### Trạng thái đơn hàng  
0 chưa phê duyệt
1 đã phê duyệt
2 đã lập lịch xử lý trong kho
3 đã lập lịch vận chuyển  
4 đang xử lý trong kho  
5 đang vận chuyển  
6 Hoàn thành  
7 Hủy

nhận xét về phần kho:
2 loại đơn hàng:
+ nhập hàng
+ xuất hàng  
Hướng của mình là gì
giải quyết phần kho của công ty nào: công ty sản xuất hay công ty logistics 
cần dựng kịch bản:
 kho + giao hàng: của sản xuất. doanh nghiệp này quan tâm đến việc làm xong thì xuất luôn, công ty làm theo quy trình rất ẩu, đôi khi còn cắt bước.  kho nội đô số khách hàng lớn
 kho + giao hàng: logistics. không quan tâm về tồn kho vì nó chỉ làm cho thuê kho và vận chuyển hàng hóa cho khách hàng. (GK logistics), xe đường dài tập khách hàng cố định. 


 --> cần làm rõ đối tượng để làm tường minh hơn cái flow chart.  


 Hồng Anh làm đầu mối vẽ kịch bản 
 Trung khả năng tích hợp / pá.