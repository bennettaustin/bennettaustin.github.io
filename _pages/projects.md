---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

## Animating the Mandelbrot Set

## RSA Cryptopgraphy
RSA is a method of public key cryptography, which allows two people who have never met or talked before to communicate securely over a public server. I programmed an entire RSA cryptosystem from the ground up. The first steps required studying number theory in great detail to develop the tools and theorems that allow RSA to actually function. Such work included proving results about finite fields, primitive roots for Fp*, Euler's theorem for primes p and q, eth roots modulo p, the Miller-Rabin test, and Euler's phi function. From this, RSA can be built by merging several, smaller helper algorithms. These algorithms are as follows: computing exponents modulo some number N, computing the greatest common divisor of two numbers and their Bezout coefficients, converting text to integers and integers to text, solving for the eth root of a number modulo a product of primes, and a large prime number generator. If you have a way of running Python code ([here is an online compiler if you need one](https://www.online-python.com/)), run the following code to send me a message that only I can decrypt and read. All you have to do is copy and paste the code below and then in the last line of code replace "message" with your message in quotes. Copy the output and email it to me (my email it to the left). Note: if you wish to send a longer message (i.e. > two sentences), then break up the message and run the code with parts of the message. For example, a five sentence message should be sent by running the code for each sentence and sending each of the five outputs separately. 
```python

def fastPowerSmall(g,A,N):
    a = g
    b = 1
    while A > 0:
        if A % 2 == 1:
            b = (b*a) % N
        a = (a*a) % N
        A //= 2
    return b % N
    
def textToInt(w):
    n = 0
    r = len(w)
    for i in range(0, r):
        n += ord(w[i])*(256)**i
    return n
    
def key_pub():
    
        return [95687730267736468309105655407326754782500942659897869053985746521303037185871428164059832595106765058507906558664508450950635050113862445069320621540629306105731589037156189773163244798310450131207271493890279095841811217699314917886618078943597566202288313042147728130245090840954661667379318327564644668627,
  943274833941751059398336489877147157885860262577555206151049927144480573932070294827847988654171915814614443633593140673062574476670615531359423766696523675871934265576543144241486506891932586452418987530075528160352882626456721240768279336073865694139601039446419026302729795926667687331673281918884254251]
    
def RSAEncrypt(message, PublicKey):
    N, e = PublicKey[0], PublicKey[1]
    m = textToInt(message)
    c = fastPowerSmall(m, e, N)
    return c
    
print(RSAEncrypt(message, key_pub()))

```

## Elliptic Curve Cryptography

## Factoring the Product of Large Primes

## Digital Key Signatures
