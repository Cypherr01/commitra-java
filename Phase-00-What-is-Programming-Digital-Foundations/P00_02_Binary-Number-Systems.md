## What Is This?
Computers speak in **binary** — a language of 0s and 1s representing "off" and "on" electrical states. Think of it like a light switch: it only understands two positions (on/off), not "dim" or "bright." Binary is the foundation of all digital data, from your name stored in a database to streaming a movie. This topic unlocks how numbers, text, and even colors are encoded for machines.

## How It Works Internally
### Layer 1 — Minimum Viable Version
Computers use binary because transistors (tiny electronic switches) have two stable states: **voltage present** (1) or **no voltage** (0). All number systems derive from this:
- **Decimal (base-10):** Human counting (digits 0-9).
- **Binary (base-2):** Computer counting (digits 0-1).
- **Hexadecimal (base-16):** Compact binary shorthand (digits 0-9, A-F).
- **Octal (base-8):** Legacy system (digits 0-7), used in Unix permissions.

### Layer 2 — Why the Simple Version Breaks
Humans count in decimal, but computers only process binary. Trying to store numbers without conversion causes gibberish. Example: The decimal number 255 becomes `11111111` in binary. Add 1 without handling overflow? It becomes `00000000` (wiping the value).

### Layer 3 — The Production Version
**Base Conversions:**  
To convert decimal → binary:  
1. Divide the number by 2.  
2. Record the remainder (0 or 1).  
3. Repeat with the quotient until it reaches 0.  
*Example: 13 → 1101 (remainders 1, 0, 1, 1 read backward).*  

**Hexadecimal Shortcut:**  
Group binary digits into sets of 4 (pad with leading zeros). Map each group to hex:  
`0000=0`, `0001=1`, ..., `1010=A`, `1111=F`.  
*Example: `11010111` → `0xD7`.*  

**Two's Complement for Negatives:**  
Flip bits and add 1.  
*Example: -5 in 8-bit binary = `11111011`.*  

### Layer 4 — Edge Cases and Failure Modes
1. **Overflow in Banking:**  
   *Trigger:* Depositing $1 into an account at `2,147,483,647` (Java `int` max).  
   *Symptom:* Balance wraps to `-2,147,483,648`.  
   *Fix:* Use `long` (64-bit) for large values.  

2. **Hexadecimal Input Error:**  
   *Trigger:* Entering `G` (invalid) instead of `A-F` in a color code.  
   *Symptom:* System crash or corrupted display.  
   *Fix:* Validate input against hex characters.  

CORE INSIGHT: All numbers are stored as binary patterns. Misunderstand the pattern → catastrophic data corruption.

## Syntax and Structure
```text
# CONCEPTUAL PSEUDOCODE: Decimal to Binary Conversion
# STEP 1: Initialize number = 13 (decimal input)
# STEP 2: Divide by 2 → quotient = 6, remainder = 1 → store remainder
# STEP 3: Divide 6 by 2 → quotient = 3, remainder = 0 → store remainder
# STEP 4: Divide 3 by 2 → quotient = 1, remainder = 1 → store remainder
# STEP 5: Divide 1 by 2 → quotient = 0, remainder = 1 → store remainder
# STEP 6: Read remainders backward → 1101 (binary)
# STEP 7: Terminate process when quotient = 0
In Phase 1 we will write this in real code.
```

## Common Mistakes Beginners Make
- **Ignoring overflow limits:** Assuming numbers "grow infinitely" → crashes in ticket systems when counters exceed `2^31-1`.  
- **Wrong idea:** Hex `A` equals decimal 10.  
  **Correct idea:** Hex `A` equals binary `1010` (value 10).  
- **Silent two's complement error:** Forgetting the sign bit → misinterpreting `11111111` as -1 (correct) vs. 255 (wrong context).  
- **Missed padding:** Not grouping binary into 4-bit chunks for hex → `101` becomes `5` instead of `0005`.  
- **Interview question:** *"Why can’t Java `int` hold 3 billion?"*  
  Surface answer: "Hard limit of 2³¹−1."  
  Production answer: "Prevents silent overflow in systems like stock exchanges where values wrap to negatives."

## Verification Task 1 — Debug This
Your system shows a user's balance as `-2,147,483,648` after a $1 deposit. You have evidence the balance was `2,147,483,647` pre-deposit. Diagnose and fix.

## Solution 1
The `int` type overflowed. Fix:  
1. Replace `int` with `long` (64-bit capacity).  
2. Add overflow checks: `if (balance == Integer.MAX_VALUE) throw exception`.  
3. Use arbitrary-precision `BigInteger` for critical financial values.

## Verification Task 2 — Design Decision
Building a temperature sensor. Use **8-bit two's complement** or **16-bit unsigned** for readings? Defend using this topic.

## Solution 2
Choose **8-bit two's complement** if temperatures range from -128°C to +127°C (common in freezers). It natively handles negatives. For wider ranges (e.g., -32,768°C to +32,767°C), use 16-bit two's complement. Avoid unsigned unless negatives are impossible (e.g., CPU usage %).

## Verification Task 3 — Code Review
```text
# PSEUDOCODE: Convert decimal to hex (BUGGED)
# Input: decimal = 255
# STEP 1: Divide by 16 → quotient = 15, remainder = 15
# STEP 2: Map remainder 15 → 'F'
# STEP 3: Map quotient 15 → 'F'
# STEP 4: Combine → 'FF' (CORRECT)
# BUT: What if remainder = 10? Map to 'A'
```
Find the subtle bug when converting 10 → hex.

## Solution 3
The code fails when the **quotient is non-zero but unprocessed**. For 10:  
- Step 1: 10 / 16 → quotient=0, remainder=10 → maps to 'A'.  
- But the loop stops here. **Fix:** Continue dividing the quotient until it reaches 0. Correct steps:  
1. 10 → remainder 10 → 'A'  
2. Quotient 0 → stop. Result: 'A' (not '0A').  
Production fix: Pad with leading zeros for consistent digit length.

## What Comes Next
Next topic: **Bits, Bytes & Data Representation**. Binary is the language, but how do computers package these 0s and 1s into usable chunks? This topic builds directly on number systems to explain how single bits combine into bytes, words, and the data types (like `int`) you’ll use in Java. Mastery here prevents memory errors in NexaBank’s transaction systems.

## Reference Summary
Binary (base-2) is computing's native language due to hardware limitations. Decimal (base-10) and hexadecimal (base-16) serve human readability and compact binary representation, while octal (base-8) appears in legacy systems. Conversions between systems require division/remainder algorithms, and two's complement enables negative numbers. Java's fixed-size `int` causes overflow at 2³¹−1, risking data corruption in finance or ticketing. For NexaBank, this underpins all numerical data processing—mismanage it, and balances vanish. Next, you'll learn how these binary patterns assemble into bytes and data structures.