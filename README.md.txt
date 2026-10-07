# Bài thực hành ERD - Quản lý đơn đặt hàng

## 📋 Danh sách thực thể

| STT | Thực thể | Thuộc tính |
|-----|----------|-----------|
| 1 | KHACH_HANG | Mã KH, Tên KH, Địa chỉ, Điện thoại |
| 2 | HANG | Mã hàng, Tên hàng, Đv tính, Mô tả |
| 3 | NGUOI_DAT | Mã NĐ, Họ tên NĐ, Mã KH |
| 4 | NGUOI_NHAN | Mã NN, Họ tên NN, Mã KH |
| 5 | NGUOI_GIAO | Mã NG, Họ tên NG |
| 6 | NOI_GIAO | Mã ĐĐG, Tên nơi giao |
| 7 | DON_DAT_HANG | Số ĐH, Ngày đặt, Mã KH, Mã NĐ |
| 8 | CHI_TIET_DDH | Số ĐH, Mã hàng, Số lượng |
| 9 | PHIEU_GIAO_HANG | Số PG, Ngày giao, Mã KH, Mã ĐĐG, Mã NN, Mã NG, Số ĐH |
| 10 | CHI_TIET_PGH | Số PG, Mã hàng, Số lượng, Đơn giá, Thành tiền |

## 🔗 Các mối quan hệ

- KHACH_HANG (1) ─── (n) NGUOI_DAT
- KHACH_HANG (1) ─── (n) NGUOI_NHAN
- NGUOI_DAT (1) ─── (n) DON_DAT_HANG
- DON_DAT_HANG (1) ─── (n) CHI_TIET_DDH
- HANG (1) ─── (n) CHI_TIET_DDH
- NGUOI_GIAO (1) ─── (n) PHIEU_GIAO_HANG
- NGUOI_NHAN (1) ─── (n) PHIEU_GIAO_HANG
- NOI_GIAO (1) ─── (n) PHIEU_GIAO_HANG
- PHIEU_GIAO_HANG (1) ─── (n) CHI_TIET_PGH
- HANG (1) ─── (n) CHI_TIET_PGH
- DON_DAT_HANG (1) ─── (n) PHIEU_GIAO_HANG

## 📸 Sơ đồ ERD

![ERD](erd.png)

## 📝 Ghi chú

- Đã gộp ĐƠN VỊ ĐH và ĐƠN VỊ KH thành KHACH_HANG (vì cùng là đơn vị bên ngoài).
- Sử dụng bảng trung gian CHI_TIET_DDH và CHI_TIET_PGH để xử lý quan hệ n-n.