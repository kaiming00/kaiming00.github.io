---
title:  "RSA Encryption Proof"
mathjax: true
layout: post
categories: media
---
## RSA Algorithm

Select two large prime numbers $$p$$ and $$q$$ ($$p\ne q$$), and let $$n=pq$$, $$\phi(n)=(p-1)(q-1)$$. Select the positive integer $$w$$ such that $$w$$ is a coprime with $$\phi(n)$$.  Let $$d$$ be the modular inverse of $$w$$ modulo, namely $$dw\equiv 1 (\mathrm{mod}\ \phi(n))$$.

- Encryption. $$c=E(m)=m^w \mathrm{mod}\ n$$,
- Decrypton. $$D(c)=c^d \mathrm{mod}\ n$$.

Where the encryption key $$(w,n)$$ are public, and $$(p,q,\phi(n),d)$$ are private.

## Proof

The following proves that the decryption algorithm is correct, namely $$m=c^d \mathrm{mod}\ n$$. Since $$m<  n$$, we only need to prove that $$c^d \equiv m (\mathrm{mod} \ n)$$, that is $$m^{dw}=m(\mathrm{mod}\ n)$$. Since $$dw\equiv 1(\mathrm{mod}\  \phi(n))$$, there exists an integer $$k$$ such that $$dw=k\phi(n)+1$$. Two possibilities are dicuss below.

1. $$m$$ is coprime with $$n$$. According to  Euler's theorem.
   
$$m^{\phi(n)}\equiv 1(\mathrm{mod} \ n),$$

Thus, we can obtain.

$$m^{dw}=m^{k\phi(n)+1}=m (\mathrm{mod} \ n)$$.

3. $$m$$ is not coprime with $$n$$, since $$m< n$$, $$n=pq$$, $$p$$ and $$q$$ are prime numbers and $$p\ne q$$, so $$m$$ must have one of $$p$$ or $$q$$ as a factor, and only one of them. Suppose $$m=cp$$ and $$q$$ does not divide $$m$$. By Fermat's little theorem
   
$$m^{q-1} \equiv 1 (\mathrm{mod} \ q).$$

Therefore

$$m^{k\phi(n)}\equiv m^{k(p-1)(q-1)}\equiv 1^{k(p-1)}=1 (\mathrm{mod} \ q).$$

Thus, there exists an integer $h$ such that

$$m^{k\phi(n)+1}=hq+1,$$

Mutiply both side by $$m$$, and notice that $$m=cp$$,

$$m^{k\phi(n)+1}=hcpq+m=hcn+m,$$

It is proven that,

$$m^{k\phi(n)+1}=m (\mathrm{mod}\ n),$$

Namely,

$$m^{dw}=m (\mathrm{mod} \ n).$$
