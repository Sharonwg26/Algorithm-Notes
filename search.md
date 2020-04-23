# 搜尋演算法

#### tags: `Algorithm` <a id="tags-Algorithm"></a>

## 廣度優先搜尋\(width-first search\)演算法 <a id="&#x5EE3;&#x5EA6;&#x512A;&#x5148;&#x641C;&#x5C0B;width-first-search&#x6F14;&#x7B97;&#x6CD5;"></a>

* 先將樹中同一層的所有節點全部拜訪\(或檢查\)過之後，才拜訪\(或檢查\)下一層的節點。
* 使用佇列\(queue\)來實作

```text
Algorithm 廣度優先搜尋演算法

Input: 起始狀態(或起始節點)與目標狀態(或目標節點) 
Output: 目標狀態(或目標節點)對應的解答

1: 設定起始節點為解答空間樹的根節點，標示根節點，並建立一個只包含啟始節點的佇列(queue)。
2: 拜訪並檢查佇列的第一個元素(節點)是否為目標節點(goal node)。若是，則輸出目標節點所對應的解答並停止。
3: 移除佇列中的第一個節點。若此節點可以擴展(expand)出未標示過的子節點，則標示這些節點，並將其加入佇列的尾端。
4: 若佇列為空，則回報無解答並停止。否則，跳至步驟2繼續執行。

```

![](https://i.imgur.com/8rIKg0r.png)

## 深度優先搜尋\(depth-first search\)演算法 <a id="&#x6DF1;&#x5EA6;&#x512A;&#x5148;&#x641C;&#x5C0B;depth-first-search&#x6F14;&#x7B97;&#x6CD5;"></a>

* 總是先拜訪最深的節點\(deepest node\)
* 使用堆疊\(stack\)來實作

```cpp
Algorithm 深度優先搜尋演算法

Input: 起始狀態(或起始節點)與目標狀態(或目標節點) 
Output: 目標狀態(或目標節點)對應的解答

1: 設定起始節點為解答空間樹的根節點， 標示根節點，並建立一個只包含啟始節點的堆疊(stack)。
2: 拜訪並檢查堆疊頂端的元素(節點)是否為目標節點(goal node)。若是，則輸出目標節點所對應的解答並停止。
3: 移除堆疊頂端的節點。若此節點可以擴展(expand)出未標示過的子節點，則標示這些節點，並將其一一加入堆疊的頂端。
4: 若堆疊為空，則回報無解答並停止。否則，跳至步驟2繼續執行。
 
```

![](https://i.imgur.com/4ydM26S.png)

![](https://i.imgur.com/LgvTPFw.png)

## 登山搜尋\(hill-climbing search\)演算法 <a id="&#x767B;&#x5C71;&#x641C;&#x5C0B;hill-climbing-search&#x6F14;&#x7B97;&#x6CD5;"></a>

堆疊\(stack\)並配合評估函數\(evaluation function\)計算節點對應的優先順序或到達目標節點的預估成本，以便優先拜訪子節點中最佳的節點

```cpp
Algorithm 登山搜尋演算法

Input: 起始狀態(或起始節點)與目標狀態(或目標節點) 
Output: 目標狀態(或目標節點)對應的解答

1: 設定起始節點為解答空間樹的根節點，標示根節點，並建立一個只包含啟始節點的堆疊(stack)。
2: 拜訪並檢查堆疊頂端的元素(節點)是否為目標節點(goal node)。若是，則輸出目標節點所對應的解答並停止。
3: 移除堆疊頂端的節點。若此節點可以擴展(expand)出未標示過的子節點，則標示這些節點，並根據由評估函數所計算的優先順序將其一一加入堆疊的頂端，優先順序低的先加入。
4: 若堆疊為空，則回報無解答並停止。否則，跳至步驟2繼續執行。
```

![](https://i.imgur.com/aPHRRnQ.png)

## 最佳優先搜尋\(best-first search\)演算法 <a id="&#x6700;&#x4F73;&#x512A;&#x5148;&#x641C;&#x5C0B;best-first-search&#x6F14;&#x7B97;&#x6CD5;"></a>

* 從所有已被擴展出的節點中選出評估函數\(evaluation function\)估計為優先順序最高的節點進行拜訪。
* 相對於僅具有區域\(也就是僅限於某分支\)最佳觀點的登山搜尋演算法，最佳優先搜尋演算法具有全域最佳的觀點。
* 可以使用堆積\(heap\)來實作。

```cpp
Algorithm 最佳優先搜尋演算法

Input: 起始狀態(或起始節點)與目標狀態(或目標節點) 
Output: 目標狀態(或目標節點)對應的解答

1: 設定起始節點為解答空間樹的根節點，標示根節點，並建立一個只包含啟始節點一個元素的堆積(heap)。
2: 拜訪並檢查堆積中優先順序最高的元素(節點)是否為目標節點(goal node)。若是，則輸出目標節點所對應的解答並停止。
3: 移除堆積優先順序最高的節點。若此節點可以擴展(expand)出未標示過的子節點，則標示這些節點，並根據由評估函數所計算的優先順序將其一一加入堆積中。
4: 若堆積為空，則回報無解答並停止。否則，跳至步驟2繼續執行。
 
```

![](https://i.imgur.com/1kM13rl.png)

![](https://i.imgur.com/1jqDkGH.png)

## 子集合加總問題\(sum of subset\) <a id="&#x5B50;&#x96C6;&#x5408;&#x52A0;&#x7E3D;&#x554F;&#x984C;sum-of-subset"></a>

### 定義 <a id="&#x5B9A;&#x7FA9;0"></a>

給定一個整數集合S和一個整數m，問是否存在S的非空子集合T，使得子集合T中的整數總和為m。

給定一個整數集合S ={6, 5, 1, 3, 8} ，回答是否存在S的非空子集合T，使得子集合T中的整數總和為10。  
 

![](https://i.imgur.com/L8QLlIF.png)

## 漢米爾頓迴路問題 \(Hamiltonian circuit\) <a id="&#x6F22;&#x7C73;&#x723E;&#x9813;&#x8FF4;&#x8DEF;&#x554F;&#x984C;-Hamiltonian-circuit"></a>

* 一個無向圖\(undirected graph\)上的漢米爾頓迴路\(Hamiltonian circuit\)又稱為漢米爾頓循環\(Hamiltonian cycle\)或漢米爾頓旅途\(Hamiltonian tour\)
* 是一條由某個起始節點出發，經過每個節點恰好一次，且最後會回到起始節點的路徑\(path\)  ![](https://i.imgur.com/d8MKd8w.png)

### 定義 <a id="&#x5B9A;&#x7FA9;"></a>

一條往返路徑，經過每個節點恰好一次，且最後會回到起始的節點。  
 決定一個無向圖之中是否存在漢米爾頓迴路的問題，稱為漢米爾頓迴路問題\(Hamiltonian circuit problem\)。這是是一個NPC問題，也就是非確定性多項式時間完全問題 \(non-deterministic polynomial complete problem, NP-complete problem, NPC problem\)。

解答左方給定的無向圖是否存在漢米爾頓迴路的解答空間樹  
 

![](https://i.imgur.com/8fFpWxq.png)

以廣度優先演算法  
 

![](https://i.imgur.com/zECJ3Ao.png)

以深度優先演算法  
 

![](https://i.imgur.com/xwOSqsd.png)

## 延伸 <a id="&#x5EF6;&#x4F38;"></a>

### 旅行銷售員問題 <a id="&#x65C5;&#x884C;&#x92B7;&#x552E;&#x54E1;&#x554F;&#x984C;"></a>

* 旅行銷售員問題\(Traveling Salesperson Problem, TSP\):給定一個加權無向圖，求出其中邊加權總合最小或長度最短的漢米爾頓迴路\(Hamiltonian circuit of the minimum length\)。
* TSP是一個是一個NP-hard問題，也就是非確定性多項式時間困難問題 \(non-deterministic polynomial hard problem, NP-hard problem\)。

### 歐拉迴路問題 <a id="&#x6B50;&#x62C9;&#x8FF4;&#x8DEF;&#x554F;&#x984C;"></a>

* 歐拉路徑\(Eulerian path\)或歐拉鏈\(Eulerian chain\): 無向圖上的一條路徑，經過每個邊恰好一次。
* 歐拉迴路\(Eulerian circuit\): 一個無向圖上經過每個邊恰好一次的迴路。
* 歐拉路徑問題:找出無向圖上歐拉路徑的問題，是一個P問題，也就是多項式時間\(polynomial problem\)問題。

## 回溯演算法 <a id="&#x56DE;&#x6EAF;&#x6F14;&#x7B97;&#x6CD5;"></a>

在邏輯上隱含地用到解空間樹，但是在思維上不一定提及解空間樹，有時會以遞迴的方式來實現，以一個個的選擇\(choice\)來找出可行解。在進行選擇的時候，可以先選擇較可能有好結果的部份\(與hill climbing概念類似\)，或是提早判斷死端\(dead end\)\(也就是確定不會產生可行解的狀態\)的出現以提早進行回溯退回先前的選擇分岔點。

### 八后問題\(eight queen problem\) <a id="&#x516B;&#x540E;&#x554F;&#x984C;eight-queen-problem"></a>

* 如何在一個8×8的西洋棋棋盤\(check board\)上放置8個不會互相攻擊的皇后棋子。
* 皇后棋子可以從上、下、左、右、左上、左下、右上、右下等八個方向攻擊對方的棋子。因此，一個皇后棋子延伸出去的上、下、左、右、左上、左下、右上、右下的八個方向上都不能有其他皇后棋子。  ![](https://i.imgur.com/wmp2CWl.png)

```cpp
Algorithm  PutQueen(i, n)

Input：整數i、整數n  //i(0<=i<=n-1)表示目前正放置編號為i(第i+1個)的皇后棋子
Output：n個皇后棋子在n×n棋盤上不互相攻擊之位置
j←0  
while j < n do
   if i列j行可放置皇后棋子 then 
      q[i]←j
      if i＝n-1  then
      else  PutQueen(i+1, n)
   j←j+1 
return

```

![](https://i.imgur.com/NKNCokV.png)

