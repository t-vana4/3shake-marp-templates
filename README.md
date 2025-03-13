# 3shake-marp-templates

Collection of Marp-based presentation templates for [3-SHAKE](https://3-shake.com/). Features standardized designs, citation styles, and custom layouts for cloud-native technology and enterprise solution presentations, ensuring consistent branding and high-quality slide creation.

**Note: This is an unofficial repository. Users are encouraged to fork it for their own use. Content may be modified without prior notice.**

## 概要

このリポジトリは[株式会社スリーシェイク](https://3-shake.com/)のプレゼンテーション資料作成のための[Marp](https://marp.app/)テンプレート集です。社内外向けのプレゼンテーションで一貫したブランディングと高品質なスライド作成を支援します。

## テンプレート一覧

- **3shake-presentation.md** - 標準プレゼンテーションテンプレート
- **3shake-standard-slides.md** - 拡張版プレゼンテーションテンプレート
- **title-slide.md** - タイトルスライド専用テンプレート
- **sample-presentation.md** - サンプルプレゼンテーション

### テンプレートディレクトリ
テンプレートディレクトリには、様々な目的に応じたテンプレートが含まれています：

- **templates/3shake-template.md** - 基本テンプレート
- **templates/3shake-logo-template.md** - ロゴ付きテンプレート
- **templates/3shake-standard-template.md** - 標準テンプレート
- **templates/background-template.md** - 背景画像テンプレート
- **examples/3shake-presentation-nwiizo-edition.md** - @nwiizo のハッピーテンプレート

## テーマ

- **themes/3shake-theme.css** - 基本テーマ
- **themes/3shake-standard-theme.css** - 標準テーマ
- **themes/title-theme.css** - タイトルスライド用テーマ
- **themes/custom.css** - カスタムテーマ

## 使い方

1. このリポジトリをフォークして自分のリポジトリとして使用することを推奨します
2. 目的に合ったテンプレートファイル（.md）をコピーして新しいファイルを作成
3. テンプレートの内容を編集してプレゼンテーションを作成
4. [Marp CLI](https://github.com/marp-team/marp-cli) または [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) を使用してPDFやPPTXに変換

### Marp CLIでの変換例

```bash
# PDFへの変換
npx @marp-team/marp-cli@latest 3shake-presentation.md --pdf --allow-local-files

# PowerPointへの変換
npx @marp-team/marp-cli@latest 3shake-presentation.md --pptx --allow-local-files
```

## 引用スタイル

引用が必要な場合は、次のように記述できます：

```markdown
これはサンプルテキストです$^{[1]}$。さらに別の引用もあります$^{[2]}$。

> [1] https://example.com  
> [2] https://sub.example.com
```

引用はスライドの下部に自動的に表示されます。

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