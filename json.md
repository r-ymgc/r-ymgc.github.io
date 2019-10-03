# JSONとは
JSON(JavaScript Object Notation):
JavaScriptの「オブジェクト」のデータ定義の書き方をそのまま抜き出した、構造的データを表現するテキストフォーマット。
JavaScriptだけでなく、あらゆる言語間のデータ交換や、設定ファイルの記述に使用されています。

似たようデータ構造を表現するフォーマットとして、YAML, XML, INI, CSVなどがありますが、
JSONの特徴として、

- JavaScriptの記法と同じなので、プログラマにとって扱いやすい
- 階層構造を表現できる
- 階層構造が必須ではない
- コメントアウトができない

などがあります。

---

## 基本文法
前提として、すべてのデータはキーバリューの形式で記述します。
まず、基本から・・・

- キーと値を:(コロン)で区切る
- キーと値(文字列)は""(ダブルクォート)で囲う※シングルクォートはNG
- その外側を{}(波カッコ)で囲う

```json:example
{"key": "value"}
```

---

複数の要素を定義するときは,(カンマ)で区切る

```json:example
{"key1": "value1", "key2": "value2"}
```

:point_up: これが「オブジェクト」の書き方

```json:example
{
    "key1": "value1",
    "key2": "value2"
}
```

:point_up: 改行とインデントは無視されるので、見やすくするために適宜入れます。

---

## データ型
オブジェクトの値として、いくつかのデータ型を扱えます。

- 文字列
- 数値
- null
- 真偽値(true/false)
- 配列(リスト)
- オブジェクト

---

### ■ 文字列
値を""(ダブルクォート)で囲うと文字列として扱われます。

```json:example
{"title": "This is string.", "message": "This is string too."}
```

### ■ 数値
数字のみの値をダブルクォートで囲わなかった場合、数値として扱われます。
小数も扱えます。

```json:example
{"id": 10001, "level": 20, "point": 10.25}
```

---

### ■ null
値が存在しないことを表すnull型も表現できます。
すべて半角英子文字で「null」以外はNG

```json:example
{"name": "John", "plan": null}
```

### ■ 真偽値(true/false)
フラグなどに使われる真偽値も扱えます。
すべて半角英子文字で「true」or「false」以外はNG

```json:example
{"isValid": true, "enable": false}
```

---

### ■ 配列(リスト)
一つのキーに対して複数の要素を定義したい場合、配列を使います。

```json:example
{"names": ["John", "Mike", "Jack"]}
```

配列の値にはすべてのデータ型が利用できます。

```json:example
{
    "colors": ["red", "green", "blue"],
    "nums": [123, 456, 789],
    "mix": ["red", 456, null, true],
    "list_in_list": [[12, 23], [34, 45], [56, 67]],
    "objects": [
        {"name": "Tanaka", "age": 26},
        {"name": "Suzuki", "age": 32}
    ]
}
```

---

### ■ オブジェクトのネスト(入れ子)
オブジェクトの値にオブジェクトを定義することもできます。

```json:example
{
    "status": 200,
    "contents": {
        "title": "news",
        "body": "This is body in article."
    },
    "datetime": "20190602 12:22:00"
}
```

たったこれだけ！簡単ですね！
Let's Enjoy JSON！ :grinning:
