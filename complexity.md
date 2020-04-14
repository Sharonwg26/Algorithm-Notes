# 複雜度分析

#### tags: `Algorithm`

## 效能 <a id="&#x6548;&#x80FD;"></a>

演算法執行時使用的資源有:

* 時間資源
* 記憶體資源
* 網路頻寬資源\(當演算法需要透過網路傳輸資料時\)
* 邏輯閘資源\(當演算法使用邏輯閘實作時\)

1. **時間複雜度\(time complexity\)**
   * 最佳狀況\(best case\)時間複雜度: 最少執行步驟數
   * 最差狀況\(worst case\)時間複雜度: 最多執行步驟數
   * 平均狀況\(average case\)時間複雜度: 平均步驟數。
2. **空間複雜度\(space complexity\)**

## 大O漸近記號\(Big-O notation\) <a id="&#x5927;O&#x6F38;&#x8FD1;&#x8A18;&#x865F;Big-O-notation"></a>

### 定義 <a id="&#x5B9A;&#x7FA9;0"></a>

令f\(n\) 與g\(n\) 是由非負整數對應至實數的函數，若存在正實數常數c 和正整數常數n0，使得對所有的n&gt;=n0 而言，f\(n\)≤cg\(n\) 成立，則我們說f\(n\) =O\(g\(n\)\)。  
 

![](https://i.imgur.com/fTpsFOs.png)

### 漸近 <a id="&#x6F38;&#x8FD1;"></a>

* 漸近上界\(Asymptotic Upper Bound\)

![](.gitbook/assets/image%20%285%29.png)

* 漸近下界\(Asymptotic Lower Bound \)

![](.gitbook/assets/image%20%286%29.png)



* 漸近緊界\(Asymptotic Tight Bound \)

![](.gitbook/assets/image%20%287%29.png)

## 降低演算法時間複雜度量級 <a id="&#x964D;&#x4F4E;&#x6F14;&#x7B97;&#x6CD5;&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;&#x91CF;&#x7D1A;"></a>

### 量級比較 <a id="&#x91CF;&#x7D1A;&#x6BD4;&#x8F03;"></a>

某些量級在演算法的輸入規模還不是很大的情況下，演算法時間複雜度的對照數值\(執行步驟數\)就已經相當大了  
   
   
 

![](https://i.imgur.com/bSROnzz.png)

![](https://i.imgur.com/KUi9ww1.png)

![](https://i.imgur.com/lgHWEDQ.png)

## 費伯納西數列\(Fibonacci series\) <a id="&#x8CBB;&#x4F2F;&#x7D0D;&#x897F;&#x6578;&#x5217;Fibonacci-series"></a>

### 定義 <a id="&#x5B9A;&#x7FA9;"></a>

* F1 = F2 = 1
* Fn = Fn-1 + Fn-2
* 1, 1, 2, 3, 5, 8, 13, 21, 34, …

### 費伯納西數列演算法 <a id="&#x8CBB;&#x4F2F;&#x7D0D;&#x897F;&#x6578;&#x5217;&#x6F14;&#x7B97;&#x6CD5;"></a>

```cpp
Algorithm Fibonacci(n)

Input: 正整數n
Output: 費伯納西數列第n項

if (n=1 or n=2) then
  return 1
else 
  a<-1;b<-1
  for i<-3 to n do 
    c<-a+b
    a<-b
    b<-c
  return c
```

#### 多項式時間\(polynomial time algorithm\) <a id="&#x591A;&#x9805;&#x5F0F;&#x6642;&#x9593;polynomial-time-algorithm"></a>

**Time Complexity: O\(n\)**

### 遞迴費伯納西數列演算法 <a id="&#x905E;&#x8FF4;&#x8CBB;&#x4F2F;&#x7D0D;&#x897F;&#x6578;&#x5217;&#x6F14;&#x7B97;&#x6CD5;"></a>

```cpp
Algorithm RecursiveFibonacci(n)

Input: 正整數n
Output: 費伯納西數列第n項

if (n=1 or n=2) then
  return 1
else 
  a <- RecursiveFibonacci(n-1)
  b <- RecursiveFibonacci(n-2)
  return a+b
```

#### 指數時間及\(exponential time algorithm\) <a id="&#x6307;&#x6578;&#x6642;&#x9593;&#x53CA;exponential-time-algorithm"></a>

T\(1\)=T\(2\)=1  
 T\(n\)=T\(n-1\)+T\(n-2\)+1&lt;=2T\(n-1\)+1  
 =2\(2T\(n-2\)+1\)+1  
 =4\(2T\(n-3\)+1\)+1+2=…  
 =2kT\(n-k\)+\(1+2+…+2k-1\)= 2kT\(n-k\)+\(2k-1\)

令n-k=1，則代入k=n-1，我們可得  
 T\(n\)&lt;=2n-1+\(2n-1-1\)&lt;=2n for n&gt;=3

**Time Complexity: O\(2n\)**

## 氣泡排序法\(bubble sort\) <a id="&#x6C23;&#x6CE1;&#x6392;&#x5E8F;&#x6CD5;bubble-sort"></a>

氣泡排序\(bubble sort\)演算法又稱為下沉\(sinking\)排序演算法或交換\(exchange\)排序演算法。

### 氣泡排序演算法 <a id="&#x6C23;&#x6CE1;&#x6392;&#x5E8F;&#x6F14;&#x7B97;&#x6CD5;"></a>

```cpp
Algorithm BubbleSort(A,n)

Input: n個整數的array A
Output: A (由小到大排)

for i=n-1 to 1 do
    for j=0 to i-1 do
        if A[j]>A[j+1] then
            swap(A[j], A[j+1])
return A
```

![](https://i.imgur.com/YR0TvtD.png)  
 當一個排序演算法能夠讓具有相同值的元素維持原來的相對位置時，我們稱這種排序演算法為穩定\(stable\)排序演算法。

不需要額外記憶體空間的排序演算法稱為就地\(in place\)演算法。

### 時間複雜度分析 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;&#x5206;&#x6790;0"></a>

一共需要n-1個回合才能完成排序工作

* 第一個回合需要n-1次比較
* 第二個回合需要n-2次比較
* …
* 第n-1個回合需要1次比較  對所有狀況而言,時間複雜度為：**O\(n2\)**

## 插入排序法\(insertion sort\) <a id="&#x63D2;&#x5165;&#x6392;&#x5E8F;&#x6CD5;insertion-sort"></a>

### 插入排序演算法 <a id="&#x63D2;&#x5165;&#x6392;&#x5E8F;&#x6F14;&#x7B97;&#x6CD5;"></a>

```cpp
Algorithm InsertionSort(A,n)

Input: n個整數的array A
Output: A (由小到大排)

for i=1 to n-1 do
    j=i-1
    t=A[i] //暫存A[i]
    while (t<A[j] and j>=0) do
        A[j+1] = A[j]
        j=j-1
    A[j+1]=t
return A
```

![](https://i.imgur.com/arnxCmO.png)

  
 插入排序演算法也是一個穩定\(stable\)排序演算法  
 排序演算法不需要額外記憶體空間,所以也是一個就地 \(in place\) 演算法

### 時間複雜度分析 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;&#x5206;&#x6790;"></a>

* A\[i\] 是所有i+1個資料中最大的資料的機率為1/\(i+1\)\(這個狀況下mi = 0\)
* A\[i\] 是所有i+1 個資料中第二大的資料的機率也為1/\(i+1\)\(這個狀況下mi=1\)
* …
* A\[i\] 是所有i+1個資料中最小的\(第i+1大的\) 資料的機率也為1/\(i+1\)\(這個狀況下mi = i\)
*  以期望值來估算，我們有
  * mi = \(0+1+…+i\)/\(i+1\) = i\(i+1\)/2/\(i+1\) = i/2。
* 因此M =Σn-1i=1\(2+i/2\) = 2\(n-1\)+n\(n-1\)/4 = O\(n2\)

### 比較 <a id="&#x6BD4;&#x8F03;"></a>

![](https://i.imgur.com/abw0DYq.png)

