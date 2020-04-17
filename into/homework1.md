# Homework1

**tags: Algorithm**

## Handwrite <a id="Handwrite"></a>

### A\)使用虛擬碼\(pseudo code\)寫一個演算法，輸入一個整數n\(n&gt;2\)並判斷n是否為質數\(prime\) <a id="A&#x4F7F;&#x7528;&#x865B;&#x64EC;&#x78BC;pseudo-code&#x5BEB;&#x4E00;&#x500B;&#x6F14;&#x7B97;&#x6CD5;&#xFF0C;&#x8F38;&#x5165;&#x4E00;&#x500B;&#x6574;&#x6578;nngt2&#x4E26;&#x5224;&#x65B7;n&#x662F;&#x5426;&#x70BA;&#x8CEA;&#x6578;prime"></a>

Write an algorithm using the pseudo code to input an integer n and output \(decide\) if n is a prime.\)

```text
Algorithm PrimeTest1(n)

Input: 一個大於2的正整數n
Output: true 或false(表示n是不是質數)

for i = 2 to n-1 do
    if (n%i) = 0 then return false
    return true
```

### B\) 使用虛擬碼\(pseudo code\)寫一個演算法，輸入一個整數n\(n&gt;2\)並輸出小於n的最大因數\(factor\) <a id="B-&#x4F7F;&#x7528;&#x865B;&#x64EC;&#x78BC;pseudo-code&#x5BEB;&#x4E00;&#x500B;&#x6F14;&#x7B97;&#x6CD5;&#xFF0C;&#x8F38;&#x5165;&#x4E00;&#x500B;&#x6574;&#x6578;nngt2&#x4E26;&#x8F38;&#x51FA;&#x5C0F;&#x65BC;n&#x7684;&#x6700;&#x5927;&#x56E0;&#x6578;factor"></a>

\(Write an algorithm using the pseudo code to input an integer n and output the n’s largest factor

```text
Algorithm Factor(n)

Input: 一個大於2的正整數n
Output: 小於n的最大因數

for i=1 to n
    if (n%i) = 0 
    return  i
```

### C\) 使用虛擬碼\(pseudo code\)寫一個演算法，輸入一個整數n\(n&gt;2\)並輸出所有n除了本身以外的正因數\(factor\)總和 <a id="C-&#x4F7F;&#x7528;&#x865B;&#x64EC;&#x78BC;pseudo-code&#x5BEB;&#x4E00;&#x500B;&#x6F14;&#x7B97;&#x6CD5;&#xFF0C;&#x8F38;&#x5165;&#x4E00;&#x500B;&#x6574;&#x6578;nngt2&#x4E26;&#x8F38;&#x51FA;&#x6240;&#x6709;n&#x9664;&#x4E86;&#x672C;&#x8EAB;&#x4EE5;&#x5916;&#x7684;&#x6B63;&#x56E0;&#x6578;factor&#x7E3D;&#x548C;"></a>

\(Write an algorithm using the pseudo code to input an integer n and output the total summation of all n’s factors except n.\)

```text
Algorithm FactorSum(n)

Input: 一個大於2的正整數n
Output: 所有小於n的正因數總和

sum <- 1
for i=2 to n
    if (n%i) = 0 
        sum <- sum+i
return  sum
```

### D\) 使用虛擬碼\(pseudo code\)寫一個演算法，輸入整數n及m\(n&gt;m&gt;2\)，輸出所有比n小並大於m的n的因數\(factor\)總和，若無，此因數則輸出0 <a id="D-&#x4F7F;&#x7528;&#x865B;&#x64EC;&#x78BC;pseudo-code&#x5BEB;&#x4E00;&#x500B;&#x6F14;&#x7B97;&#x6CD5;&#xFF0C;&#x8F38;&#x5165;&#x6574;&#x6578;n&#x53CA;mngtmgt2&#xFF0C;&#x8F38;&#x51FA;&#x6240;&#x6709;&#x6BD4;n&#x5C0F;&#x4E26;&#x5927;&#x65BC;m&#x7684;n&#x7684;&#x56E0;&#x6578;factor&#x7E3D;&#x548C;&#xFF0C;&#x82E5;&#x7121;&#xFF0C;&#x6B64;&#x56E0;&#x6578;&#x5247;&#x8F38;&#x51FA;0"></a>

\(Write an algorithm using the pseudo code to input integers n and m, and output all n’s factors larger than m and less than n.\)

```text
Algorithm FactorSum2(m,n)

Input: 大於2的正整數m,n
Output: 比n小並大於m的n的因數總和

sum <- 0
for i=m+1 to n-1
    if (n%i) = 0 
        sum <- sum+i
return  sum
```

### E\) 使用虛擬瑪\(pseudo code\)寫一個演算法，輸入一個整數n\(n&gt;2\)並判斷n是否為完美數\(perfect number\)。一個完美數是一個正整數，它所有的真因數\(即除了自身以外的因數\)的和，恰好等於它本身。 <a id="E-&#x4F7F;&#x7528;&#x865B;&#x64EC;&#x746A;pseudo-code&#x5BEB;&#x4E00;&#x500B;&#x6F14;&#x7B97;&#x6CD5;&#xFF0C;&#x8F38;&#x5165;&#x4E00;&#x500B;&#x6574;&#x6578;nngt2&#x4E26;&#x5224;&#x65B7;n&#x662F;&#x5426;&#x70BA;&#x5B8C;&#x7F8E;&#x6578;perfect-number&#x3002;&#x4E00;&#x500B;&#x5B8C;&#x7F8E;&#x6578;&#x662F;&#x4E00;&#x500B;&#x6B63;&#x6574;&#x6578;&#xFF0C;&#x5B83;&#x6240;&#x6709;&#x7684;&#x771F;&#x56E0;&#x6578;&#x5373;&#x9664;&#x4E86;&#x81EA;&#x8EAB;&#x4EE5;&#x5916;&#x7684;&#x56E0;&#x6578;&#x7684;&#x548C;&#xFF0C;&#x6070;&#x597D;&#x7B49;&#x65BC;&#x5B83;&#x672C;&#x8EAB;&#x3002;"></a>

\(Write an algorithm using the pseudo code to input an integer n and output \(decide\) if n is a perfect number. Note that a perfect number is a positive integer that is equal to the sum of its proper positive divisors, that is, the sum of its positive divisors excluding the number itself.\)

```text
Algorithm PerfectNumber(n)

Input: 一個大於2的正整數n
Output: true 或false(表示n是不是完美數)

sum <- 0
for i = 1 to n-1 do
    if (n%i) = 0 
        sum <- sum+i
if sum=n then return true
    return false
```

### F\) 使用虛擬瑪\(pseudo code\)寫 一個演算法，輸入一個整數n\(n&gt;0\)並判斷n是否為快樂數\(happy number\) <a id="F-&#x4F7F;&#x7528;&#x865B;&#x64EC;&#x746A;pseudo-code&#x5BEB;-&#x4E00;&#x500B;&#x6F14;&#x7B97;&#x6CD5;&#xFF0C;&#x8F38;&#x5165;&#x4E00;&#x500B;&#x6574;&#x6578;nngt0&#x4E26;&#x5224;&#x65B7;n&#x662F;&#x5426;&#x70BA;&#x5FEB;&#x6A02;&#x6578;happy-number"></a>

\(Write an algorithm to input an integer n and output \(decide\) if n is a happy number.\)  
 註: 快樂數有以下的特性：在給定的進位制下，該數字所有數位\(digits\)的平方和，得到的新數再次求所有數位的平方和，如此重複進 行，最終結果必為1。例 如，以十進位為例：28 → 22+82= 68 → 62+82=100 → 12+02+02=1，因此28是快樂數

```text
Algorithm HappyNumber(n)

Input: 一個大於0的正整數n
Output: true 或false(表示n是不是快樂數)

check ← [n];
r←n;
while True:
	r ← r 按個別位數拆開平方後相加
	if r == 1:
		return true;
	else if r in check:
		return false; 
	check ← check.append(r)
```

## Online <a id="Online"></a>

### Above Average <a id="Above-Average"></a>

[UVa 10370-Above Average](https://onlinejudge.org/index.php?option=onlinejudge&Itemid=8&page=show_problem&problem=1311)

#### Solution <a id="Solution"></a>

[https://github.com/Sharonwg26/UVA/blob/master/10370-Above Average.cpp](https://github.com/Sharonwg26/UVA/blob/master/10370-Above%20Average.cpp)

### Prime factorization <a id="Prime-factorization"></a>

[UVa583-Prime factorization](https://onlinejudge.org/index.php?option=onlinejudge&Itemid=8&category=7&page=show_problem&problem=524)

#### Solution <a id="Solution1"></a>

[https://github.com/Sharonwg26/UVA/blob/master/583-Prime factorization.cpp](https://github.com/Sharonwg26/UVA/blob/master/583-Prime%20factorization.cpp)

### Odd Sum without prime <a id="Odd-Sum-without-prime"></a>

#### Solution <a id="Solution2"></a>

[https://github.com/Sharonwg26/UVA/blob/master/583-Prime factorization.cpp](https://github.com/Sharonwg26/UVA/blob/master/583-Prime%20factorization.cpp)

