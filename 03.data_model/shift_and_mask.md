Shift and mask operations are bitwise operations commonly used in programming and digital logic design. They manipulate individual bits within binary numbers and are fundamental in low-level programming, such as in systems programming, embedded systems, and computer architecture.

### Shift Operations

Shift operations move bits to the left or right within a binary number, effectively multiplying or dividing the number by powers of two.

1. **Left Shift (<<):**
   - Shifts the bits of a binary number to the left by a specified number of positions.
   - Zeroes are filled in from the right.
   - Each left shift by one position is equivalent to multiplying the number by 2.

   ```cpp
   int a = 5;       // Binary: 0000 0101
   int b = a << 2;  // Binary: 0001 0100 (20 in decimal)
   ```

2. **Right Shift (>>):**
   - Shifts the bits of a binary number to the right by a specified number of positions.
   - For unsigned numbers, zeroes are filled in from the left.
   - For signed numbers, the sign bit (most significant bit) is propagated (arithmetic shift) or zeroes are filled (logical shift).
   - Each right shift by one position is equivalent to dividing the number by 2.

   ```cpp
   int a = 20;      // Binary: 0001 0100
   int b = a >> 2;  // Binary: 0000 0101 (5 in decimal)
   ```

### Mask Operations

Mask operations use bitwise AND, OR, and XOR to manipulate specific bits within a binary number.

1. **AND Masking (&):**
   - Used to clear (set to 0) specific bits in a number.
   - A mask is created with 1s in positions to keep and 0s in positions to clear.

   ```cpp
   int a = 29;      // Binary: 0001 1101
   int mask = 21;   // Binary: 0001 0101
   int result = a & mask; // Binary: 0001 0101 (21 in decimal)
   ```

2. **OR Masking (|):**
   - Used to set (set to 1) specific bits in a number.
   - A mask is created with 1s in positions to set and 0s in positions to leave unchanged.

   ```cpp
   int a = 29;      // Binary: 0001 1101
   int mask = 2;    // Binary: 0000 0010
   int result = a | mask; // Binary: 0001 1111 (31 in decimal)
   ```

3. **XOR Masking (^):**
   - Used to toggle (invert) specific bits in a number.
   - A mask is created with 1s in positions to toggle and 0s in positions to leave unchanged.

   ```cpp
   int a = 29;      // Binary: 0001 1101
   int mask = 17;   // Binary: 0001 0001
   int result = a ^ mask; // Binary: 0000 1100 (12 in decimal)
   ```

### Practical Examples

1. **Extracting Specific Bits:**
   - Use a combination of shift and mask operations to extract specific bits from a number.

   ```cpp
   int a = 0b11001101; // Example byte
   int mask = 0b00001111; // Mask to extract lower 4 bits
   int lowerBits = a & mask; // Result: 0b00001101
   ```

2. **Setting Specific Bits:**
   - Use OR masking to set specific bits in a number.

   ```cpp
   int a = 0b11001100; // Example byte
   int mask = 0b00100000; // Mask to set the 6th bit
   int result = a | mask; // Result: 0b11101100
   ```

3. **Clearing Specific Bits:**
   - Use AND masking with a negated mask to clear specific bits.

   ```cpp
   int a = 0b11001100; // Example byte
   int mask = 0b11111011; // Mask to clear the 3rd bit (negated mask)
   int result = a & mask; // Result: 0b11001000
   ```

Shift and mask operations are powerful tools for efficient bitwise manipulation, essential for tasks like data encoding/decoding, hardware register management, and optimization of memory and performance in low-level programming.
