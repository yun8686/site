# operator<<
* chrono[meta header]
* std::chrono[meta namespace]
* function[meta id-type]
* cpp20[meta cpp]

```cpp
namespace std::chrono {
  template <class charT, class traits>
  std::basic_ostream<charT, traits>&
    operator<<(bstd::asic_ostream<charT, traits>& os, const day& d); // (1) C++20
}
```

## 概要
`day`オブジェクトを出力ストリームに出力する。


## 戻り値
便宜上のリテラルキャスト`STATICALLY-WIDEN`を導入する。`STATICALLY-WIDEN<charT>("...")`は、`charT`が`char`である場合は`"..."`、`charT`が`wchar_t`である場合は`L"..."`を意味する。

- (1) : 以下と等価：
    ```cpp
    return os << (d.ok() ?
      format(os.getloc(), STATICALLY-WIDEN<charT>("{:%d}"), d) :
      format(os.getloc(), STATICALLY-WIDEN<charT>("{:%d} is not a valid day"), d));
    ```
    * format[link /reference/format/format.md]
    * os.getloc()[link /reference/ios/ios_base/getloc.md]


## 備考
- このフォーマットでは、2桁ゼロ埋めで日の整数値が出力される。1桁の日を出力する場合、`01`のように先頭にゼロがつく


## 例
```cpp example
#include <iostream>
#include <chrono>

namespace chrono = std::chrono;

int main()
{
  std::cout << chrono::day{1} << std::endl;
  std::cout << chrono::day{15} << std::endl;
}
```

### 出力
```
01
15
```

## バージョン
### 言語
- C++20

### 処理系
- [Clang](/implementation.md#clang): (9.0時点で実装なし)
- [GCC](/implementation.md#gcc): (9.2時点で実装なし)
- [Visual C++](/implementation.md#visual_cpp): (2019 Update 3時点で実装なし)


## 関連項目
- [`local_time_format()`](/reference/chrono/local_time_format.md.nolink) (フォーマットの詳細)
