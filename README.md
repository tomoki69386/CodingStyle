# Swiftコーディング規約

# 目次

-[命名規則](#命名規則)
-[ファイルフォーマット](#ファイルフォーマット)
-[アクセス制御](#アクセス制御)
-[変数](#変数)
-[型](#型)
-[制御構文](#制御構文)

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
let HogeNumber: Int
func HogeMethod() {

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

良い例

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

# ファイルフォーマット
以下の順に書く。

```swift
// 1
import UIKit

// 2
protocol ViewControllerdelegate {

}

// 3
class ViewController: UIViewController {

}

// 4
extension ViewController: UITableViewDelegate {

}
```

## スペース

- ブランケットの前後にはスペースを1つおく。
- メソッドの戻り値の->の前後にはスペースを1つおく。
- コロンの前にはスペースを入れず、コロンの後ろに1つスペースを入れる
- {}の前後にはスペースを1つおく。

良い例

```swift
func something(number: Int) -> Int {
    return number
}
```

悪い例

```swift
func ssomethind(number:Int)->Int{
    return number
}
```

## プロトコルの実装
ひとつのextensionで実装するプロトコルは1つとする。

良い例

```swift
class ViewController: UIViewController {

}

extension ViewController: UITableViewDataSource {

}

extension ViewController: UITableViewDelegate {

}
```

悪い例

```swift
class ViewController: UIViewController, UITableViewDataSource {

}
```
```swift
extension ViewController: UITableViewDataSource, UITableViewDelegate {

}
```

## enumの場所
enumは独立したファイルに宣言する。

**理由**

enumのある場所の統一

## セミコロンの使用禁止
行末のセミコロンの使用を禁止する。

**理由**

必要ない

## 条件文の()の使用禁止
条件文を()で囲わない。

**理由**

必要ない

**例**

良い例

```swift
if names.isEmpty {

}
```

悪い例

```swift
if (names.isEmpty) {

}
```

# アクセス制御

## アクセス制御
アクセス制御は可能な限りprivateを指定する。

**理由**

そのクラス内、メソッド内ということが担保でき、実装変更時の影響範囲を小さくできるため。

# 変数

## 変数・定数の宣言
var宣言を使用するのは、その値が変わる場合など明確な理由がある場合のみ。
それ以外の場合はlet宣言を使用する。

# 型
## 型推論
最大限利用する。

**理由**
シンプルなコードにするため

**例**

良い例

```swift
let name = "hoge"
let image = UIImage(named: "hoge")
view.backgroundColor = .blue
let View = UIView()

*数値を扱い場合
let int = 1
let double = 1.0
let float: Float = 1.0 //Float型にする場合は明記
```

```swift
let name: String = "hoge"
let image: UIImage = UIImage(named: "hoge")
view.backgroundColor = UIColor.blue
let View: UIView = UIVew()
```

# 制御構文

## 早期return

**例**

良い例

```swift
guard hogehoge else {
return
}
```

悪い例

```swift
if hogehoge {

} else {
return
}
```
