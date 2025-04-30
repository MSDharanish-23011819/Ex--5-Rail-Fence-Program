# Ex--5-Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
def encrypt_rail_fence(text):
    even_chars = ''
    odd_chars = ''

    for i in range(len(text)):
        if i % 2 == 0:
            even_chars += text[i]
        else:
            odd_chars += text[i]

    cipher_text = even_chars + odd_chars
    return cipher_text

def decrypt_rail_fence(cipher_text):
    length = len(cipher_text)
    if length % 2 == 0:
        k = length // 2
    else:
        k = (length // 2) + 1

    first_half = cipher_text[:k]
    second_half = cipher_text[k:]

    decrypted = [''] * length
    j = 0
    for i in range(0, length, 2):
        decrypted[i] = first_half[j]
        j += 1

    j = 0
    for i in range(1, length, 2):
        decrypted[i] = second_half[j]
        j += 1

    return ''.join(decrypted)

print("\n\t\t RAIL FENCE TECHNIQUE")
input_text = input("\nEnter the input string: ")

cipher_text = encrypt_rail_fence(input_text)
print("\nCipher text after applying rail fence:", cipher_text)

decrypted_text = decrypt_rail_fence(cipher_text)
print("Text after decryption:", decrypted_text)
```

# OUTPUT
![image](https://github.com/user-attachments/assets/174851be-8cc1-4731-9c7d-fef57b06e6a4)

# RESULT
The program is executed successfully
