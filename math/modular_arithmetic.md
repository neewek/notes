## Fermat’s little theorem 

P = an integer Prime number    
 a = an integer which is not multiple of P  
 Let a = 2 and P = 17 
 
 According to Fermat's little theorem 
  2^(17 - 1)     ≡ 1 mod(17)    
 we got  65536 % 17 ≡ 1   
 that mean (65536-1) is an multiple of 17 

## Modular Inverting

Looking again at Fermat's little theorem...    
if p is prime, for every integer a:    
        pow(a, p) = a mod p    
and, if p is prime and a is an integer coprime with p:    
        pow(a, p-1) = 1 mod p    
We can do some magic like this:    
Note: i'll use math notation, so a^b means pow(a,b)    
            a^(p-1) = 1 (mod p)    
            a^(p-1) * a^-1 = a^-1 (mod p)    
            a^(p-2) * a * a^-1 = a^-1 (mod p)    
            a^(p-2) * 1 = a^-1 (mod p)    
So finally we have:    
        a^(p-2) = a^-1 (mod p)    
So, doing a^(p-2) and then (mod p) we can achieve    
our result    


## Quadratic Residues
We can take the integer a = 11 and calculate a2 = 5 mod 29.

As a = 11, a^2 = 5, we say the square root of 5 is 11.

We say that an integer x is a Quadratic Residue if there exists an a such that a2 = x mod p. If there is no such solution, then the integer is a Quadratic Non-Residue.

If a^2 = x then (-a)^2 = x. So if x is a quadratic residue in some finite field, then there are always two solutions for a.

## Legendre Symbol

Legendre's Symbol: (a / p) ≡ a^((p-1)/2) mod p obeys:

(a / p) = 1 if a is a quadratic residue and a ≢ 0 mod p    
(a / p) = -1 if a is a quadratic non-residue mod p    
(a / p) = 0 if a ≡ 0 mod p     

Which means given any integer a, calculating pow(a,(p-1)/2,p) is enough to determine if a is a quadratic residue.
