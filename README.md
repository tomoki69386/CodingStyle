# Swiftコーディング規約

# 目次

-[命名規則](#命名規則)

# 命名規則

## class, enum, struct, protocol
先頭を大文字とする。
(XxxYyy)

**例**

良い例

```swift
enum SomeEnum {
    
}

struct SomeStruct {

}

protocol SomeProtocol {

}
```

悪い例

```swift
enum someEnum {

}

struct someStruct {

}

protocol someProtocol {

}
```

## 変数・メソッド・enumのcase
先頭は小文字とする。
(xxxYyy)

**例**

良い例

```swift
let hogeNumber: Int
func hogeMethod() {

}

enum SomeEnum {
    case hoge
    case fuga
    case piyo
}
```

悪い例

```swift
let HomeNumber: Int
func HomeMethod() {

}

enum SomeEnum {
    case Home
    case Fuga
    case Piyo
}
```

## 頭文字語
すべて大文字またはすてべ小文字にする。

**例**

```swift
let url: URL = ...
let homeURL: URL =

let id: String = ...
let userID: String = ...
```

## extensionのファイル名
extensionのみのファイル名は**UIView+機能名.swift** とする。
extensionは機能単位でグルーピングする。

**良い例**

UIView+Boder.swift

```swift
extension UIView {

}
```

悪い例

Boder.swift

```swift
extension UIView {

}
```

# ファイフォーマット

# クラス

# プロパティ

# 変数

# 型

#  制御

# 演算子

# エラーハンドリング・オプショナル

# クロージャー

# 規約外項目
