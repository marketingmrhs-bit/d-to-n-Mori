# Dự toán chi phí xây dựng · MORI HOMES

Công cụ web để khách hàng tự dự toán chi phí xây dựng nhà phố, biệt thự, văn phòng và khách sạn. Khách chọn mô hình, nhập diện tích khu đất và diện tích từng tầng, chọn móng, hầm, mái, sân. Kết quả hiện ngay, kèm bảng diện tích quy đổi và mặt cắt minh họa.

Chạy thử: https://marketingmrhs-bit.github.io/d-to-n-Mori/ (sau khi bật GitHub Pages, xem bên dưới).

## Các file

| File | Dùng để |
| --- | --- |
| `index.html` | Trang web hoàn chỉnh, mở trực tiếp bằng trình duyệt hoặc chạy qua GitHub Pages |
| `wordpress/mori-du-toan-wordpress.html` | Mã nhúng cho WordPress: dán vào widget HTML của Elementor hoặc khối HTML tùy chỉnh (cần tài khoản quản trị) |

Không cần cài đặt hay build. Mỗi file là một trang tự chứa, chỉ tải phông chữ Be Vietnam Pro từ Google Fonts.

## Bật GitHub Pages

1. Vào **Settings → Pages** của repo này.
2. Mục **Build and deployment**, chọn **Source: Deploy from a branch**.
3. Chọn nhánh **main**, thư mục **/ (root)**, bấm **Save**.
4. Đợi 1–2 phút, trang chạy ở https://marketingmrhs-bit.github.io/d-to-n-Mori/

## Cách tính

Chi phí = Tổng diện tích quy đổi × Đơn giá của mô hình. Diện tích quy đổi của từng phần = diện tích × hệ số.

| Mô hình | Đơn giá |
| --- | --- |
| Nhà phố | 4.850.000 đ/m² |
| Biệt thự | 5.050.000 đ/m² |
| Văn phòng, khách sạn | 5.300.000 đ/m² |

| Hạng mục | Hệ số |
| --- | --- |
| Móng đơn | 30% diện tích trệt |
| Móng băng, cọc, bè | 50% (có đổ bê tông nền trệt: 65%) |
| Tầng hầm sâu dưới 1,2 m / 1,2–1,8 m / trên 1,8 m (so với vỉa hè) | 150% / 170% / 200% |
| Tầng trệt, lửng, các lầu, tum thang | 100% |
| Ô thông tầng của lửng | dưới 8 m² tính 100%, từ 8 m² tính 50% |
| Sân thượng | 50% |
| Mái tôn | 35% × 1,4 hệ số nghiêng |
| Mái bê tông cốt thép đúc bằng | 50% |
| Mái ngói xà gồ sắt | 50% × 1,4 |
| Mái bê tông xiên dán ngói | 75% × 1,4 |
| Sân trước, sân sau | 50% |

Vật tư hoàn thiện ước bằng 40–70% chi phí phần thô, hiện thành khoảng "tổng cả nhà".

Ví dụ: nhà phố 5 × 15 m, trệt + 2 lầu, tum 20 m², sân thượng, mái bê tông, móng băng có đổ nền: 48,75 + 75 × 3 + 20 + 27,5 + 10 = 331,25 m² × 4.850.000 = 1.606.562.500 đ.

## Sửa đơn giá, hotline

Mở `index.html`, tìm phần đầu thẻ `<script>`:

```js
const MO_HINH = {
  pho:      { label: 'Nhà phố', price: 4850000 },
  bietthu:  { label: 'Biệt thự', price: 5050000 },
  vanphong: { label: 'Văn phòng, khách sạn', price: 5300000 }
};
const CONFIG = {
  vatTu: [0.4, 0.7],
  heSoNghieng: 1.4,
  maxTang: 12,
  hotline: '078 928 6679',
  facebook: 'https://www.facebook.com/Morihomes.vn'
};
```

Sửa số rồi lưu. File WordPress có cùng khối cấu hình, nhớ sửa cả hai cho khớp.

## Liên hệ

MORI HOMES · Hotline 078 928 6679 · https://www.facebook.com/Morihomes.vn
