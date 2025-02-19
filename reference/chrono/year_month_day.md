# year_month_day
* chrono[meta header]
* std::chrono[meta namespace]
* class[meta id-type]
* cpp20[meta cpp]

```cpp
namespace std::chrono {
  class year_month_day;
}
```

## 概要
`year_month_day`は、年、月、日を表すカレンダー表現のためクラスである。

このクラスは、年、および月に関する演算に対応している。ただし、日に関する演算はできない。

このクラスは等値比較および大小比較ができ、[EqualityComparable](/reference/concepts/equality_comparable.md)およびLessThanComparableの要件を満たす。

このクラスは、[トリビアルコピー可能](/reference/type_traits/is_trivially_copyable.md)で、かつ[スタンダードレイアウト型](/reference/type_traits/is_standard_layout.md)である。


## メンバ関数
### 構築／コピー／破棄

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`(constructor)`](year_month_day/op_constructor.md.nolink) | コンストラクタ | C++20 |
| `year_month_day& operator=(const year_month_day&) = default;`<br/> `year_month_day& operator=(year_month_day&&) = default;` | 代入演算子 | C++20 |


### 算術演算

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`operator+=`](year_month_day/op_plus_assign.md.nolink)  | 加算の複合代入 | C++20 |
| [`operator-=`](year_month_day/op_minus_assign.md.nolink) | 減算の複合代入 | C++20 |


### 観測

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`year`](year_month_day/year.md)   | 年要素を取得する | C++20 |
| [`month`](year_month_day/month.md) | 月要素を取得する | C++20 |
| [`day`](year_month_day/day.md)     | 日要素を取得する | C++20 |


### 変換

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`sys_days`](year_month_day/sys_days.md.nolink)     | システム時間の日付を取得する | C++20 |
| [`local_days`](year_month_day/local_days.md.nolink) | システム時間の日付を取得する | C++20 |


### 検証

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`ok`](year_month_day/ok.md.nolink) | 値が範囲に収まっているか判定する | C++20 |


## 非メンバ関数
### 算術演算

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`operator+`](year_month_day/op_plus.md.nolink)  | 加算 | C++20 |
| [`operator-`](year_month_day/op_minus.md.nolink) | 減算 | C++20 |


### 比較演算

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`operator==`](year_month_day/op_equal.md.nolink) | 等値比較を行う | C++20 |
| `bool operator!=(const year_month_day&, const year_month_day&) noexcept;` | 非等値比較を行う (`==`により使用可能) | C++20 |
| [`operator<=>`](year_month_day/op_compare_3way.md.nolink) | 三方比較を行う | C++20 |
| `bool operator<(const year_month_day&, const year_month_day&) noexcept;` | 左辺が右辺より小さいかを判定する (`<=>`により使用可能) | C++20 |
| `bool operator<=(const year_month_day&, const year_month_day&) noexcept;` | 左辺が右辺以下を判定する (`<=>`により使用可能) | C++20 |
| `bool operator>(const year_month_day&, const year_month_day&) noexcept;` | 左辺が右辺より大きいかを判定する (`<=>`により使用可能) | C++20 |
| `bool operator>=(const year_month_day&, const year_month_day&) noexcept;` | 左辺が右辺以上を判定する (`<=>`により使用可能) | C++20 |


### 入出力

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`operator<<`](year_month_day/op_ostream.md.nolink)   | 出力ストリームに出力する | C++20 |
| [`from_stream`](year_month_day/from_stream.md.nolink) | フォーマット指定して入力ストリームから入力する | C++20 |


## 例
```cpp example
```

### 出力
```
```

## バージョン
### 言語
- C++20

### 処理系
- [Clang](/implementation.md#clang): 8.0 (入出力ストリームなし)
- [GCC](/implementation.md#gcc): (9.2時点で実装なし)
- [Visual C++](/implementation.md#visual_cpp): (2019 Update 3時点で実装なし)
