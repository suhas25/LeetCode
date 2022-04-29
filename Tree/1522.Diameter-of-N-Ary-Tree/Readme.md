### 1522.Diameter-of-N-Ary-Tree

本题和```543.Diameter-of-Binary-Tree```一样的思路。在rooted-tree里，任何路径都一定有一个最高的拐点，往左是一条以某个孩子为起点的单链，往右是另一条以某个孩子为起点单链（所谓单链就是一路向下奔向叶子节点、不带拐弯的路径）。显然，我们会取所有孩子节点里最长的两条单链。

所以本题的本质就是求以任意节点node为起点的最长单链长度```h(node)```。显然有递推关系：```h(node) = max{h(node->child)}+1```. 

对于任意节点node，我们会找它孩子节点中最长的两条单链，再加1，就是以node为拐点的最长路径。全局的最长路径就是最终答案。