# Run Log - FIT4012 Lab 1

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