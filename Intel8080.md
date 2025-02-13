|HLh| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**0**|00h|01h|02h|03h|04h|05h|06h|07h|08h|09h|0Ah|0Bh|0Ch|0Dh|0Eh|0Fh|
|**1**|10h|11h|12h|13h|14h|15h|16h|17h|18h|19h|1Ah|1Bh|1Ch|1Dh|1Eh|1Fh|
|**2**|20h|21h|22h|23h|24h|25h|26h|27h|28h|29h|2Ah|2Bh|2Ch|2Dh|2Eh|2Fh|
|**3**|30h|31h|32h|33h|34h|35h|36h|37h|38h|39h|3Ah|3Bh|3Ch|3Dh|3Eh|3Fh|
|**4**|40h|41h|42h|43h|44h|45h|46h|47h|48h|49h|4Ah|4Bh|4Ch|4Dh|4Eh|4Fh|
|**5**|50h|51h|52h|53h|54h|55h|56h|57h|58h|59h|5Ah|5Bh|5Ch|5Dh|5Eh|5Fh|
|**6**|60h|61h|62h|63h|64h|65h|66h|67h|68h|69h|6Ah|6Bh|6Ch|6Dh|6Eh|6Fh|
|**7**|70h|71h|72h|73h|74h|75h|76h|77h|78h|79h|7Ah|7Bh|7Ch|7Dh|7Eh|7Fh|
|**8**|80h|81h|82h|83h|84h|85h|86h|87h|88h|89h|8Ah|8Bh|8Ch|8Dh|8Eh|8Fh|
|**9**|90h|91h|92h|93h|94h|95h|96h|97h|98h|99h|9Ah|9Bh|9Ch|9Dh|9Eh|9Fh|
|**A**|A0h|A1h|A2h|A3h|A4h|A5h|A6h|A7h|A8h|A9h|AAh|ABh|ACh|ADh|AEh|AFh|
|**B**|B0h|B1h|B2h|B3h|B4h|B5h|B6h|B7h|B8h|B9h|BAh|BBh|BCh|BDh|BEh|BFh|
|**C**|C0h|C1h|C2h|C3h|C4h|C5h|C6h|C7h|C8h|C9h|CAh|CBh|CCh|CDh|CEh|CFh|
|**D**|D0h|D1h|D2h|D3h|D4h|D5h|D6h|D7h|D8h|D9h|DAh|DBh|DCh|DDh|DEh|DFh|
|**E**|E0h|E1h|E2h|E3h|E4h|E5h|E6h|E7h|E8h|E9h|EAh|EBh|ECh|EDh|EEh|EFh|
|**F**|F0h|F1h|F2h|F3h|F4h|F5h|F6h|F7h|F8h|F9h|FAh|FBh|FCh|FDh|FEh|FFh|

|HLh|Instruction| Notes |
|---|---|---|
|00h|NOP||
|06h|MVI B, data||

**Fibonacci Series**: Fib(10)

```
        MVI C, 0AH       ; C = 10 (要計算 Fib(10))
        MVI B, 00H       ; B = Fib(0) = 0
        MVI A, 01H       ; A = Fib(1) = 1

        DCR C            ; C = C - 1 (因為 Fib(1) 已知，不需再計算)

LOOP:   JZ DONE          ; 若 C == 0，結束
        MOV H, A         ; H = A (暫存 Fib(n))
        ADD B            ; A = A + B (計算 Fib(n) = Fib(n-1) + Fib(n-2))
        MOV B, H         ; B = H (更新 Fib(n-1) = 原本的 A)
        DCR C            ; C = C - 1
        JMP LOOP         ; 繼續計算

DONE:   HLT             ; 停止執行

```
