# Signature
* RSA
* ElGamal
* Schnorr
* DSA
---
## RSA
public key: $PR = (n,e)$
private key: $PU = (n,d)$

choose $n = p*q$ ,$gcd\,(e ,(p-1)(q-1))$ 
$d = e^{-1}\,mod\,(p-1)(q-1)$


### Sign

1. compute $m = H(M)$, $s = m^d\,mod\,n$
 
 $(M,s)$ is signature

### verify
1. compute $m = H(M)$, $m' = s^e\,mod\,n$

pass if $m=m'$

---
## Elgamal

public key: $PR = (q,α,X)$
private key: $PU = (q,α,Y)$

choose $α$ is a primitive root of $q$ , $1<X<q-1$
$Y = α^X mod q$
### Sign

1. compute $m = H(M)$, choose a $1<k<q$ and $gcd\,(k,q-1)=1$
2. compute $s_1 = α^k\,mod\,q$ and $s_2 = k^{-1}\,(m-X*s_1)\, mod\,({\color{red}{q-1}})$
    
$(M,s_1,s_2)$ is signature

### verify
1. compute $m = H(M)$

pass if $α^m\equiv Y^{s_{1}}s_{1}^{s_{2}}$


---



