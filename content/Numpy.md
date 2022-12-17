---
title:
 'Numpy'
---

- ユニバーサルな操作: 全要素に与えられる要素
![image](https://gyazo.com/fef5839c70ce24aef6dd75cc07d4f122/thumb/1000)

- 四則演算、比較（=, <, >）, sin/cosなどでできる
- ![image](https://gyazo.com/006773ee04c86b03a84ed209c377b722/thumb/1000)
- np._ix()
    - 各次元に対してインデックスで選ぶときに楽
 python

```
# 以下の2つは同じ
print(a[np.ix_([0, 2], [1, 3])])
print(a[[[0], [2]], [1, 3]])
```

#GCI2020