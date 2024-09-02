# Cryptography---19CS412-classical-techqniques
# Caeser Cipher
Caeser Cipher using with different key values

# AIM:

To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.


## DESIGN STEPS:

### Step 1:

Design of Caeser Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

1.	In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
2.	For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
3.	The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the   
    scheme, A = 0, B = 1, Z = 25.
4.	Encryption of a letter x by a shift n can be described mathematically as,
                       En(x) = (x + n) mod26
5.	Decryption is performed similarly,
                       Dn (x)=(x - n) mod26


## PROGRAM:
PROGRAM:
CaearCipher.

Encryption:
```                                                                                                 
#include <stdio.h>
#include <string.h>

void encryptCaesarCipher(char* message, int shift) {
    for (int i = 0; i < strlen(message); i++) {
        char c = message[i];
        
        // Check for uppercase letters
        if (c >= 'A' && c <= 'Z') {
            message[i] = ((c - 'A' + shift) % 26) + 'A';
        }
        // Check for lowercase letters
        else if (c >= 'a' && c <= 'z') {
            message[i] = ((c - 'a' + shift) % 26) + 'a';
        }
    }
}

int main() {
    char message[100];
    int shift;

    printf("Enter a message: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = 0;  // Remove newline character

    printf("Enter shift value: ");
    scanf("%d", &shift);

    // Encrypt the message
    encryptCaesarCipher(message, shift);
    printf("Encrypted Message: %s\n", message);

    return 0;
}
```

Decryption:
```
#include <stdio.h>
#include <string.h>

void decryptCaesarCipher(char* message, int shift) {
    for (int i = 0; i < strlen(message); i++) {
        char c = message[i];
        
        // Check for uppercase letters
        if (c >= 'A' && c <= 'Z') {
            message[i] = ((c - 'A' - shift + 26) % 26) + 'A';
        }
        // Check for lowercase letters
        else if (c >= 'a' && c <= 'z') {
            message[i] = ((c - 'a' - shift + 26) % 26) + 'a';
        }
    }
}

int main() {
    char message[100];
    int shift;

    printf("Enter an encrypted message: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = 0;  // Remove newline character

    printf("Enter shift value used for encryption: ");
    scanf("%d", &shift);

    // Decrypt the message
    decryptCaesarCipher(message, shift);
    printf("Decrypted Message: %s\n", message);

    return 0;
}
```


## OUTPUT:
OUTPUT:

Encryption:

![alt text](1.png)

Decryption:

![alt text](<decrypt 1.png>)


## RESULT:
The program is executed successfully

---------------------------------
