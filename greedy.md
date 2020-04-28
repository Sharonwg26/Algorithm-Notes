# 貪婪演算法

#### tags: `Algorithm` <a id="tags-Algorithm"></a>

## 概念 <a id="&#x6982;&#x5FF5;"></a>

貪婪演算法\(greedy algorithm\)使用貪婪策略\(greedy strategy\)解決問題。  
 假設一個問題可以藉由一系列的選擇\(或決策\)來解決，貪婪演算法的特性為每一次選擇皆採取**區域最佳解\(locally optimal solution\)** ，而透過每一個區域最佳解最後綜合成為**全域最佳解\(globally optimal solution\)** 而將問題解決。

## 背包演算法\(Knapsack algorithm\) <a id="&#x80CC;&#x5305;&#x6F14;&#x7B97;&#x6CD5;Knapsack-algorithm"></a>

### Definition <a id="Definition"></a>

![](https://i.imgur.com/sSrzUEy.png)

### Algorithm <a id="Algorithm"></a>

![](https://i.imgur.com/txSWLf7.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;"></a>

* 依pi/wi由大至小排序: O\(nlogn\)
* 將物品依序放入背包: O\(n\)
* 總時間複雜度: O\(nlogn\)

### Ex. <a id="Ex"></a>

* 給定:  n=3, m=5,\(w1,w2,w3\)=\(1,2,3\),\(p1,p2,p3\)=\(20,60,45\)
* 貪婪策略解答:
  * p1/w1 = 20/1 = 20
  * p2/w2 = 60/2 = 30
  * p3/w3 = 45/3 = 15
  * 最佳解: x2=1,x1=1,x3=2/3
  * 最大總價值: 60\* 1 + 20\* 1+ 45\* \(2/3\) =110

## 0/1背包問題 <a id="01&#x80CC;&#x5305;&#x554F;&#x984C;"></a>

### Definition <a id="Definition1"></a>

![](https://i.imgur.com/Voi2Bbp.png)

### Ex. <a id="Ex1"></a>

* 給定:  n=3, m=5,\(w1,w2,w3\)=\(1,2,3\),\(p1,p2,p3\)=\(20,60,45\)
* 貪婪策略解答:
  * p1/w1 = 20/1 = 20
  * p2/w2 = 60/2 = 30
  * p3/w3 = 45/3 = 15
  * 解: x2=1,x1=1,x3=0
  * 總價值: 60\* 1 + 20\* 1+ 45\* 0 =80
* 最佳解: x1=0,x2=1,x3=1
* 最大總價值: 20\* 0+ 60\* 1+ 45\* 1 =105

## Huffman code <a id="Huffman-code"></a>

### 概念 <a id="&#x6982;&#x5FF5;1"></a>

* 字元編碼\(character coding\)可以分為
  * 固定長度編碼: 如ACSII、Unicode
  * 可變長度編碼: Huffman code
* Huffman編碼以 **字首碼\(prefix code\)** 方式達到字元編碼最佳資料壓縮\(optimal data compression\)
  * 字首碼 \(prefix code\): 任何字元編碼一定不是其他字元編碼的字首\(prefix\)。
  * 可以使用二元樹來呈現，達到簡單編碼\(encoding\)與解碼\(decoding\)的功能  

![](https://i.imgur.com/9nFCMcl.png)

### Cost <a id="Cost"></a>

![](https://i.imgur.com/2iSDXDv.png)

### Algorithm <a id="Algorithm1"></a>

```cpp
Algorithm Huffman編碼演算法

Input: 字元集合C與每個字元的出現頻率f
Output: Huffman編碼樹

1.	n <- |C|   //C: the set of n characters
2.	Q <- C   //Q: 優先佇列，以字元頻率為優先次序
3.	for  i <- 1 to  n – 1 //n個字元(節點)欲合併成一個節點，每迭代合併一次可少一節點
4.	    配置一個新的樹節點u
5.	    u.left <- x <- GetMin(Q)
6.	    u.right <- y <- GetMin(Q)
7.	    u.f <- x.f + y.f
8.	    Insert u into Q
9.	return GetMIN(Q) 作為Huffman編碼樹的樹根
```

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;1"></a>

* O\(n\)建立優先佇列Q
* for迴圈一共執行n-1次，而且迴圈中的優先佇列操作均為O\(log n\)複雜度
* 總時間複雜度: O\(nlogn\)

## Kruskal Minimum Spanning Tree <a id="Kruskal-Minimum-Spanning-Tree"></a>

### 最小含括樹\(Minimum Spanning Tree, MST\) <a id="&#x6700;&#x5C0F;&#x542B;&#x62EC;&#x6A39;Minimum-Spanning-Tree-MST"></a>

* 定義在歐式空間\(Euclidean space\)或者一個圖\(graph\)上。
* 給定一個加權連通無向圖\(weighted connected undirected graph\) G = \(V, E\)
* **含括樹\(spanning tree\)** H=\(V,T\), T屬於E,是一個無向樹\(undirected tree\)，它是G的子圖，包含G的所有節點
* 最小含括樹MST是一個擁有**最小\(minimum\)總權重\(weight\)** 或總成本\(cost\)的含括樹

### 概念 <a id="&#x6982;&#x5FF5;2"></a>

* Kruskal最小含括樹演算法是一個貪婪演算法\(greedy algorithm\)
* 它採取貪婪解題策略產生給定圖G=\(V, E\)的最小含括樹H=\(V, T\)，每次都是挑選最小成本且不形成cycle的邊加入目前的最小含括樹的邊集合T之中
* 因為n個節點的樹具有n-1個邊，因此，經過n-1次邊的挑選之後，就可以形成累積成本最小的含括樹。  ![](https://i.imgur.com/2AXa5Q9.png)

### Algorithm <a id="Algorithm2"></a>

![](https://i.imgur.com/1ESOymg.png)

### Ex. <a id="Ex2"></a>

![](https://i.imgur.com/rCKobUr.png)

## Prim Minimum Spanning Tree <a id="Prim-Minimum-Spanning-Tree"></a>

### 概念 <a id="&#x6982;&#x5FF5;3"></a>

* Prim最小含括樹演算法是一個貪婪演算法\(greedy algorithm\)。
* 它採取貪婪解題策略產生給定圖G=\(V, E\)的最小含括樹H=\(V,T\)。此演算法先隨意挑一個節點加入集合X中，此後每次都挑選一個一端的節點在X中，而另一端的節點在\(V-X\)中的最小成本的邊。如此，可保證將所挑選的邊加入T之後不會形成循環\(cycle\)，這代表H=\(V, T\)是一棵樹\(tree\)。
* 等挑完n-1個邊之後，H=\(V, T\)就是最小含括樹\(MST\)。

### Algorithm <a id="Algorithm3"></a>

![](https://i.imgur.com/JqhiRUu.png)

### Ex. <a id="Ex3"></a>

![](https://i.imgur.com/ATtOLyP.png)

### 時間複雜度 <a id="&#x6642;&#x9593;&#x8907;&#x96DC;&#x5EA6;2"></a>

* while迴圈\(行3-6\): n-1 -&gt; O\(n\)
* 在\(u, v\)中選擇最小權重，其中u屬於X，v屬於V-X -&gt; O\(n\)
* 總時間複雜度: **O\(n^2\)**

