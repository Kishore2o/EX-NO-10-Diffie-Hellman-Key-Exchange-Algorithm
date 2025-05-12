# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```python
#include <stdio.h>

// Function for modular exponentiation
long long int power(long long int base, long long int exp, long long int mod) {
    long long int result = 1;
    base = base % mod;
    while (exp > 0) {
        if (exp % 2 == 1) { // If exp is odd
            result = (result * base) % mod;
        }
        exp = exp >> 1; // Divide exp by 2
        base = (base * base) % mod; // Square base
    }
    return result;
}

// Main Function
int main() {
    long long int P, G, x, a, y, b, ka, kb;
    printf("\n *****Diffie-Hellman Key Exchange algorithm*****\n\n");
    printf("\nEnter the value of P: ");
    scanf("%lld", &P);
    printf("The value of P: %lld\n", P);
    printf("Enter the value of G (Primitive root of P): ");
    scanf("%lld", &G);
    printf("The value of G: %lld\n\n", G);
    a = 4;  
    printf("The private key a for Alice : %lld\n", a);
    x = power(G, a, P); // Public key for Alice
    b = 3;  
    printf("The private key b for Bob : %lld\n\n", b);
    y = power(G, b, P); 
    ka = power(y, a, P); // Secret key for Alice
    kb = power(x, b, P); // Secret key for Bob

    // Display secret keys
    printf("Secret key for Alice is : %lld\n", ka);
    printf("Secret key for Bob is : %lld\n", kb);

    return 0;
}
```


## Output:

![image](https://github.com/user-attachments/assets/924f2337-ccbd-4808-95ef-417661105cdb)



## Result:
  The program is executed successfully

