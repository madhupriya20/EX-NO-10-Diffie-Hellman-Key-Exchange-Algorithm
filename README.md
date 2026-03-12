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
```
def power(base, exp, mod):
    result = 1
    for i in range(exp):
        result = (result * base) % mod
    return result

# Input values
P = int(input("Enter a prime number (P): "))
G = int(input(f"Enter a primitive root of {P} (G): "))

a = int(input("Enter private key for madhu(a): "))
b = int(input("Enter private key for priya(b): "))

# Public keys
A = power(G, a, P)
B = power(G, b, P)

# Secret keys
secretA = power(B, a, P)
secretB = power(A, b, P)

print("\nPublic Key of madhu (A):", A)
print("Public Key of priya (B):", B)

print("\nSecret Key for madhu:", secretA)
print("Secret Key for priya:", secretB)

if secretA == secretB:
    print("\nSecret key successfully established!")
else:
    print("\nError: Keys do not match.")
```



## Output:
<img width="366" height="356" alt="image" src="https://github.com/user-attachments/assets/6a70f67f-213a-439c-8fb2-fe6eefc64382" />




## Result:
  The program is executed successfully

