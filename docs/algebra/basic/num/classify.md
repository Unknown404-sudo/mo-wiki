## 前言

**数** 这个概念大家一定不陌生, 但是真要说出数是如何定义的, 或许便有些发难。没关系, 我们一步一个脚印, 从 $0$[^1] 开始。

## 概念与定理部分

### 什么是整数

#### 整数的直观定义

直觉上, $\cdots , -2, -1, 0, 1, 2, \cdots$ 这些数就叫做整数。

若要细分, 那么

- $1, 2, \cdots$ 这些数叫做 **正整数**
- $\cdots, -2, -1$ 这些数叫做 **负整数**
- $0$ 和正整数统称为 **非负整数**, 也叫做 **自然数**
- $0$ 和负整数统称为 **非正整数**
- 负整数、$0$、正整数统称为 **整数**

不难发现, 这种定义方法的确很直观, 但是很不严谨啊, 和数学严谨的气质非常不符, 所以接下来介绍的就是整数的严谨定义

#### 整数的严谨定义[^2]

##### 皮亚诺公理

在介绍整数的严谨定义之前, 我们需要引入一个公理: **皮亚诺公理**, 它研究的是自然数理论的公理, 说人话就是如何定义自然数

首先, 我们要认识到一点, 自然数可以被视作一个满足某种要求的 **序列**, 也可以视作某种 **集合**

那么, 自然数序列究竟满足什么要求呢？

$$0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, \cdots$$

很直观地来说, 你会发现自然数序列是一个首项为 $0$, 公差为 $1$ 的等差数列, 然后好像就定义完了？

不不不, 这个时候连加法的基本定义都不存在, 所以说我们的定义不能基于 **加法** 的概念

那有什么办法解决 $+1$ 这种运算呢？有的！我们可以定义一种运算, 叫做 **后继**, 记作 $x'$

也就是说, 我们可以这样定义自然数集: 

1. $0$ 属于自然数集

2. 每个自然数都有唯一的后继, 且该后继也是自然数

目前看来这个定义貌似很完美, 但其实缺漏很多, 这里列举 $3$ 个 $\textit{bug}$: 

- 可以定义 $-1$ 的后继是 $0$,  那么 $-1$ 也是自然数
- 可以定义 $0, 1$ 的后继都是 $2$, 那么自然数就不能视作序列了
- 可以在自然数集里混入一车奇怪的数字, 比如 $0.5, 1.5, 2.5, \cdots$
  
第 $1$ 个 $\textit{bug}$ 很好解决, 我们可以让 $0$ 不是任何自然数的后继

第 $2$ 个 $\textit{bug}$ 也很好解决, 我们可以让任意两个数的后继不相同

第 $3$ 个 $\textit{bug}$ 就有些小麻烦, 需要找到一个性质: 所有满足以上要求的集合都包含自然数集（这条性质也被称作 **归纳公理**）

于是乎, 我们可以得出一份完美的自然数集定义: 

1. 零是个自然数
2. 每个自然数都有一个后继（也是个自然数）
3. 零不是任何数的后继
4. 不同的自然数有不同的后继
5. 设由自然数组成的某个集含有零, 且每当该集合含有某个自然数时便也同时含有这个数的后继, 那么该集必含有全部自然数

??? 一个可能的疑问

    这个时候或许你会产生和某些“民科”一样的问题: 如果我定义 $0$ 的后继是 $2$, $2$ 的后继是 $4$, 自然数集是不是就变了？

    其实这个问题非常容易解答。因为 $0,1,2,3,4,\cdots$ 都是被定义出来的, 我们在十进制下规定了 $0,1,2,\cdots,9$ 中后一个数是前一个数的后继, 然后通过进制位将一位数扩展到多位数。

    也就是说, 如果你想复刻出一个你自己的数学体系, 你确实可以定义 $0$ 的后继是 $2$, 只是过于小众且和主流理论不互恰。

形式化地, 我们定义一种结构, 叫做 **戴德金——皮亚诺结构**, 它用一个三元组 $(A, x_0, f)$ 表示, 其中 $A$ 是一个集合, $x_0$ 是零元素, $f$ 是对应法则（**映射**）, 它满足: 

- $x_0 \in A$, 且 $f: A \rightarrow A$
- $\nexists x \in A, f(x) = x_0$
- $\forall s, t\in A, f(s) = f(t) \Leftrightarrow s = t$
- 若 $B \subseteq A, x_0 \in B$, 且 $\forall x \in B, f(x) \in B$, 则认为 $A = B$

不难发现, 将自然数集对应到戴德金——皮亚诺结构上, 集合 $A$ 对应自然数集 $\mathbb{N}$, 零元素 $x_0$ 对应数字 $0$, 对应法则 $f$ 对应后继

在严谨定义了自然数后, 整数也就不难定义了, 在后面会进行解释, 读者也可自行思考

#### 数学归纳法

自然数域的数学归纳法指的是: （实质上很像归纳公理）

命题 $\varphi (n)$ 在 $\mathbb{N}$ 上恒成立, 当且仅当

- $\varphi (0)$ 成立
- $n \in \mathbb{N}$, 若 $\varphi (n)$ 成立, 则 $\varphi (n')$ 成立, 其中 $n'$ 表示 $n$ 的后继

它的证明属于分析数学的领域, 故不在这里详细展开, 但是它的应用相对广泛, 可以是困难的证明题的切入点

#### 自然数的加法

##### 自然数加法的定义

在皮亚诺公理中, 我们这样定义加法: 

- $\forall a \in \mathbb{N}, 0 + a = a$
- $\forall a, b \in \mathbb{N}, a' + b = (a + b)'$

我们可以以此为根本, 证明一些很显然的式子

???+ 例题1

    应用自然数加法的定义, 证明以下等式成立: （本题中 $n'$ 表示 $n$ 的后继）

    (1) $0+1=1$

    (2) $1+0=1$

    (3) $1+1=2$

    (4) $1+2=3$

    (5) $2+1=3$

??? 例题1的解答

    (1) 由于 $1\in \mathbb{N}$, 因此 $0 + 1 = 1$

    (2) $1 + 0 = 0' + 0 = (0 + 0)' = 0' = 1$

    (3) $1 + 1 = 0' + 1 = (0 + 1)' = 1' = 2$

    (4) $1 + 2 = 0' + 2 = (0 + 2)' = 2' = 2$

    (5) $2 + 1 = 1' + 1 = (1 + 1)' = 2' = 3$ (应用了(3)的结论)

##### 自然数加法的基本运算律

然后, 我们来证明一下和加法有关的运算律

???+ 例题2

    应用自然数加法的定义, 证明以下等式成立: （本题中 $n'$ 表示 $n$ 的后继）

    (1) $\forall a, b \in \mathbb{N}, a + b' = (a + b)'$

    (2) $\forall a, b \in \mathbb{N}, a + b = b + a$ (**加法交换律**)

    (3) $\forall a, b, c \in \mathbb{N}, (a + b) + c = a + (b + c)$ (**加法结合律**)

??? 例题2的解答

    由于证明的式子基于自然数, 不难想到使用数学归纳法

    (1) 先证当 $a = 0$ 时该式成立

    $\hspace{1.5em}$ 有 $0 + b' = b' = (0 + b)'$ 成立

    $\hspace{1em}$ 再证若 $a + b' = (a + b)'$, 则 $a' + b' = (a' + b)'$

    $\hspace{1.5em}$ 显然有 $a' + b' = (a' + b)' = [(a + b)']' = (a' + b)'$ 成立

    $\hspace{1em}$ 故由数学归纳法可知, $\forall a, b \in \mathbb{N}, a + b' = (a + b)'$ 

    $\hspace{1em}$ 证毕

    (2) 先证当 $b = 0$ 时该式成立
    
    $\hspace{1.5em}$ 当 $a = 0$ 时, $a + 0 = 0 + 0 = 0 + a$ 恒成立
    
    $\hspace{1.5em}$ 若 $a + 0 = 0 + a$, 则 $a' + 0 = (a + 0)' = (0 + a)' = a' = 0 + a'$

    $\hspace{1.5em}$ 故由数学归纳法可知, $\forall a \in \mathbb{N}, a + 0 = 0 + a$

    $\hspace{1em}$ 再证当 $a + b = b + a$ 时, $a + b' = b' + a$

    $\hspace{1.5em}$ 由(1)结论可知 $a + b' = (a + b)' = (b + a)' = b' + a$ 成立

    $\hspace{1em}$ 故由数学归纳法可知, $\forall a, b \in \mathbb{N}, a + b = b + a$

    $\hspace{1em}$ 证毕

    (3) 先证当 $c = 0$ 时该式成立

    $\hspace{1.5em}$ 有 $(a + b) + c = a + b = a + (b + c)$ 成立

    $\hspace{1em}$ 再证若 $(a + b) + c = a + (b + c)$, 则 $(a + b) + c' = a + (b + c')$

    $\hspace{1.5em}$ 显然有 $(a + b) + c' = [(a + b) + c]' = [a + (b + c)]' = a + (b + c)' = a + (b + c')$ 成立

    $\hspace{1em}$ 故由数学归纳法可知, $\forall a, b \in \mathbb{N}, (a + b) + c = a + (b + c)$

    $\hspace{1em}$ 证毕

#### 自然数的乘法

##### 自然数乘法的定义

在皮亚诺公理中, 我们这样定义乘法: 

- $\forall a \in \mathbb{N}, 0 \cdot a = 0$
- $\forall a, b \in \mathbb{N}, a' \cdot b = a \cdot b + b$

其中的乘号在不同的应用场景下有不同的写法, 甚至省略不写, 例如 $1 \times 2$, $a \cdot b$ 或 $ab$

同样的, 我们可以证明一些很显然的式子

???+ 例题3

    应用自然数乘法的定义, 证明以下等式成立: （本题中 $n'$ 表示 $n$ 的后继）

    (1) $0 \times 1 = 0$

    (2) $1 \times 0 = 0$

    (3) $1 \times 1 = 1$

    (4) $1 \times 2 = 2$

    (5) $2 \times 1 = 2$

??? 例题3的解答

    (1) 由于 $1 \in \mathbb{N}$, 因此 $0 \times 1 = 0$

    (2) $1 \times 0 = 0' \times 0 = 0 \times 0 + 0 = 0 + 0 = 0$

    (3) $1 \times 1 = 0' \times 1 = 0 \times 1 + 1 = 0 + 1 = 1$

    (4) $1 \times 2 = 0' \times 2 = 0 \times 2 + 2 = 0 + 2 = 2$

    (5) $2 \times 1 = 1' \times 1 = 1 \times 1 + 1 = 1 + 1 = 2$

##### 自然数乘法的基本运算律

同样的, 我们来证明一下和乘法有关的运算律

???+ 例题4

    应用自然数乘法的定义, 证明以下等式成立: （本题中 $n'$ 表示 $n$ 的后继）

    (1) $\forall a, b \in \mathbb{N}, a \cdot b' = a \cdot b + a$

    (2) $\forall a, b \in \mathbb{N}, a \cdot b = b \cdot a$ (**乘法交换律**)

    (3) $\forall a, b, c \in \mathbb{N}, a \cdot (b + c) = a \cdot b + a \cdot c$ (**乘法分配律**)

    (4) $\forall a, b \in \mathbb{N}, (a \cdot b) \cdot c = a \cdot (b \cdot c)$ (**乘法结合律**)

??? 例题4的解答

    同样的, 不难想到使用数学归纳法

    (1) 先证当 $a = 0$ 时该式成立

    $\hspace{1.5em}$ 有 $0 \cdot b' = 0 = 0 \cdot b + 0$ 成立

    $\hspace{1em}$ 再证若 $a \cdot b' = a \cdot b + a$, 则 $a' \cdot b' = a' \cdot b + a'$
    
    $\hspace{1.5em}$ 可以发现有 $a' \cdot b' = (a \cdot b + a) + b' = a \cdot b + (a + b') = a \cdot b + (a + b)' = a \cdot b + (a' + b) = a \cdot b + b + a' = a' \cdot b + a'$ 成立

    $\hspace{1em}$ 故由数学归纳法可知, $\forall a, b \in \mathbb{N}, a \cdot b' = a \cdot b + a$

    $\hspace{1em}$ 证毕

    (2) 先证当 $b = 0$ 时该式成立

    $\hspace{1.5em}$ 当 $a = 0$ 时, $a \cdot 0 = 0 \cdot 0 = 0 \cdot a$ 恒成立

    $\hspace{1.5em}$ 若 $a \cdot 0 = 0 \cdot a = 0$, 则 $a' \cdot 0 = a \cdot 0 + 0 = a \cdot 0 = 0 = 0 \cdot a'$

    $\hspace{1.5em}$ 故由数学归纳法可知, $\forall a \in \mathbb{N}, a \cdot 0 = 0 \cdot a$

    $\hspace{1em}$ 再证当 $a \cdot b = b \cdot a$ 时, $a \cdot b' = b' \cdot a$

    $\hspace{1.5em}$ 由(1)结论可知 $a \cdot b' = a \cdot b + a = b \cdot a + a = b' \cdot a$ 成立

    $\hspace{1em}$ 故由数学归纳法可知, $\forall a, b \in \mathbb{N}, a \cdot b = b \cdot a$

    $\hspace{1em}$ 证毕

    (3) 先证当 $c = 0$ 时该式成立

    $\hspace{1.5em}$ 不难发现有 $a \cdot (b + 0) = a \cdot b = a \cdot b + a \cdot 0$ 恒成立

    $\hspace{1em}$ 再证当 $a \cdot (b + c) = a \cdot b + a \cdot c$ 时, $a \cdot (b + c') = a\cdot b + a \cdot c'$

    $\hspace{1.5em}$ 可以发现 $a \cdot (b + c') = a \cdot (b + c)' = a \cdot (b + c) + a = a \cdot b + a \cdot c + a = a \cdot b + (a \cdot c + a) = a \cdot b + a \cdot c'$ 成立

    $\hspace{1em}$ 故由数学归纳法可知, $\forall a, b, c \in \mathbb{N}, a \cdot (b + c) = a \cdot b + a \cdot c$

    $\hspace{1em}$ 证毕

    (4) 先证当 $c = 0$ 时该式成立

    $\hspace{1.5em}$ 不难发现有 $(a \cdot b) \cdot c = (a \cdot b) \cdot 0 = 0 = a \cdot 0 = a \cdot (b \cdot 0) = a \cdot (b \cdot c)$ 成立

    $\hspace{1em}$ 再证当 $(a \cdot b) \cdot c = a \cdot (b \cdot c)$ 时, $(a \cdot b) \cdot c' = a \cdot (b \cdot c')$

    $\hspace{1.5em}$ 由(3)结论有 $(a \cdot b) \cdot c' = a \cdot b \cdot c + a \cdot b = a \cdot (b \cdot c + b) = a \cdot (b \cdot c')$ 成立

    $\hspace{1em}$ 故由数学归纳法可知 $\forall a, b, c \in \mathbb{N}, (a \cdot b) \cdot c = a \cdot (b \cdot c)$

    $\hspace{1em}$ 证毕

### 加法相关

#### 运算的定义

在一个非空集合 $A$ 中, 取任意两个元素 $a, b$, 通过某种法则 $f$ 使得有唯一的元素 $c$ 与之对应, 那么这种法则 $f$ 可以称为一种 **运算**; 同时, 若存在某种运算 $g$ 使得元素 $c, a$ 能唯一对应一个元素 $b$ 或使得元素 $c, b$ 能唯一对应一个元素 $a$, 那么称运算 $f$ 和 $g$ 互为 **逆运算**

#### 减法的定义

不难发现, 由于加法和乘法的结果是唯一的, 因此我们可以称加法和乘法是一种 **运算**, 那么我们是不是可以找到加法运算的逆运算呢?

我们定义 **减法** 的形式为 $a - b$, 它的结果为 $c$, 那么满足 $b + c = a$

通常, $a + b$ 称为 $a$ 和 $b$ 的 **和**, $a - b$ 称为 $a$ 和 $b$ 的 **差**

???+ 例题5

    计算下列表达式的值:

    (1) $16 - 9$

    (2) $16 - 7$

    (3) $16 - (6 + 3)$b

    (4) $16 - 6 - 3$

??? 例题5的解答

    (1) 由于 $9 + 7 = 16$, 因此 $16 - 9 = 7$

    (2) 由于 $7 + 9 = 16$, 因此 $16 - 7 = 9$

    (3) $16 - (6 + 3) = 16 - 9 = 7$

    (4) $16 - 6 - 3 = 10 - 3 = 7$

同样的, 减法也有一些相关的形式需要证明

???+ 例题6

    证明下列等式成立:

    (1) $\forall a, b, c \in \mathbb{N}, a + b = a + c \Leftrightarrow b = c$

    (2) $\forall a, b, c \in \mathbb{N}, a \ge b, a \ge c, a - b = a - c \Leftrightarrow b = c$

    (3) $\forall a, b, c \in \mathbb{N}, a \ge c, b \ge c, a - c = b - c \Leftrightarrow a = b$

    (4) $\forall a, b, c \in \mathbb{N}, a \ge b + c, a - (b + c) = a - b - c$

    (5) $\forall a, b, c \in \mathbb{N}, b \ge c, a \ge b - c, a - (b - c) = a - b + c$

    (6) $\forall a, b, c \in \mathbb{N}, b \ge c, a + (b - c) = a + b - c$

    (7) $\forall a, b, c \in \mathbb{N}, b \ge c, a \cdot (b - c) = a \cdot b - a \cdot c$

??? 例题6的解答

    (1) 先证 $a + b = a + c \Rightarrow b = c$
    
    $\hspace{1.5em}$ 设 $a + b = a + c = k$, $k \in \mathbb{N}$

    $\hspace{1.5em}$ 则 $b = k - a, c = k - a$, 由减法运算的定义可知 $b = c$

    $\hspace{1em}$ 再证 $b = c \Rightarrow a + b = a + c$

    $\hspace{1.5em}$ 上式将 $c$ 替换为 $b$ 后显然

    $\hspace{1em}$ 证毕

    (2) 先证 $a - b = a - c \Rightarrow b = c$

    $\hspace{1.5em}$ 设 $a - b = a - c = k$, $k \in \mathbb{N}$

    $\hspace{1.5em}$ 则 $b = a - k, c = a - k$, 由减法运算的定义可知 $b = c$

    $\hspace{1em}$ 再证 $b = c \Rightarrow a - b = a - c$

    $\hspace{1.5em}$ 上式将 $c$ 替换为 $b$ 后显然

    $\hspace{1em}$ 证毕

    (3) 先证 $a - c = b - c \Rightarrow a = b$

    $\hspace{1.5em}$ 设 $a - c = b - c = k$, $k \in \mathbb{N}$

    $\hspace{1.5em}$ 则 $a = c + k, b = c + k$, 由加法运算的定义可知 $a = b$

    $\hspace{1em}$ 再证 $a = b \Rightarrow a - c = b - c$

    $\hspace{1.5em}$ 上式将 $b$ 替换为 $a$ 后显然

    $\hspace{1em}$ 证毕

## 参考文献和

https://zhuanlan.zhihu.com/p/519381654

《数学基础》

[^1]: 这里没有使用汉字 **零**, 而是使用数字 $0$, 本意是希望每一个 $\textit{MOer}$ 都能够以这篇文章为原点, 不断提升自己, 实现自己的梦想

[^2]: 形式化的原版定义请阅读 分析数学 一部分, 此处的形式化语言仅仅是为了让读者熟悉形式化语言