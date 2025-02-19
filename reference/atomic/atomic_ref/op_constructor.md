# コンストラクタ
* atomic[meta header]
* std[meta namespace]
* atomic_ref[meta class]
* function[meta id-type]
* cpp20[meta cpp]

```cpp
atomic_ref() = delete;                        // (1) C++20
explicit atomic_ref(T& obj);                  // (2) C++20
atomic_ref(const atomic_ref& other) noexcept; // (3) C++20
```

## 概要
- (1) : デフォルト構築禁止
- (2) : `obj`を参照して`*this`にポインタとして保持する
- (3) : コピーコンストラクタ。`other`が参照するオブジェクトを`*this`もまた参照する


## 事前条件
- 参照するオブジェクトがメンバ定数のアライメント値`required_alignment`にアライメントされていること


## 例外
投げない


## 例
```cpp example
#include <atomic>

int main()
{
  int value = 3;

  // valueを参照するatomic_refオブジェクトを構築
  std::atomic_ref<int> a{value};

  // コンストラクタの引数によって、
  // クラステンプレートのテンプレート引数を推論 (<int>を省略)
  std::atomic_ref b{value};

  // cとbで同じ値 (value) を参照
  std::atomic_ref c = b;
}
```


### 出力
```
```

## バージョン
### 言語
- C++20

### 処理系
- [Clang](/implementation.md#clang): (9.0時点で実装なし)
- [GCC](/implementation.md#gcc): 10.1
- [Visual C++](/implementation.md#visual_cpp): ??

