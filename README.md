# 3shake-marp-templates

Collection of Marp-based presentation templates for [3-SHAKE](https://3-shake.com/). Features standardized designs, citation styles, Mermaid diagram support, and custom layouts for cloud-native technology and enterprise solution presentations, ensuring consistent branding and high-quality slide creation.

**Note: This is an unofficial repository. Users are encouraged to fork it for their own use. Content may be modified without prior notice.**

## 概要

このリポジトリは[株式会社スリーシェイク](https://3-shake.com/)のプレゼンテーション資料作成のための[Marp](https://marp.app/)テンプレート集です。社内外向けのプレゼンテーションで一貫したブランディングと高品質なスライド作成を支援します。

## 開発環境のセットアップ

```bash
# リポジトリをクローン
git clone https://github.com/nwiizo/3shake-marp-templates.git
cd 3shake-marp-templates

# 依存関係をインストール
npm install

# 開発サーバーを起動（http://localhost:8080）
npm start

# プレビューモードで起動
npm run preview
```

## テンプレート一覧

### メインテンプレート（templates/）
- **3shake-standard-template.md** - 標準プレゼンテーションテンプレート
- **background-template.md** - 背景画像付きテンプレート
- **basic.md** - 基本テンプレート（3-SHAKEブランディング付き）
- **with-logo.md** - ロゴ統合専用テンプレート

### サンプル・例（examples/）
- **3shake-presentation-nwiizo-edition.md** - @nwiizo カスタムテンプレート
- **3shake-standard-slides.md** - 拡張版プレゼンテーション例
- **mermaid-examples.md** - Mermaid図表の包括的な使用例
- **sample-presentation.md** - サンプルプレゼンテーション
- **title-slide.md** - タイトルスライド専用例

## テーマ

- **themes/3shake-theme.css** - 基本テーマ
- **themes/3shake-standard-theme.css** - 標準テーマ
- **themes/title-theme.css** - タイトルスライド用テーマ
- **themes/custom.css** - カスタムテーマ

## 使い方

### 新しいプレゼンテーションの作成

1. このリポジトリをフォークして自分のリポジトリとして使用することを推奨します
2. 目的に合ったテンプレートファイル（`templates/`）をコピーして新しいファイルを作成
   ```bash
   # 例：標準テンプレートをベースに新しいプレゼンテーションを作成
   cp templates/3shake-standard-template.md slides/my-presentation.md
   ```
3. テンプレートの内容を編集してプレゼンテーションを作成
4. 開発サーバーでプレビューしながら編集
   ```bash
   npm start
   # ブラウザで http://localhost:8080 にアクセス
   ```

### ファイル出力

[Marp CLI](https://github.com/marp-team/marp-cli)、[Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)、または [marp.nvim](https://github.com/nwiizo/marp.nvim) を使用してPDFやPPTXに変換できます。

```bash
# PDFへの変換
npx @marp-team/marp-cli@latest slides/my-presentation.md --pdf --allow-local-files

# PowerPointへの変換
npx @marp-team/marp-cli@latest slides/my-presentation.md --pptx --allow-local-files

# HTMLへの変換
npx @marp-team/marp-cli@latest slides/my-presentation.md --html --allow-local-files
```

### Neovim ユーザー向け (marp.nvim)

[marp.nvim](https://github.com/nwiizo/marp.nvim) プラグインを使用することで、Neovim内でMarpプレゼンテーションを効率的に作成・編集できます。

**インストール (lazy.nvim):**
```lua
{
  'nwiizo/marp.nvim',
  ft = "markdown",
  config = function()
    require("marp").setup {
      marp_command = "/path/to/marp",
      server_mode = false
    }
  end,
}
```

**主要コマンド:**
- `:MarpWatch` - ライブプレビュー開始
- `:MarpStop` - 監視停止
- `:MarpExport [format]` - プレゼンテーション出力（HTML、PDF、PPTX、PNG、JPEG対応）
- `:MarpTheme [theme]` - テーマ切り替え

**特徴:**
- 🔄 ライブプレビュー（自動リフレッシュ）
- 🛑 自動クリーンアップ（バッファクローズ時）
- 📤 マルチフォーマット出力対応
- 🎨 簡単なテーマ切り替え
- ✂️ プレゼンテーション要素用スニペット

## 高度な機能

### Mermaid図表サポート

このテンプレートは包括的なMermaid図表サポートを提供します。詳細な例は `examples/mermaid-examples.md` を参照してください。

そこまで良いものではないので画像を使用することを推奨します。

利用可能なサイズクラス：
- `.mermaid-xs` - 200px（超小）
- `.mermaid-sm` - 300px（小）
- `.mermaid-md` - 500px（中）
- `.mermaid-lg` - 700px（大）
- `.mermaid-xl` - 900px（超大）

### 引用スタイル

引用が必要な場合は、上付き文字記法を使用できます：

```markdown
これはサンプルテキストです^[1]^。さらに別の引用もあります^[2]^。

> [1] https://example.com  
> [2] https://sub.example.com
```

## カスタマイズ

テーマファイル（CSSファイル）を編集して、必要に応じてスタイルをカスタマイズできます。

## 貢献方法

1. このリポジトリをフォークします
2. 新しいブランチを作成します
3. 変更を加えてコミットします
4. プルリクエストを送信します

## ライセンス

社内用テンプレートのため、ライセンスは適用されません。このリポジトリは非公式であり、予告なく変更される可能性があります。

## 連絡先

質問や提案がある場合は、社内のコミュニケーションチャネルでお問い合わせください。
