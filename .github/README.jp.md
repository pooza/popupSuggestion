# PopupSuggestion

PopupSuggestion は、特定のトリガーキー（デフォルトは `#`）が入力フィールドまたはテキストエリア内で押されると、オートサジェストポップアップを提供する軽量なバニラ JavaScript ライブラリです。サジェストは JSON ファイルから取得され、スタイル付きのポップアップに表示されます。

![PopupSuggestion Demo](https://popup-suggestion-gif.rabinsonthapa.me/)

## 特徴

- 任意の入力フィールドまたはテキストエリアをサポート。
- 色、フォント、ボーダー、サイズなど、カスタマイズ可能なスタイル。
- キーボードでのナビゲーション（`ArrowUp`、`ArrowDown`、`Enter`、`Escape`）に対応。
- ユーザーの入力に基づいてサジェストが動的にフィルタリングされます。
- 項目間にオプションでボーダーを表示（ボーダーの色をカスタマイズ可能）。

## インストール

npm を使用してパッケージをインストールできます：

```sh
npm install popup-suggestion
```

## 使い方

### モジュールをインポート（ES6 モジュール使用時）

```javascript
import PopupSuggestion from "popup-suggestion";
```

### PopupSuggestion の初期化

```javascript
const popup = new PopupSuggestion("path/to/data.json", {
  triggerKey: "#",
  fontSize: "14px",
  color: "white",
  backgroundColor: "#0e1116",
  borderRadius: "7px",
  hoverColor: "#386ee3",
  showBorders: true,
  borderColor: "#ccc",
  width: "300px",
  height: "200px",
  textOverflow: "wrap",
});
```

### JSON データ形式

JSON ファイルは、`id` と `title` フィールドを含むオブジェクトの配列である必要があります：

```json
[
  { "id": "123", "title": "最初のサジェスト" },
  { "id": "124", "title": "二番目のサジェスト" }
]
```

## オプション

コンストラクタは、外観や動作をカスタマイズするためのオプションの `options` オブジェクトを受け取ります。

### 必須パラメータ

| 名前      | 型     | 説明                                             |
| --------- | ------ | ------------------------------------------------ |
| `jsonUrl` | 文字列 | サジェストを含む JSON ファイルのパスまたは URL。 |

### オプションのパラメータ

| 名前              | 型     | デフォルト値           | 説明                                                       |
| ----------------- | ------ | ---------------------- | ---------------------------------------------------------- |
| `triggerKey`      | String | `#`                    | ポップアップをトリガーするキー。                           |
| `fontSize`        | String | `12px`                 | サジェストのフォントサイズ。                               |
| `color`           | String | `white`                | テキストの色。                                             |
| `backgroundColor` | String | `#0e1116`              | ポップアップの背景色。                                     |
| `borderRadius`    | String | `7px`                  | ポップアップのボーダー半径。                               |
| `hoverColor`      | String | `#386ee3`              | ホバーした項目の背景色。                                   |
| `showBorders`     | String | `true`                 | 項目間にボーダーを表示するかどうか。                       |
| `borderColor`     | String | テキストの色の明るい色 | 項目のボーダーの色。                                       |
| `width`           | String | `300px`                | ポップアップの最大幅。                                     |
| `height`          | String | `200px`                | ポップアップの最大高さ。                                   |
| `textOverflow`    | String | `wrap`                 | テキストのオーバーフローの方法（`wrap`または`ellipsis`）。 |

## キーボードショートカット

| キー                      | アクション                                         |
| ------------------------- | -------------------------------------------------- |
| `#`（またはカスタムキー） | ポップアップを開く。                               |
| `ArrowUp`                 | 上に移動する。                                     |
| `ArrowDown`               | 下に移動する。                                     |
| `Enter`                   | ハイライトされた項目を選択する。                   |
| `Escape`                  | ポップアップを閉じる。                             |
| `Backspace`               | ユーザーの入力に基づいてフィルタリングを更新する。 |

## ライセンス

このパッケージは MIT ライセンスの下で提供されています。
