# Shamir Secret Sharing or Packed Shamir Secret Sharing

Shamir Secret Sharing（Shamir SS）是一种秘密共享方案，由Adi Shamir在1979年提出。其主要思想是将一个秘密分成多个份额（shares），并分发给参与者，使得只有当收集到一定数量的份额时，才能恢复出原始的秘密。具体来说，给定一个秘密s，可以选择一个足够高阶的多项式f(x)，使得f(0)=s，然后为每个参与者分配一个不同的x值，并计算相应的f(x) 作为其份额。通过拉格朗日插值，多数参与者可以联合恢复秘密。

Packed Shamir Secret Sharing（Packed Shamir SS）是Shamir Secret Sharing的一个变种，它通过打包多个秘密在同一个多项式中来提高效率。在PSSS中，不是仅仅将一个秘密嵌入到多项式的常数项中，而是通过不同的系数嵌入多个秘密。例如，如果有多个秘密s1, s2, ..., sm，可以构造一个多项式f(x)=s1 + s2⋅x + s3⋅x^2 + ... + sm ⋅x^m−1 ，然后按照Shamir的方式分发份额。这样，通过收集足够多的份额，参与者可以同时恢复多个秘密。

## 1. Shamir SS和Packed Shamir SS学习路线





## 2. Shamir SS和Packed Shamir SS论文




