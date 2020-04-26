# 刪尋演算法

#### tags: `Algorithm` <a id="tags-Algorithm"></a>

## 步驟 <a id="&#x6B65;&#x9A5F;0"></a>

1. 使用多次迭代\(iteration\)解決問題
2. 在每次迭代都刪除\(prune\)輸入資料的一部份\(假設為f部份, 0&lt;f&lt;1\)，而後採用相同的演算法遞迴地\(recursively\)從剩餘資料中搜尋\(search\)出解答。
3. 而經過幾次迭代後，輸入資料的規模將會小到足以讓問題使用常數時間複雜度直接解決。

## 二元搜尋演算法\(Binary Search\) <a id="&#x4E8C;&#x5143;&#x641C;&#x5C0B;&#x6F14;&#x7B97;&#x6CD5;Binary-Search"></a>

可視為刪尋\(prune-and-search\)演算法，在每一個迭代的比較之後，會有一半的資料被**刪除\(prune away\)** 。亦可視為分治\(divide-and-conquer\)演算法

### Algorithm <a id="Algorithm0"></a>

![](https://i.imgur.com/NvhX2rw.png)

### Ex. <a id="Ex0"></a>

![](https://i.imgur.com/Enac2U8.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;0"></a>

![](https://i.imgur.com/q9YxtJo.png)  
 Let n/2^k=1,so n=2^k,and k=logn  
 T\(n\) = T\(1\)+k = 1+k =O\(log n\)

## 選取與中位數演算法 <a id="&#x9078;&#x53D6;&#x8207;&#x4E2D;&#x4F4D;&#x6578;&#x6F14;&#x7B97;&#x6CD5;"></a>

### 選取問題\(Selection problem\) <a id="&#x9078;&#x53D6;&#x554F;&#x984C;Selection-problem"></a>

1. 給定一個擁有n個元素的集合S，欲尋找S中第k小的元素。
2. 給定一個擁有n個元素的集合S，中位數\(median\) 問題欲尋找S中第 小的元素。

### 步驟 <a id="&#x6B65;&#x9A5F;"></a>

1. 令S={a1, a2, …, an}
2. 找出 p屬於S, 用p將S分割成3個子集合S1,S2,S3:
3. S1= ai \| ai &lt; p,1&lt;=i&lt;=n
4. S2= ai \| ai = p , 1&lt;=i&lt;=n
5. S3= ai \| ai &gt; p , 1&lt;=i&lt;=n
6. 若 \|S1\|&gt;k，代表第k小的元素在S1中，我們可刪除S2和S3。
7. 否則，若 \|S1\|+\|S2\|&gt;k，則p就是S中第k小的元素。
8. 否則，代表第k小的元素是S3中第\(k -\|S1\|-\|S2\|\)小的元素，我們可刪除S1和S2。  

![](https://i.imgur.com/YSFS5Qx.png)

### Algorithm <a id="Algorithm0"></a>

```text
Algorithm 刪尋選取演算法


Input: 一個有n個元素的集合S，以及整數k。
Output: 集合S內第k小的元素。

步驟0: 若|S|<=10，則直接排序S中元素並輸出第k個元素後結束執行。
步驟1: 將S分割為大小為5的子集合，共有[n/5]個。若n不能被5整除，則在最後一個子集合內增加值為的元素，使其補滿5個元素。
步驟2: 直接排序每個子集合內的元素。
步驟3: 從每個子集合內找出中位數，再遞迴地從找出的中位數中找出中位數(也就是找出所有子集合中位數的中位數)，令其為p。
步驟4: 將S分成 S1, S2, S3三個子集合，每個子集合分別包含小於、等於、大於p的元素。
步驟5: 若 |S1|>= k, 則捨棄 S2 與 S3 並且在下一次迭代中從S1 內找出第k小的元素為輸出(令S=S1；跳回步驟1)；否則，若|S1| + |S2|>= k 則輸出p為S內第K小的元素; 否則，令 k = k - |S1| - |S2|，在下一次的迭代中從S3 找出第 k’ 小的元素為輸出(令S=S3；k=k’；跳回步驟1) 。
```

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;0"></a>

* 步驟時間複雜度:
  * 步驟1: O\(n\)
  * 步驟2: O\(n\)
  * 步驟3: T\(n/5\)
  * 步驟4: O\(n\)
  * 步驟5: T\(3n/4\)
* 總時間複雜度: T\(n\) = T\(3n/4\)+T\(n/5\)+cn

![](https://i.imgur.com/Fn2hJPG.png)

## 限制的一圓心演算法 <a id="&#x9650;&#x5236;&#x7684;&#x4E00;&#x5713;&#x5FC3;&#x6F14;&#x7B97;&#x6CD5;"></a>

### 1-center problem <a id="1-center-problem"></a>

給定n個平面點，找出一個最小可覆蓋此n個點的圓。  
 ![](https://i.imgur.com/8Qk8e8w.png)

* 基本暴力\(brute force\)法: 列出每一個可能的候選圓並檢查其是否能夠覆蓋所有的點:
  * 任取三點做圓: 時間複雜度O\(n^3\)
  * 任取二點為直徑做圓: 時間時間複雜度O\(n^2\)
  * 針對一個候選圓檢查是否能夠覆蓋所有的點: O\(n\)
* 總時間複雜度: O\(n4\)

### Constrained 1-center problem <a id="Constrained-1-center-problem"></a>

給定n個平面點，找出一個最小可覆蓋此n個點的圓，但是限制圓心r必須座落在y=c\(例如y=0\)的直線上  
 ![](https://i.imgur.com/oq5wJN0.png)

### Algorithm <a id="Algorithm0"></a>

```text
Algorithm 限制的一圓心演算法

Input: n個平面點p1, p2, …, pn與直線y = c, n>2
Output: 圓心在y=c上可覆蓋p1, p2, …, pn的最小圓

步驟1: 若n<=2，則直接找出圓。
步驟2: 若n為偶數，則形成[n/2]個點對(p1, p2), …,(pn-1, pn)；反之，若n為奇數，則形成[n/2]個點對(p1, p2), …, (pn-2, pn-1), (pn, p1)。
步驟3: 對於每一點對(pi, pi+1)，做出其中垂線Lij，交於直線y=c，以找出一個在直線y=c上的等距點qi,i+1，使得d(pi, qi,i+1)= d(pi+1, qi,i+1)，其中d(p, q)代表點p與點q的距離。
步驟4: 找出所有等距點的X座標值的中位數xm，令對應的等距點為qm=(xm, c)。
步驟5: 以qm來評估最佳解圓心q*在y=c的位置: 計算每個pi與點qm的距離，並令pj為距qm最遠的點。令qj表示pj 在直線 y=c上的投影點，若 qj 落在qm左側(右側)，則最佳解圓心q* 亦必定會落在qm的左側(右側)。
步驟6: 若q*落在qm的左側，則針對每個X軸值大於xm的等距點qi,i+1，刪除其對應點pi與pi+1中靠qm較近的點;反之，若q*落在qm的右側，則針對每個X軸值小於xm的等距點qi,i+1，刪除其對應點pi與pi+1中靠qm較近的點。
步驟7: 跳到步驟1繼續執行。 
```

![](https://i.imgur.com/6nw6INt.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;0"></a>

T\(n\)=T\(3n/4\)+cn=……=O\(n\)

## 簡化的二變數線性規劃演算法\(Simplified two-variable linear programming\) <a id="&#x7C21;&#x5316;&#x7684;&#x4E8C;&#x8B8A;&#x6578;&#x7DDA;&#x6027;&#x898F;&#x5283;&#x6F14;&#x7B97;&#x6CD5;Simplified-two-variable-linear-programming"></a>

![](https://i.imgur.com/23jNzIa.png)

### 概念 <a id="&#x6982;&#x5FF5;"></a>

* 線性規劃 \(linear programming, LP\)問題: 目標函數\(objective function\)和限制條件\(constraints\)都是線性\(變數都是一次方\)的最佳化\(optimization\)問題。是多項式時間複雜度\(polynomial time complexity\)問題。
* 要求所有變數都限定為整數的線性規劃問題叫做整數線性規劃 \(integer linear programming, ILP\)或整數規劃\(integer programming, IP\)問題。是NP困難\(NP-hard\)問題。
* 0/1 整數規劃\(0/1 integer linear programming, 0/1 ILP\)是整數線性規劃的特殊情況，要求所有的變數都要是0或1。是NP困難\(NP-hard\)問題。

### Problem <a id="Problem"></a>

* 給定n個限制條件，其中第i個限制條件為
  * **y&gt;= kix + ti** , i=1,2,…,n \(ki為**斜率** ，ti為**y截距** \)
  * 欲最小化目標函數y

### Ex. <a id="Ex"></a>

![](https://i.imgur.com/7sKXm5x.png)

### Algorithm <a id="Algorithm"></a>

![](https://i.imgur.com/BHZ9duH.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;"></a>

總共有 \[n/2\]對限制式，因此有\[n/4\]個限制式在每一次的迭代中被刪除  
 T\(n\) = T\(3n/4\)+cn = O\(n\)

