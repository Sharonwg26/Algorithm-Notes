# 分治演算法

**tags: Algorithm**

## 概念 <a id="&#x6982;&#x5FF5;"></a>

分治\(divide and conquer\)演算法使用分治解題策略解決問題。

* 分割階段  如果問題規模很小，就直接解決此問題；否則，將原本的問題**分割\(divide\)成2個或多個子問題\(subproblem\)**。
* 克服階段  用相同的演算法遞**迴地\(recirsively\)解決或克服\(conquer\)** 所有的子問題。
* 合併階段  **合併\(merge\)** 所有子問題的解答成為原本問題的解答。

## 合併排序演算法\(Merge sort\) <a id="&#x5408;&#x4F75;&#x6392;&#x5E8F;&#x6F14;&#x7B97;&#x6CD5;Merge-sort"></a>

### 步驟 <a id="&#x6B65;&#x9A5F;"></a>

假設我們要使用合併排序演算法來將陣列A中的n個元素或資料\(索引為0,…,n−1\) 依照其值以由小而大的次序排列

1. 分割: 若陣列A 只有一個元素，代表陣列已排序完成；否則將陣列分割成兩個大小相等的子陣列。
2. 克服: 遞迴地排序兩個子陣列。
3. 合併: 最後合併兩個已完成排序的子陣列，即可完成原來陣列的排序。

### Algorithm <a id="Algorithm"></a>

### Ex. <a id="Ex"></a>

![](https://i.imgur.com/7NkVEB3.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;"></a>

T\(n\) = 2T\(n/2\) + n = 2\(2T\(n/4\)+\(n/2\)\) + n = 4T\(n/4\) + n + n  
 = 4\(2T\(n/8\)+\(n/4\)\) + 2n= 8T\(n/8\) + 3n = … = 2kT\(n/2k\) + kn  
 假設n = 2k，則k = log2&lt;/sub2&gt;n  
 T\(n\) = nlogn+2k=nlogn+n=O\(nlogn\)

* Best Case：Ο\(n log n\)
* Worst Case：Ο\(n log n\)
* Average Case：Ο\(n log n\)

### 空間複雜度 <a id="&#x7A7A;&#x9593;&#x8907;&#x96DC;&#x5EA6;"></a>

每次都替子數列申請新的記憶體空間，Ο\(n\)

## 快速排序演算法\(Quick sort\) <a id="&#x5FEB;&#x901F;&#x6392;&#x5E8F;&#x6F14;&#x7B97;&#x6CD5;Quick-sort"></a>

### 特性 <a id="&#x7279;&#x6027;"></a>

* 實作簡單，速度快。
* 不穩定排序：排序後，相同鍵值的元素相對位置可能改變。
* 非原地排序：除了資料本身，仍需額外花費儲存空間來排序。
* 分治演算法：將主問題化作數個子問題，各個擊破。

### 步驟 <a id="&#x6B65;&#x9A5F;1"></a>

Quicksort 是一個分治演算法（divide-and-conquer），不斷遞迴下列三個步驟：

1. 分割  選一個元素p當作**中樞\(pivot\)** 元素將陣列分割為2部份：**SP及LP**，其中SP \(smaller part\)包含所有小於p的元素；而LP\(larger part\)則包含所有大於或等於p的元素。
2. 克服  完成陣列**分割\(partition\)** 之後，快速排序演算法持續遞迴地\(recursively\)進行SP部份與LP部份的元素排序。
3. 合併  最後再將SP、p及LP合併即可完成排序。

### Algorithm <a id="Algorithm1"></a>

![](https://i.imgur.com/gSHk5gV.png)

### Ex. <a id="Ex1"></a>

![](https://i.imgur.com/1Rj9457.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;1"></a>

* Bast Case  每次 pivot 都可以順利選到序列的中位數（median）  T\(n\)=n+2T\(n/2\)=O\(nlogn\)
* Worst Case  最差的分割序列狀況發生在挑選的 pivot 總是最大或最小值  T\(n\)=\(n+2\)\(n-1\)/2=O\(n2&lt;/sup\)&gt;\)
  * Average Case : T\(n\)=2cnHn-c\(n+1\)=O\(nlogn\)

### 空間複雜度 <a id="&#x7A7A;&#x9593;&#x8907;&#x96DC;&#x5EA6;1"></a>

分割序列步驟需 O\(1\)的空間複雜度

* Best Case： Ο\(log n\) 遞迴呼叫的深度為log n
* Worst Case：Ο\(n\) 遞迴呼叫的深度為n-1

## 排序演算法比較 <a id="&#x6392;&#x5E8F;&#x6F14;&#x7B97;&#x6CD5;&#x6BD4;&#x8F03;"></a>

![](https://i.imgur.com/MZUzYeJ.png)

## 缺陷棋盤填滿演算法 <a id="&#x7F3A;&#x9677;&#x68CB;&#x76E4;&#x586B;&#x6EFF;&#x6F14;&#x7B97;&#x6CD5;"></a>

### Definition <a id="Definition"></a>

*  一個棋盤是一個 **nxn 方格\(grid\)**，具有n2個單格\(cell\)，其中n&gt;2而且n是2的幂

![](.gitbook/assets/image%20%2810%29.png)

* 缺陷棋盤是有一單格\(cell\)無法使用的棋盤。

![](.gitbook/assets/image%20%288%29.png)

* 三格骨牌\(Triomino\)為一 **L型骨牌** ，可填滿一棋盤上的3個單格。

![](.gitbook/assets/image%20%289%29.png)

### Problem <a id="Problem"></a>

放置\(n2-1\)/3個三格骨牌在nxn缺陷棋盤上，使得全部\(n2–1\)個非缺陷單格都被填滿。  
 

![](https://i.imgur.com/xBlbG01.png)

### Algorithm <a id="Algorithm2"></a>

```text
Algorithm 缺陷棋盤填滿演算法

Input: n*n缺陷棋盤， n>2而且n是2的幂
Output: 以三格骨牌填滿的n*n缺陷棋盤

步驟1: 若n=2，則旋轉一個三格骨牌直接填滿缺陷棋盤，回傳此2*2缺陷棋盤並結束。
步驟2: 將缺陷棋盤分為3個(n/2)*(n/2)棋盤及1個(n/2)*(n/2)缺陷棋盤，旋轉一個三格骨牌填滿3個棋盤中相鄰的單格，可使3個棋盤成為缺陷棋盤，我們可得4個(n/2)*(n/2)缺陷棋盤。
步驟3: 遞迴地使用缺陷棋盤填滿演算法以三格骨牌填滿步驟2的4個(n/2)*(n/2)缺陷棋盤，回傳原始n*n缺陷棋盤並結束。
```

### Ex <a id="Ev"></a>

* 將8x8缺陷棋盤分割成4個更小的4x4棋盤。
* 其中1個為4 x 4缺陷棋盤，其他3個為一般 4 x 4 棋盤

  ![](https://i.imgur.com/N7Wt8dI.png)

* 放置1個三格骨牌在3個4x4正常棋盤的相鄰單格，讓他們也變成缺陷棋盤。
* 再以遞迴方式填滿4個缺陷4x4棋盤。

  ![](https://i.imgur.com/xXeUk9o.png)

* 以遞迴方式填滿右上角之缺陷4 x 4棋盤。

  ![](https://i.imgur.com/cDpZCfH.png)

## 二維求秩演算法\(\(2D rank finding\)\) <a id="&#x4E8C;&#x7DAD;&#x6C42;&#x79E9;&#x6F14;&#x7B97;&#x6CD5;2D-rank-finding"></a>

### Definition <a id="Definition1"></a>

* Dominate  令A=\(ax,ay\),B=\(bx,by\)為二維XY平面上的點，則我們說A支配\(dominate\)B,若且唯若 ax&gt;bx且ay&gt;by。
* Rank  給定一個由二維平面點所構成的集合S，點A之秩\(rank\)定義為集合S中有多少個點被A所支配。  

![](https://i.imgur.com/wUcqYL3.png)

### Algorithm <a id="Algorithm3"></a>

```text
Algorithm 二維求秩演算法

Input: n個二維平面點所構成的集合S，n>=1
Output: 集合S中所有點的秩(rank)

步驟1: 若n=1，則回傳S中唯一一個點的秩為0並結束。
步驟2: 找出所有點的X軸中位數(median)畫出垂直於X軸的直線L，將S中的點分為二個集合SL與SR。
步驟3: 遞迴地使用二維求秩演算法分別求出SL與SR中所有點的秩。
步驟4: 根據Y軸值排序所有在S(S=SL U SR)中的點，依序由小而大掃描所有點，求出每一個在SR的點i排在多少在SL的點的後面(記為updatei)，並將點i的秩加上updatei，最後回傳S中所有點的秩。
```

### Ex. <a id="Ex2"></a>

![](https://i.imgur.com/VPGUBtO.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;2"></a>

T\(n\) = 2T\(n/2\)+c1nlogn+c2nlogn  
 = 2T\(n/2\)+cnlogn= 2\(2T\(n/4\)+c\(n/2\)log\(n/2\)\)+cnlogn  
 =4T\(n/4\)+cn log\(n/2\)+cnlogn=nT\(1\)+cn\(logn+log\(n/2\)+log\(n/4\)+…+log2\)  
 &lt;= nT\(1\)+cn\(logn\(logn+log2\)\)/2\(其中T\(1\)=1\)  
 = **O\(n log^2n\)**

## 二維極大點演算法\(\(2D maxima finding\)\) <a id="&#x4E8C;&#x7DAD;&#x6975;&#x5927;&#x9EDE;&#x6F14;&#x7B97;&#x6CD5;2D-maxima-finding"></a>

### Definition <a id="Definition2"></a>

* 如果一個點不被任何其他點所支配，我們就稱此點不被支配\(non-dominated\)，或稱此點為極大點\(maxima\)。
* **不只一個**  ![](https://i.imgur.com/CqpBbfY.png)

### Algorithm <a id="Algorithm4"></a>

```text
Algorithm 二維極大點演算法

Input: n個二維平面點所構成的集合S，n>=1
Output: 集合S中所有的極大點(maxima)

步驟1: 若n=1，則回傳S中唯一一個點為極大點並結束。
步驟2: 找出所有點的X軸中位數(median)畫出垂直於X軸的直線L，將S中的點分為二個集合SL與SR。
步驟3: 遞迴地使用二維極大點演算法分別求出SL與SR中所有的極大點。
步驟4: 在SR的極大點中找出最大的Y軸值y*。 對每個在SL中的極大點，如果該點的Y軸值小於y*，則標示該點為不是極大點。回傳SR中的極大點和SL中未被標示的極大點。
```

### Ex. <a id="Ex3"></a>

![](https://i.imgur.com/RAo5nyK.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;3"></a>

* 排序演算法  T\(n\)=2T\(n/2\)+c1nlogn+c2n=2T\(n/2\)+cn logn  =2\(2T\(n/4\)+c\(n/2\)log\(n/2\)\)+cnlogn=4T\(n/4\)+cnlog\(n/2\)+cnlogn  = nT\(1\) + cn\(log n + log \(n/2\)+ log \(n/4\) +…+ log 2\)  = nT\(1\) + cn \(log n \(log n+ log 2\)\)/2 \(其中T\(1\)=1\)  = **O\(nlog^2n\)**
* 刪尋演算法  T\(n\)=2T\(n/2\)+c1n+c2n=2T\(n/2\)+cn  = 2\(2T\(n/4\)+c\(n/2\)\)+cn=4T\(n/4\)+cn+cn  = nT\(1\)+cn+cn+…+cn \(其中總共log n個cn\)= nT\(1\)+cnlogn \(其中T\(1\)=1\)  = **O\(nlogn\)**

## 最近二維點對演算法\(Closest pair of 2D points\) <a id="&#x6700;&#x8FD1;&#x4E8C;&#x7DAD;&#x9EDE;&#x5C0D;&#x6F14;&#x7B97;&#x6CD5;Closest-pair-of-2D-points"></a>

### Algorithm <a id="Algorithm5"></a>

```text
Algorithm 最近二維點對演算法

Input: n個二維平面點所構成的集合S，n>=2
Output: 集合S中距離最近的二個點的距離d

步驟1: 根據X軸值與Y軸值來事先排序S中的點。
步驟2: 若n=2，則回傳S中二點的距離d並結束。
步驟3: 找出所有點的X軸中位數(median)m畫出垂直於X軸的直線L，將S中的點分為二個集合SL與SR。
步驟4: 遞迴地使用二維點對演算法分別求出SL與SR中最近二維點對的距離dL與dR，且令 d = min(dL, dR)。 
步驟5: 將X軸值介於m-d與m+d的所有點的Y軸值投射至直線L上。針對於每個X軸值落在範圍介於m-d與m之間的點p，以yp記錄其Y軸值，並尋找所有X軸值落在範圍介於m與m+d之間，且Y軸值介於yP+d 與 yP-d之間的所有點，若存在一點與p之距離為小於d的d’，則令d=d’。回傳d並結束執行。
```

### Ex. <a id="Ex4"></a>

![](https://i.imgur.com/BHkMlb6.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;4"></a>

步驟 1: c1nlogn \(事先排序\)  
 步驟 2~5:![](https://i.imgur.com/WetTMGq.png)  
 T’\(n\) = c2nlog n  
 T\(n\)=c1nlogn+c2nlogn=**O\(nlogn\)**

## 最大連續子序列和\(Maximum Contiguous Subsequence Sum, MCSS\) <a id="&#x6700;&#x5927;&#x9023;&#x7E8C;&#x5B50;&#x5E8F;&#x5217;&#x548C;Maximum-Contiguous-Subsequence-Sum-MCSS"></a>

### Problem <a id="Problem1"></a>

給定一個包含n個正或負整數的序列S=s1, s2,…, sn，找出S的連續子序列，使得子序列中的元素總和最大。

### Algorithm <a id="Algorithm6"></a>

* 窮舉演算法1 \(Exhaustive Algorithm 1\)

```cpp
Algorithm 最大子序列和窮舉演算法1

Input: 序列S=s1, s2,…, sn
Output: 最大連續子序列sl,…,sr及其和m

m <- -00   
for i<- 1 to n do
  for j<- i to n do
     t<- 0
     for k<- i to j do 
        t<- t+sk
     if t>m then 
        m<-t;l<-i;r<-j
return l, r, m
```

* 窮舉演算法2 \(Exhaustive Algorithm 2\)

```cpp
Algorithm 最大子序列和窮舉演算法2

Input: 序列S=s1, s2,…, sn
Output:最大連續子序列sl,…,sr及其和m

m <- -00    
for i<-1 to n do
  t<-0
  for j<-i to n do
     t<-t+sj
     if t>m then 
        m=t;l<-i;r<-j
return l, r, m
```

* 分治演算法  

![](https://i.imgur.com/VJKVHVg.png)

## Fast Fourier Transform \(FFT\) <a id="Fast-Fourier-Transform-FFT"></a>

* FF is to an electrical signal what an optical prism is to light.
* FF is used to move a function from amplitude as a function of time to amplitude as a function of frequency

### Fourier series <a id="Fourier-series"></a>

![](https://i.imgur.com/MelHjeZ.png)

#### E.G.: Square Wave <a id="EG-Square-Wave"></a>

![](https://i.imgur.com/Ai1EzIN.png)

### Discrete Fourier transform\(DFT\) <a id="Discrete-Fourier-transformDFT"></a>

Given a0, a1, …, an-1 , compute![](https://i.imgur.com/FAEJPTa.png)

### Inverse DFT <a id="Inverse-DFT"></a>

![](https://i.imgur.com/wCX3doz.png)

* DFT can be computed in O\(n2\) time by a straightforward method.
* DFT can be solved by the divide-and-conquer strategy \(FFT\) in **O\(nlogn\)** time.

### Algorithm  <a id="Algorith"></a>

![](https://i.imgur.com/tqOV4xL.png)

![](https://i.imgur.com/fMmMxGG.png)

![](https://i.imgur.com/gEh7jvx.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;5"></a>

T\(n\) = 2T\(n/2\) + O\(n\)= O\(nlogn\)

