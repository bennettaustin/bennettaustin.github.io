---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

## Predicting Employee Attrition
I designed a machine learning model that predicts whether or not an employee will leave a certain company. The dataset was composed of nine features including salary, time spent at the company, and satisfication level. I used a deep neural network to build the classification algorithm. To score this algorithm, I used cross valdiation, which returned an average score of 97.6% on the testing data. The results are shown below. The confusion matrix and classification report give the overall performance of the algorithm and the feature importance plot shows which variables are most influential when deciding if an employee with leave the company. The 0 label refers to an employee staying and the 1 label corresponds to an employee leaving.

<p align="center">
  <img width="300" src="https://user-images.githubusercontent.com/93623304/143722820-ab0f7749-5010-4bb9-a600-88e4f61ae85e.png" />
</p>

<p align="center">
  <img width="500" src="https://user-images.githubusercontent.com/93623304/143722789-317b661c-1ce8-40ea-aff9-4b6e2b3603a3.png" />
  <img width="360" src="https://user-images.githubusercontent.com/93623304/143722811-7114a8ab-21f0-4d68-9f5c-95eba62bd8fd.png" />
</p>

## Predicting Cancerous Cells
I programmed another machine learning model that predicts whether or not a breast cell is cancerous. The dataset was composed of thirty features. These variables describe certain aspects of images of the cells, such as radius, perimeter, area, and concavity. I used a deep neural network to build the classification algorithm. To score this algorithm, I used cross valdiation, which returned an average score of 98.4% on the testing data. The results are shown below. The confusion matrix and classification report give the overall performance of the algorithm and the feature importance plot shows which variables are most influential when deciding if a cell is cancerous. The 0 label refers to a benign cell and the 1 label corresponds to a malignant cell. 

## RSA Cryptography
RSA is a method of public key cryptography, which allows two people who have never met or talked before to communicate securely over a public server. I programmed an entire RSA cryptosystem from the ground up. The first steps required studying number theory in great detail to develop the tools and theorems that allow RSA to actually function. Such work included proving results about finite fields, primitive roots for Fp*, Euler's theorem for primes p and q, eth roots modulo p, the Miller-Rabin test, and Euler's phi function. From this, RSA can be built by merging several, smaller helper algorithms. These algorithms are as follows: computing exponents modulo some number N, computing the greatest common divisor of two numbers and their Bezout coefficients, converting text to integers and integers to text, solving for the eth root of a number modulo a product of primes, and a large prime number generator. 

If you have a way of running Python code ([here is an online compiler if you need one](https://www.online-python.com/)), run the following code to send me a message that only I can decrypt and read. All you have to do is copy and paste the code below and then in the last line of code replace "message" with your message in quotes. Copy the output and email it to me. Note: if you wish to send a longer message (i.e. > two sentences), then break up the message and run the code with parts of the message. For example, a five sentence message should be sent by running the code for each sentence and then sending each of the five outputs in one email. 
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

## Factoring the Product of Two Large Primes
Having created an RSA cryptosystem, whose security depends on the secrecy of two large prime numbers, it is important to be mindful of attacks that may hack the cryptosystem. Here large means greater than 500 bits, which is about 100 digits. The reason only I am able to decrypt messages sent to me is because my private key is of the form N = pq, where p,q are large primes. In general, factoring such a number N is hard, i.e., a computer would take millions of years to figure out one of p or q. Though, there are special cases when N can be factored quickly. 

The first method is Pollard's p-1 algorithm, which can factor N = pq quickly so long as p-1 (or q-1) is a product of small prime numbers. For example, I was able to factor N = 523097775055862871433433884291 almost instantly. This is because the largest prime factor of p-1 = 835667525772396 is 9397. Hence, when building an RSA system, ensure that p-1 and q-1 do not factor into small primes. 

The second factorizing method I implemented is an algorithm that factors N = pq in subexponential time using the quadratic sieve method, based on the difference of squares factorization technique. For 100 bit primes p and q, this algorithm is essentially instant; for 250 bit primes, about 2.5 hours; for 500 bits, over 1,000 years; beyond 500 bits, the time to factor is simply too long, as if 1,000 years weren't already slow enough. Note that this timing was computed based on my own PC's machinery (standard Macbook Pro). 
