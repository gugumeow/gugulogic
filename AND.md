#### True Table

| A | B | Output (A AND B) |
|---|---|------------------|
| 0 | 0 | 0                |
| 0 | 1 | 0                |
| 1 | 0 | 0                |
| 1 | 1 | 1                |

#### 確保前一個指令成功執行後，才執行下一個指令。

sudo apt update && sudo apt install -y qemu-system-riscv32

#### 判斷AB二台電腦在相同網段。
( IP_A && SubnetMask_A ) == ( IP_B && SubnetMask_B )
