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
    - Thời gian hiệu lực ~ Priority ~ **Chế độ giao hàng**
- Các sản phẩm:
    - STT
    - **Mã SP**
    - Tên SP
    - Đơn vị tính
    - Giá niêm yết
    - Giá tính tiền
    - **Số lượng**
    - Khuyến mãi
    - Thành tiền
    - Thuế
    - Tổng tiền
    - Cam kết chất lượng
    - Ghi chú
- Giao hàng: 
   - Phí giao hàng (bỏ)
   - **Thời gian giao mong muốn**

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
### 2.1 Kịch bản hoạt động đơn lẻ  
#### 2.1.1 Xử lý  

**Multipot problem:**   
Map đơn hàng với kho mong muốn. cho auto map đơn hàng - kho. 
Người dùng chỉ có nhu cầu lập lịch xử lý (các) đơn hàng đang chờ xử lý.  
B1: Tại **Quản lý đơn hàng**, chọn mục **Đơn bán hàng**
B2: Với danh sách các đơn hàng được hiện lên, tích chọn các đơn hàng muốn lập lịch, sau đó chọn **Lập lịch**
#### 2.1.2 Vận chuyển  
##### Input:  
Giá trị đơn hàng  
Chế độ đơn hàng: tiêu chuẩn, nhanh, siêu tốc, ..

Ràng buộc: thời gian, địa điểm,   
Phí bốc dỡ: dựa trên khối lượng, thể tích.  

*Bỏ deadline giao hàng*
### 2.2 Kịch bản hoạt động tích hợp  


### Output
Thời gian hoàn thành thực tế



