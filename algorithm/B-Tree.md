# B-Tree的性质
对于m阶B数，有如下性质
1. 每一个节点最多有m个子节点
2. 除了根节点，每个非叶子节点包含至少⌈m/2⌉个子节点
3. 如果根节点不是叶子节点，那么它包含至少2个子节点
4. 有k个子节点的非叶子节点包含k-1个key
5. 所有叶子节点都在同一层级
6. 所有非叶子节点包含下列信息数据
    > (n,K0,A0,K1,A1,K2,A2,...,Kn,An)  
    > 其中n为key的数量，⌈m/2⌉-1 <= n <= m-1


## 查找
使k是需要查找的key，从根节点开始向下递归查找，对于每个不是叶子的节点，如果这个节点包含k，那么返回该节点；否则，向下超找它的子节点，该子节点在第一个更大的key的左边。如果到达了叶子节点且找不到k，那么返回NULL

## 遍历
与二叉树遍历类似，采用中根遍历，先访问根节点，再访问左节点，最后访问右节点
