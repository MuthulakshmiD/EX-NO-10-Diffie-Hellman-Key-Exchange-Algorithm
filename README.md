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

Name:Muthulakshmi D
Reg:212223040122

```
def mod_exp(base, exp, mod):
    result = 1
    while exp > 0:
        if exp % 2 == 1:
            result = (result * base) % mod
        exp = exp >> 1  # equivalent to exp // 2
        base = (base * base) % mod
    return result

# User inputs
P = int(input("Enter the value of P: "))
print(f"The value of P: {P}")

G = int(input("Enter the value of G (Primitive root of P): "))
print(f"The value of G: {G}\n")

a = int(input("Enter the private key for Alice (a): "))
x = mod_exp(G, a, P)

b = int(input("Enter the private key for Bob (b): "))
y = mod_exp(G, b, P)

ka = mod_exp(y, a, P)  # Alice computes shared key
kb = mod_exp(x, b, P)  # Bob computes shared key

print(f"\nShared secret key for Alice : {ka}")
print(f"Shared secret key for Bob   : {kb}")
```

## Output:

![image](https://github.com/user-attachments/assets/04aff701-c087-482f-8a69-b9efd51e8932)


## Result:
  The program is executed successfully

