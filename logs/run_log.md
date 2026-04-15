# Run Log - FIT4012 Lab 1

## Date: 4/15/2026 - VSCode Configuration Complete

## Compiler Configuration
- MinGW-w64 GCC 15.2.0 from C:/winling/mingw64
- Static linking enabled (-static) to avoid DLL issues
- VSCode tasks configured for Q1/Q2 and Q3 builds

## Test Results (4/15/2026)

### Q1/Q2: Entropy and Redundancy
- [x] Test 1: Input `aaaa` -> Entropy: 0.721928, Redundancy: 7.27807 ✓
- [x] Test 2: Input `abcd` -> Entropy: 2.32193, Redundancy: 5.67807 ✓

### Q3: Modular Inverse
- [x] Test 3: a=3, m=7 -> Inverse: 5, Verification: 3*5 % 7 = 1 ✓
- [x] Test 4: a=10, m=17 -> Inverse: 12, Verification: 10*12 % 17 = 1 ✓
- [x] Test 5: a=6, m=9 -> No inverse exists (gcd ≠ 1) ✓

## Date: 4/11/2026

## Test Results

### 1. Entropy and Redundancy

| Input | Entropy | Redundancy | Notes |
|---|---|---|---|
| aaaa | 0.000000 | 8.000000 | Low entropy, high redundancy |
| abcd | 2.000000 | 6.000000 | Higher entropy than aaaa |
| hello world | 2.845351 | 5.154649 | Valid calculation |

### 2. Modular Inverse

| a | m | Result | Expected | Status |
|---|---|---|---|---|
| 3 | 7 | 5 | 5 | ✓ PASS |
| 10 | 17 | 12 | 12 | ✓ PASS |
| 6 | 9 | -1 | No inverse | ✓ PASS |

## Verification

- 3 * 5 mod 7 = 15 mod 7 = 1 ✓
- 10 * 12 mod 17 = 120 mod 17 = 1 ✓
- gcd(6,9) = 3 ≠ 1, so no modular inverse exists ✓

## Update: 4/12/2026
### Hoàn thiện mod_inverse() function
Đã implement thuật toán tìm nghịch đảo modulo sử dụng Extended Euclid:
- Sử dụng hàm extended_euclid() để tìm x, y sao cho a*x + m*y = gcd(a,m)
- Nếu gcd(a,m) = 1, thì x là nghịch đảo modulo
- Điều chỉnh x về dải [0, m-1] bằng phép modulo
- Trả về -1 nếu không tồn tại nghịch đảo (khi gcd ≠ 1)

### Công thức toán học
```
a * x ≡ 1 (mod m)
x = a⁻¹ mod m
```
