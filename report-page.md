# Report 1 Page – FIT4012 Lab 1

## 1. Mục tiêu
Tính toán entropy và độ dư thừa (redundancy) của chuỗi ký tự. Tìm nghịch đảo modulo sử dụng thuật toán Euclid mở rộng.

## 2. Cách làm
- Đọc hiểu chương trình entropy mẫu.
- Bổ sung hàm tính redundancy.
- Hoàn thiện hàm mod_inverse() sử dụng extended_euclid.
- Chạy thử trên nhiều test case.

## 3. Kết quả chính
### 3.1 Entropy và redundancy
| Input | Entropy | Redundancy | Nhận xét |
|---|---:|---:|---|
| aaaa | 0.000000 | 8.000000 | Thấp entropy, cao redundancy |
| abcd | 2.000000 | 6.000000 | Cao hơn aaaa |
| hello world | 2.845351 | 5.154649 | Hợp lệ |

### 3.2 Modulo inverse
| a | m | Kết quả mong đợi | Kết quả chương trình |
|---:|---:|---|---|
| 3 | 7 | 5 | 5 ✓ |
| 10 | 17 | 12 | 12 ✓ |
| 6 | 9 | Không tồn tại | -1 ✓ |

## 4. Kết luận
- Entropy đo mức độ ngẫu nhiên của dữ liệu: chuỗi lặp lại có entropy thấp.
- Redundancy = log2(alphabet_size) - entropy cho biết lượng thông tin có thể nén.
- Mod inverse tồn tại khi gcd(a,m)=1, sử dụng thuật toán Euclid mở rộng để tìm x, y sao cho ax + my = gcd(a,m).
- Khó khăn: Hiểu cách hoạt động của thuật toán đệ quy extended Euclid và xử lý kết quả âm.
