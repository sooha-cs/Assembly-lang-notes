## Decimal to Binary          

Converting Decimal to Binary: Divide by 2 repeatedly and read remainders from bottom to top.      

Example: Convert 13 to binary       

| Division |	Result  |	Remainder |
|-------|--------|---------|
| 13 ÷ 2	|6	|1 |
| 6 ÷ 2	|3	|0 |
| 3 ÷ 2	|1	|1 |
| 1 ÷ 2	|0	|1 |       

 
Read remainders bottom to top: 1101 → 13 (decimal) = 1101 (binary)          

Stop dividing when the result reaches 0. Each remainder is the next binary digit from right to left.


## Hex digits
Consist of 0–9 = 0-9, A–F = 10-15.     

Bit-to-hex mapping:       
```
8 bits (1 byte) → 2 hex digits          
16 bits → 4 hex digits           
64 bits → 16 hex digits              
```
Hex prefix used: 0x (e.g. 0xFF, 0x41 for 'A', 0x0a for newline).

## Hex to Decimal

Hexadecimal (base 16): each position is a power of 16. Digits A-F represent 10-15.       

Hex     	A 	B 	C	 D	 E	 F         
Decimal	10	11	12	13	14	15            
Converting hex to decimal: multiply each digit by its place value (16⁰, 16¹, 16², ...) and sum.     

Formula for digits d₂ d₁ d₀:      
```
Value = d₂ × 256 + d₁ × 16 + d₀ × 1
```
Examples:      

0x2A = 2×16 + 10×1 = 42     
