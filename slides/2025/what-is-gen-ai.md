---
marp: true
theme: ../../themes/3shake-theme.css
paginate: true
math: mathjax
style: |
  :root {
    --logo-url: url("../../assets/images/3shake-cover.png");
    --mini-font-size: 20px;
    --header-footer-height: 50px;
    --black: #333;
  }
  /* Add highlight-red class */
  .highlight-red {
    color: rgb(224, 64, 64);
  }
  /* 通常ページの左下にロゴを表示（より左下に押し込む） */
  section:not(.title)::before {
    content: "";
    position: absolute;
    left: 15px;  /* より左に */
    bottom: 15px;  /* より下に */
    width: 60px !important;  /* ロゴサイズを調整 */
    height: 60px !important;  /* ロゴサイズを調整 */
    background-image: var(--logo-url);
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    opacity: 0.9;
    z-index: 100;
  }
  /* 背景色付きスライドではロゴ色を反転 */
  section[data-background-color="dark"]::before {
    filter: brightness(0) invert(1);
  }
  /* タイトルページのページ番号を非表示 */
  section.title::after {
    display: none;
  }
  /* タイトルスライドのロゴスタイル */
  .title-logo {
    position: fixed;
    top: 5px;
    left: 5px;
    width: 240px !important;
    height: auto;
    z-index: 9999;
  }
  /* すべての画像サイズを上書き - 3shake-logo.pngのみに適用 */
  img[src*="3shake-logo.png"] {
    max-width: 240px !important;
    width: 240px !important;
  }
  /* タイトルとサブタイトルのサイズ調整 */
  .title h1 {
    font-size: 2.4em !important;
    margin-bottom: 0.1em !important;
  }
  .title h3 {
    font-size: 1.1em !important;
    margin-top: 0.1em !important;
  }
  /* 作者情報のスタイル */
  .author-info {
    position: absolute !important;
    bottom: 40px !important;
    left: 100px !important;
    padding-left: 0 !important;
    text-indent: 0 !important;
    font-size: 0.9em !important;
    color: white !important;
    font-weight: bold !important;
  }
  /* スライドタイトル（h2）のスタイル */
  section h2 {
    font-size: 1.8em !important;
    margin-top: -25px !important;
    padding-top: 0 !important;
    margin-bottom: 10px !important;
    color: #434343;
    border-bottom: 1px solid #dadce0 !important;
  }
  /* コンテンツエリアの上部マージンを調整 */
  section > *:not(h2):not(header):not(footer) {
    margin-top: 1.2em !important;
  }
  /* 本文の基本書式（上揃え＆文字色濃いグレー＆フォントサイズ */
  section:not(.title) {
    align-content: start;
    color: #434343;
    font-size: 24px;
  }
  /* 引用（参考文献）のスタイル */
  blockquote {
    border-top: 0.1em dashed var(--black);
    font-size: var(--mini-font-size);
    width: 100%;
    position: absolute;
    bottom: var(--header-footer-height);
    left: 0;
    padding: 10px 20px;
    margin: 0;
    box-sizing: border-box;
  }
  /* 参考文献用のスタイル */
  .reference-right {
    font-size: 0.4em;
    text-align: right;
    margin-right: 20px;
    margin-top: -15px;
    display: block;
    width: 30%;
    margin-left: 70%;
  }
---

<!-- 
_backgroundColor: #0a1929
_color: white
_class: title dark
-->

![bg](../../assets/images/3shake-background-full.png)

<img src="../../assets/images/3shake-logo.png" alt="3-SHAKE logo" style="position: absolute !important; top: 100px !important; left: 100px !important; width: 240px !important; height: auto !important; z-index: 9999 !important;">

<div class="title" style="text-align: left; margin-top: 100px; margin-left: 20px; padding-left: 0; max-width: 70%;">

# <span style="font-size: 0.7em;">なれる！Generative AI Leader</span>

</div>

<div class="author-info" style="text-align: left; padding-left: 0; text-indent: 0;">
Hajime Tachibana
</div>

---

## 本日のゴール

<div style="font-size: 0.95em;">

この研修を通じて、以下のことを目指します：

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 20px; margin: 30px 0;">

<div style="background: linear-gradient(135deg, #e3f2fd 0%, #bbdefb 100%); padding: 25px; border-radius: 12px; border-left: 5px solid #1976d2;">
<div style="font-size: 2em; text-align: center; margin-bottom: 10px;">📚</div>
<div style="font-weight: bold; color: #1976d2; font-size: 1.1em; margin-bottom: 10px; text-align: center;">理解する</div>
<div style="font-size: 0.9em;">
生成AIとは何か、どんな能力があるのかを理解する
</div>
</div>

<div style="background: linear-gradient(135deg, #fff3e0 0%, #ffe0b2 100%); padding: 25px; border-radius: 12px; border-left: 5px solid #f57c00;">
<div style="font-size: 2em; text-align: center; margin-bottom: 10px;">🛠️</div>
<div style="font-weight: bold; color: #f57c00; font-size: 1.1em; margin-bottom: 10px; text-align: center;">使いこなす</div>
<div style="font-size: 0.9em;">
効果的なプロンプトの書き方と、上手な活用方法を学ぶ
</div>
</div>

<div style="background: linear-gradient(135deg, #e8f5e9 0%, #c8e6c9 100%); padding: 25px; border-radius: 12px; border-left: 5px solid #388e3c;">
<div style="font-size: 2em; text-align: center; margin-bottom: 10px;">🚀</div>
<div style="font-weight: bold; color: #388e3c; font-size: 1.1em; margin-bottom: 10px; text-align: center;">実践する</div>
<div style="font-size: 0.9em;">
今日から業務で活用できる自信を持つ
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.2em; font-weight: bold;">
研修後には「生成AIを使ってみよう！」と思える状態に
</div>

</div>

---

## 目次

1. 「生成AI」とは何か？
   
2. 生成AIに関する基礎知識

3. Google Geminiを使ってみよう

4. 生成AIをより上手に使うために

5. まとめ

---

## 目次

1. 「生成AI」とは何か？
   
2. <font color=#E5E8EA>生成AIに関する基礎知識</font>

3. <font color=#E5E8EA>Google Geminiを使ってみよう</font>

4. <font color=#E5E8EA>生成AIをより上手に使うために</font>

5. <font color=#E5E8EA>まとめ</font>

---

## まずは全体像を理解しよう

**生成AI**を理解するには、AI技術全体の中での位置づけを知ることが大切です。

これから、以下の3つのポイントで解説します：

1. **AI技術の階層関係** 〜 生成AIはどこに位置する？
2. **生成AIの定義と4つの能力** 〜 何ができるの？
3. **マルチモーダル** 〜 テキストだけじゃない！

---

## AI技術の階層関係

<div style="text-align: center; margin: 30px auto;">

<div style="background: #e3f2fd; border: 3px solid #1976d2; border-radius: 15px; padding: 25px; margin: 10px auto; max-width: 85%;">
<div style="font-size: 1.4em; font-weight: bold; color: #1976d2;">🌐 AI（人工知能）</div>
<div style="font-size: 0.85em; margin-top: 5px; color: #434343;">最も広い概念</div>

<div style="background: #fff3e0; border: 3px solid #f57c00; border-radius: 12px; padding: 20px; margin: 15px auto; max-width: 90%;">
<div style="font-size: 1.25em; font-weight: bold; color: #f57c00;">🧠 機械学習（ML）</div>

<div style="background: #fce4ec; border: 3px solid #c2185b; border-radius: 10px; padding: 15px; margin: 12px auto; max-width: 90%;">
<div style="font-size: 1.1em; font-weight: bold; color: #c2185b;">🔬 ディープラーニング</div>

<div style="background: #e8f5e9; border: 4px solid #388e3c; border-radius: 8px; padding: 12px; margin: 10px auto; max-width: 90%;">
<div style="font-size: 1.0em; font-weight: bold; color: #388e3c;">✨ 生成AI</div>
</div>
</div>
</div>
</div>

</div>

<div style="font-size: 0.85em; margin-top: 20px; text-align: center;">

**マトリョーシカ人形**のように、各技術が入れ子構造になっています。

</div>

---

## それぞれの技術の役割

<div style="font-size: 0.95em;">

| 技術 | 説明 |
|------|------|
| **AI（人工知能）** | 人間の知能を必要とするタスクを実行できる<br/>システムの総称（最も広い概念） |
| **機械学習（ML）** | データから自動的に学習し、<br/>パターンを見つけ出す技術 |
| **ディープラーニング** | 脳の神経回路を模した多層構造で<br/>複雑なパターンを抽出する技術 |
| **生成AI** | **新しいコンテンツを作成**することに<br/>特化したAIの応用分野 |

</div>

---

## 生成AIとは？

<div style="text-align: center; margin: 40px 0;">
<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 30px; border-radius: 15px; font-size: 1.3em; font-weight: bold; box-shadow: 0 4px 15px rgba(0,0,0,0.2);">
新しいコンテンツやアイデアを<br/>作成できるAIの一種
</div>
</div>

<br>

**ポイント**：既存のデータを分析・予測するだけでなく、  
**全く新しいもの**を「生成」できるのが最大の特徴です。

---

## 生成AIの4つの能力

生成AIには、主に**4つの能力**があります：

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 30px; font-size: 0.9em;">

<div style="background: #e3f2fd; padding: 20px; border-radius: 10px; border-left: 5px solid #1976d2;">
<strong>1. 作成（Create）</strong><br/>
まったく新しいコンテンツを生成
</div>

<div style="background: #fff3e0; padding: 20px; border-radius: 10px; border-left: 5px solid #f57c00;">
<strong>2. 要約（Summarize）</strong><br/>
長い情報を簡潔にまとめる
</div>

<div style="background: #fce4ec; padding: 20px; border-radius: 10px; border-left: 5px solid #c2185b;">
<strong>3. 自動化（Automate）</strong><br/>
定型的なタスクを自動化
</div>

<div style="background: #e8f5e9; padding: 20px; border-radius: 10px; border-left: 5px solid #388e3c;">
<strong>4. 発見（Discover）</strong><br/>
必要な情報を迅速に発見
</div>

</div>

---

## 1. 作成（Create）

<div style="font-size: 0.95em;">

**文章、画像、コード、音楽など、まったく新しいコンテンツをゼロから生成します。**

<br>

### 具体例

- 📝 **マーケティング**：新商品のキャッチコピーを考える
- 🎨 **デザイン**：製品デザインのコンセプト画像を生成する
- 💻 **プログラミング**：特定の機能を実現するコードを作成する
- 🎵 **音楽**：雰囲気に合ったBGMを作曲する

<br>

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px; border-left: 5px solid #388e3c;">
💡 <strong>あなたの「創造的パートナー」として活躍！</strong>
</div>

</div>

---

## 2. 要約（Summarize）

<div style="font-size: 0.95em;">

**長いレポートや会議の議事録などを、要点を押さえた簡潔な文章にまとめます。**

<br>

### 具体例

- 📄 **長文レポート**：100ページの報告書を3ページに要約
- 📰 **ニュース記事**：長いニュース記事を3行で要約
- 💬 **会議議事録**：2時間の会議内容を決定事項中心にまとめる
- 📧 **メールの山**：大量のメールから重要な情報だけを抽出

<br>

<div style="background: #fff3e0; padding: 15px; border-radius: 8px; border-left: 5px solid #f57c00;">
💡 <strong>情報過多の時代に、あなたの「時間」を取り戻す！</strong>
</div>

</div>

---

## 3. 自動化（Automate）

<div style="font-size: 0.95em;">

**これまで手作業で行っていた定型的なタスクを自動化し、業務効率を向上させます。**

<br>

### 具体例

- ✉️ **顧客対応**：問い合わせメールへの返信文案を自動作成
- 📊 **レポート作成**：データから定型レポートを自動生成
- 📝 **文書整理**：社内文書の分類やタグ付けを自動化
- 🔄 **データ変換**：異なる形式のデータを一括変換

<br>

<div style="background: #fce4ec; padding: 15px; border-radius: 8px; border-left: 5px solid #c2185b;">
💡 <strong>ルーチンワークから解放され、本当に大切な仕事に集中！</strong>
</div>

</div>

---

## 4. 発見（Discover）

<div style="font-size: 0.95em;">

**膨大なデータの中から必要な情報を迅速に見つけ出し、適切なタイミングで提供します。**

<br>

### 具体例

- 🔍 **社内ナレッジ検索**：過去のプロジェクト資料から類似事例を発見
- 👥 **専門家発見**：特定の知識を持つ社員を瞬時に特定
- 📚 **関連情報の提示**：現在の作業に関連する参考資料を提案
- 🎯 **パターン分析**：データから隠れたトレンドを発見

<br>

<div style="background: #e3f2fd; padding: 15px; border-radius: 8px; border-left: 5px solid #1976d2;">
💡 <strong>組織の知識を「使える資産」に変える！</strong>
</div>

</div>

---

## マルチモーダル：テキストの壁を超える力

<div style="font-size: 0.9em;">

現代の生成AIは**マルチモーダル**（複数のデータ形式を扱える）能力を持っています。

<br>

<div style="display: flex; justify-content: center; align-items: center; gap: 30px; margin: 30px 0;">

<div style="background: #e8f5e9; border: 3px solid #388e3c; border-radius: 15px; padding: 20px; text-align: center; min-width: 120px;">
<div style="font-size: 1.5em;">👤</div>
<div style="font-weight: bold; color: #388e3c; margin-top: 5px;">ユーザー</div>
</div>

<div style="font-size: 2em; color: #667eea;">⇄</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); border-radius: 15px; padding: 25px; text-align: center; min-width: 140px;">
<div style="font-size: 1.5em; color: white;">🤖</div>
<div style="font-weight: bold; color: white; margin-top: 5px; font-size: 1.2em;">生成AI</div>
</div>

<div style="font-size: 2em; color: #667eea;">⇄</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 10px;">
<div style="background: #e3f2fd; border: 2px solid #1976d2; border-radius: 10px; padding: 12px; text-align: center;">
<div style="font-size: 1.2em;">📝</div>
<div style="font-size: 0.85em; font-weight: bold; color: #1976d2;">テキスト</div>
</div>
<div style="background: #fff3e0; border: 2px solid #f57c00; border-radius: 10px; padding: 12px; text-align: center;">
<div style="font-size: 1.2em;">🖼️</div>
<div style="font-size: 0.85em; font-weight: bold; color: #f57c00;">画像</div>
</div>
<div style="background: #fce4ec; border: 2px solid #c2185b; border-radius: 10px; padding: 12px; text-align: center;">
<div style="font-size: 1.2em;">🔊</div>
<div style="font-size: 0.85em; font-weight: bold; color: #c2185b;">音声</div>
</div>
<div style="background: #f3e5f5; border: 2px solid #7b1fa2; border-radius: 10px; padding: 12px; text-align: center;">
<div style="font-size: 1.2em;">💻</div>
<div style="font-size: 0.85em; font-weight: bold; color: #7b1fa2;">コード</div>
</div>
</div>

</div>

<br>

**テキスト、画像、音声、コード**を同時に理解・生成できる = より人間らしい対話が可能に！

</div>

---

## マルチモーダルの実例

<div style="font-size: 0.95em;">

### 具体的な使い方の例

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; margin: 15px 0;">

**建築家の例**  
ラフスケッチ（画像）をAIに見せて...

「このデザインに基づいた3Dモデルと、  
クライアント向けの説明文を作成して」

→ **画像入力** → **3Dモデル + テキスト出力**

</div>

<br>

このように、**複数の形式を組み合わせた創造的なワークフロー**が実現可能に！

</div>

---

## 第1章のまとめ

<div style="font-size: 0.95em;">

### 「生成AI」とは何か？

<br>

✅ **生成AI**は、AI技術の中でも「新しいコンテンツを作る」ことに特化

✅ **4つの能力**：作成、要約、自動化、発見

✅ **マルチモーダル**：テキストだけでなく、画像・音声・コードも扱える

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
生成AIは、あなたの仕事を支援する<br/>「万能アシスタント」です！
</div>

</div>

---

## 目次

1. <font color=#E5E8EA>「生成AI」とは何か？</font>
   
2. 生成AIに関する基礎知識

3. <font color=#E5E8EA>Google Geminiを使ってみよう</font>

4. <font color=#E5E8EA>生成AIをより上手に使うために</font>

5. <font color=#E5E8EA>まとめ</font>

---

## 第2章で学ぶこと

生成AIがどのように機能しているのか、その舞台裏にある重要な構成要素を理解します。

### 3つの柱

1. **モデル** 〜 AIの「頭脳」とは？
2. **データ** 〜 AIの「賢さ」の源泉
3. **プロンプト** 〜 AIとの「対話術」

<div style="background: #e3f2fd; padding: 15px; border-radius: 8px; border-left: 5px solid #1976d2; margin-top: 25px;">
💡 この3つを理解することで、AIの能力を最大限に引き出せるようになります！
</div>

---

## AIの頭脳：「モデル」とは？

<div style="font-size: 0.95em;">

生成AIの中核をなすのが**モデル**と呼ばれる、複雑なアルゴリズムの集合体です。

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; margin-bottom: 10px;">🧠 モデル = AIの「脳」</div>
データから学習し、新しいコンテンツを生成する能力を持つ
</div>

<br>

特に重要なのが以下の2つの概念です：
- **基盤モデル**（Foundation Model）
- **大規模言語モデル**（LLM：Large Language Model）

</div>

---

## 基盤モデル（Foundation Model）

<div style="font-size: 0.9em;">

<div style="background: #fff3e0; border-left: 5px solid #f57c00; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-size: 1.1em; font-weight: bold; color: #f57c00; margin-bottom: 10px;">📚 基盤モデルとは</div>

大量のデータで事前にトレーニングされた、非常に大規模なAIモデル

特定のタスクに特化せず、**幅広い知識と能力**を持つ汎用的な土台
</div>

<br>

### 特徴

✅ **広範な知識**：インターネット上の膨大なデータから自律的に学習  
✅ **汎用性**：様々な用途に応用可能  
✅ **自己学習**：人間が正解ラベルを付けなくても学習できる

<br>

<div style="font-size: 0.85em; text-align: center; color: #666;">
例：GPT、Gemini、Claudeなど
</div>

</div>

---

## 大規模言語モデル（LLM）

<div style="font-size: 0.9em;">

<div style="background: #e8f5e9; border-left: 5px solid #388e3c; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-size: 1.1em; font-weight: bold; color: #388e3c; margin-bottom: 10px;">💬 LLMとは</div>

基盤モデルの一種で、特に**人間の言語（テキスト）**の理解と生成に特化したモデル
</div>

<br>

### できること

✅ **文章の作成**：レポート、メール、記事など  
✅ **要約**：長文を短くまとめる  
✅ **翻訳**：多言語間の翻訳  
✅ **質問応答**：質問に対して適切な回答を生成

<br>

<div style="background: #e3f2fd; padding: 12px; border-radius: 6px; text-align: center; font-weight: bold;">
基盤モデル = 汎用的な土台 ｜ LLM = 言語能力を極めた専門家
</div>

</div>

---

## 学習の仕組み：モデルはどうやって賢くなる？

<div style="font-size: 0.9em;">

モデルが賢くなるプロセスは**「学習」または「トレーニング」**と呼ばれます。

<br>

### 主な学習アプローチ

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 15px; margin-top: 20px; font-size: 0.9em;">

<div style="background: #e3f2fd; padding: 15px; border-radius: 10px; border-top: 5px solid #1976d2;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px;">📖 教師あり学習</div>
<div style="font-size: 0.85em;">
問題と正解のセットで学習<br/>
<span style="color: #666;">例：画像認識</span>
</div>
</div>

<div style="background: #fff3e0; padding: 15px; border-radius: 10px; border-top: 5px solid #f57c00;">
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px;">🔍 教師なし学習</div>
<div style="font-size: 0.85em;">
データから自動的にパターンを発見<br/>
<span style="color: #666;">基盤モデルで使用</span>
</div>
</div>

<div style="background: #fce4ec; padding: 15px; border-radius: 10px; border-top: 5px solid #c2185b;">
<div style="font-weight: bold; color: #c2185b; margin-bottom: 8px;">🎮 強化学習</div>
<div style="font-size: 0.85em;">
試行錯誤で良い行動を学習<br/>
<span style="color: #666;">例：ゲームAI</span>
</div>
</div>

</div>

</div>

---

## データの重要性：「質」がすべてを決める

<div style="font-size: 0.9em;">

<div style="background: #fff3e0; border: 3px solid #f57c00; padding: 20px; border-radius: 12px; margin: 20px 0; text-align: center;">
<div style="font-size: 1.5em; font-weight: bold; color: #f57c00; margin-bottom: 10px;">
⚠️ Garbage In, Garbage Out
</div>
<div style="font-size: 1.1em;">
ゴミを入れれば、ゴミしか出てこない
</div>
</div>

<br>

### 高品質なデータの条件

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin-top: 15px; font-size: 0.9em;">

<div style="background: #e3f2fd; padding: 15px; border-radius: 8px;">
✅ **正確性**<br/>データに誤りがないこと
</div>

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px;">
✅ **完全性**<br/>必要な情報が欠けていないこと
</div>

<div style="background: #fce4ec; padding: 15px; border-radius: 8px;">
✅ **整合性**<br/>データ間で矛盾がないこと
</div>

<div style="background: #f3e5f5; padding: 15px; border-radius: 8px;">
✅ **関連性**<br/>課題に対して適切なデータであること
</div>

</div>

</div>

---

## データの質が低いとどうなる？

<div style="font-size: 0.9em;">

質の低いデータで学習したモデルには、重大な問題が発生します。

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 20px;">

<div style="background: #ffebee; border-left: 5px solid #d32f2f; padding: 20px; border-radius: 8px;">
<div style="font-size: 1.1em; font-weight: bold; color: #d32f2f; margin-bottom: 10px;">❌ 不正確な回答</div>
誤った情報や事実でない内容を生成してしまう
</div>

<div style="background: #fff3e0; border-left: 5px solid #f57c00; padding: 20px; border-radius: 8px;">
<div style="font-size: 1.1em; font-weight: bold; color: #f57c00; margin-bottom: 10px;">⚠️ バイアスの増幅</div>
社会的な偏見や差別的な内容を反映・増幅してしまう
</div>

</div>

<br>

<div style="background: #e3f2fd; padding: 20px; border-radius: 10px; text-align: center; font-weight: bold; color: #1976d2;">
💡 高品質なデータこそが、高性能で公正なAIモデルを生み出す最も重要な資源！
</div>

</div>

---

## AIとの対話術：「プロンプト」とは？

<div style="font-size: 0.9em;">

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; margin-bottom: 10px;">💬 プロンプトとは</div>
AIに指示を与え、望む結果を引き出すための<br/>「入力」や「命令」のこと
</div>

<br>

### プロンプトの重要性

単に質問を投げかけるだけでなく、**どのように指示するか**で、AIの応答は劇的に変わります！

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9em;">

<div style="background: #ffebee; padding: 15px; border-radius: 8px;">
❌ <strong>あいまいな指示</strong><br/>
「生成AIについて教えて」
</div>

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px;">
✅ <strong>具体的な指示</strong><br/>
「生成AIのメリットを、初心者向けに3つ、箇条書きで教えて」
</div>

</div>

</div>

---

## プロンプトエンジニアリング

<div style="font-size: 0.9em;">

効果的なプロンプトを作成し、モデルの価値を最大限に引き出す技術を  
**「プロンプト エンジニアリング」**と呼びます。

<br>

<div style="background: #e8f5e9; border-left: 5px solid #388e3c; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 10px;">🎯 良いプロンプトのポイント</div>

✅ **具体的**：何をしてほしいか明確に  
✅ **形式を指定**：箇条書き、表形式など  
✅ **役割を与える**：「あなたは〇〇の専門家です」  
✅ **例を示す**：期待する出力の例を提示

</div>

<br>

<div style="text-align: center; font-weight: bold; color: #667eea; font-size: 1.1em;">
プロンプトエンジニアリングは、これからの時代の重要なスキル！
</div>

</div>

---

## 良いプロンプトの例①：レポート作成

<div style="font-size: 0.85em;">

<div style="background: #ffebee; border: 2px solid #d32f2f; padding: 15px; border-radius: 8px; margin: 15px 0;">
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 8px;">❌ 悪い例</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.95em;">
「AI活用について書いて」
</div>
</div>

<div style="background: #e8f5e9; border: 2px solid #388e3c; padding: 15px; border-radius: 8px; margin: 15px 0;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px;">✅ 良い例</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.9em; line-height: 1.6;">
あなたは経験豊富なITコンサルタントです。<br/>
【依頼内容】<br/>
中小企業向けに、生成AIの業務活用について説明するレポートを作成してください。<br/>
【形式】<br/>
• 見出しは「1. 〇〇」「2. 〇〇」の形式<br/>
• 各セクションは200文字程度・・・<br/>
【含めてほしい内容】<br/>
1. 生成AIとは何か<br/>
2. 中小企業にとってのメリット・・・<br/>
</div>
</div>

</div>

---

## 良いプロンプトの例②：データ分析

<div style="font-size: 0.85em;">

<div style="background: #ffebee; border: 2px solid #d32f2f; padding: 15px; border-radius: 8px; margin: 15px 0;">
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 8px;">❌ 悪い例</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.95em;">
「この数字を分析して」
</div>
</div>

<div style="background: #e8f5e9; border: 2px solid #388e3c; padding: 15px; border-radius: 8px; margin: 15px 0;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px;">✅ 良い例</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.9em; line-height: 1.6;">
あなたはデータアナリストです。<br/>
【データ】<br/>
• 1月売上：500万円、2月：450万円、3月：600万円<br/>
• 1月訪問者：1000人、2月：900人、3月：1200人<br/>
【分析してほしいこと】<br/>
1. 月ごとの売上トレンド<br/>
2. 1人あたりの購入単価の変化・・・<br/>
【出力形式】<br/>
• 箇条書きで簡潔に<br/>
• 数値は必ず記載・・・<br/>
</div>
</div>

</div>

---

## プロンプト作成のコツ

<div style="font-size: 0.9em;">

実例から学ぶ、効果的なプロンプトの共通点：

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin: 20px 0;">

<div style="background: #e3f2fd; border-left: 5px solid #1976d2; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 10px;">📋 構造化する</div>
【役割】【依頼内容】【形式】など、セクションに分けて整理
</div>

<div style="background: #fff3e0; border-left: 5px solid #f57c00; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #f57c00; margin-bottom: 10px;">🎯 具体的な数値</div>
「短く」ではなく「200文字程度」のように具体的に指定
</div>

<div style="background: #fce4ec; border-left: 5px solid #c2185b; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #c2185b; margin-bottom: 10px;">👤 役割設定</div>
「あなたは〇〇です」と専門家の役割を明確に
</div>

<div style="background: #e8f5e9; border-left: 5px solid #388e3c; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 10px;">✨ 期待値を明示</div>
何を、どのように、どの程度出力してほしいか明確に
</div>

</div>

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
💡 最初は悪い例でも大丈夫！試しながら改善していきましょう
</div>

</div>

---

## 第2章のまとめ

<div style="font-size: 0.95em;">

### 生成AIを動かす3つの柱

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 15px; margin: 20px 0;">

<div style="background: #e3f2fd; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #1976d2;">
<div style="font-size: 2em; margin-bottom: 10px;">🧠</div>
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px;">モデル</div>
<div style="font-size: 0.85em;">基盤モデルとLLM<br/>AIの「頭脳」</div>
</div>

<div style="background: #fff3e0; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #f57c00;">
<div style="font-size: 2em; margin-bottom: 10px;">📊</div>
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px;">データ</div>
<div style="font-size: 0.85em;">質がすべてを決める<br/>AIの「栄養」</div>
</div>

<div style="background: #e8f5e9; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #388e3c;">
<div style="font-size: 2em; margin-bottom: 10px;">💬</div>
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px;">プロンプト</div>
<div style="font-size: 0.85em;">AIとの対話術<br/>能力を引き出す鍵</div>
</div>

</div>

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
この3つを理解すれば、生成AIを効果的に使いこなせます！
</div>

</div>

---

## 目次

1. <font color=#E5E8EA>「生成AI」とは何か？</font>
   
2. <font color=#E5E8EA>生成AIに関する基礎知識</font>

3. Google Geminiを使ってみよう

4. <font color=#E5E8EA>生成AIをより上手に使うために</font>

5. <font color=#E5E8EA>まとめ</font>

---

## 第3章で学ぶこと

実際にGoogle Geminiを使いながら、生成AIの基本操作を体験します。

### この章のポイント

1. **Geminiにアクセスする** 〜 すぐに始められる
2. **最初の質問をしてみる** 〜 基本的な使い方
3. **プロンプトを改善する** 〜 より良い回答を得るために
4. **実践演習** 〜 業務で使えるシーンを体験

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px; border-left: 5px solid #388e3c; margin-top: 25px;">
💡 このセクションでは、実際に手を動かしながら学びます！
</div>

---

## Google Geminiとは？

<div style="font-size: 0.95em;">

<div style="background: linear-gradient(135deg, #4285f4 0%, #34a853 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; margin-bottom: 10px;">🌟 Google Gemini</div>
Googleが開発した最新の生成AI  
Googleアカウントがあれば無料ですぐに使える
</div>

<br>

### Geminiの特徴

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin-top: 20px;">

<div style="background: #e8f5e9; padding: 20px; border-radius: 10px; border-left: 5px solid #388e3c;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 10px;">✅ 無料で利用可能</div>
Googleアカウントだけで始められる
</div>

<div style="background: #e3f2fd; padding: 20px; border-radius: 10px; border-left: 5px solid #1976d2;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 10px;">✅ 日本語対応</div>
自然な日本語で会話できる
</div>

<div style="background: #fff3e0; padding: 20px; border-radius: 10px; border-left: 5px solid #f57c00;">
<div style="font-weight: bold; color: #f57c00; margin-bottom: 10px;">✅ マルチモーダル</div>
テキスト、画像、コードに対応
</div>

<div style="background: #fce4ec; padding: 20px; border-radius: 10px; border-left: 5px solid #c2185b;">
<div style="font-weight: bold; color: #c2185b; margin-bottom: 10px;">✅ Google連携</div>
Googleサービスとシームレスに連携
</div>

</div>

</div>

---

## Geminiを始める：3ステップ

<div style="font-size: 0.9em;">

非常にシンプルです。数分で始められます。

<br>

<div style="display: flex; flex-direction: column; gap: 20px; margin: 25px 0;">

<div style="background: #e3f2fd; border: 3px solid #1976d2; padding: 25px; border-radius: 12px;">
<div style="display: flex; align-items: center; gap: 20px;">
<div style="background: #1976d2; color: white; width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.5em; font-weight: bold; flex-shrink: 0;">1</div>
<div>
<div style="font-weight: bold; color: #1976d2; font-size: 1.2em; margin-bottom: 5px;">Webブラウザを開く</div>
<div style="font-size: 0.95em;">Chrome、Safari、Edgeなど、お好みのブラウザで</div>
</div>
</div>
</div>

<div style="background: #fff3e0; border: 3px solid #f57c00; padding: 25px; border-radius: 12px;">
<div style="display: flex; align-items: center; gap: 20px;">
<div style="background: #f57c00; color: white; width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.5em; font-weight: bold; flex-shrink: 0;">2</div>
<div>
<div style="font-weight: bold; color: #f57c00; font-size: 1.2em; margin-bottom: 5px;">URLにアクセス</div>
<div style="font-size: 0.95em; font-family: monospace; background: white; padding: 8px; border-radius: 5px; margin-top: 8px;">https://gemini.google.com/</div>
</div>
</div>
</div>

<div style="background: #e8f5e9; border: 3px solid #388e3c; padding: 25px; border-radius: 12px;">
<div style="display: flex; align-items: center; gap: 20px;">
<div style="background: #388e3c; color: white; width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.5em; font-weight: bold; flex-shrink: 0;">3</div>
<div>
<div style="font-weight: bold; color: #388e3c; font-size: 1.2em; margin-bottom: 5px;">Googleアカウントでログイン</div>
<div style="font-size: 0.95em;">普段使っているGoogleアカウントでOK</div>
</div>
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
これだけで準備完了！今すぐ始められます
</div>

</div>

---

## Geminiの画面構成

<div style="font-size: 0.9em;">

シンプルで直感的なインターフェースです。

<br>

<div style="background: white; border: 3px solid #4285f4; padding: 30px; border-radius: 12px; margin: 20px 0;">

<div style="margin-bottom: 25px;">
<div style="background: #e3f2fd; padding: 15px; border-radius: 8px; border-left: 5px solid #1976d2;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px;">📝 入力エリア（画面下部）</div>
質問やプロンプトを入力する場所  
「メッセージを入力」と書かれたテキストボックス
</div>
</div>

<div style="margin-bottom: 25px;">
<div style="background: #fff3e0; padding: 15px; border-radius: 8px; border-left: 5px solid #f57c00;">
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px;">💬 会話エリア（画面中央）</div>
あなたの質問とGeminiの回答が表示される場所  
チャット形式で会話が続く
</div>
</div>

<div style="margin-bottom: 25px;">
<div style="background: #e8f5e9; padding: 15px; border-radius: 8px; border-left: 5px solid #388e3c;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px;">🔄 新しいチャット（画面左上）</div>
別のトピックで話したいときは「新しいチャット」で開始
</div>
</div>

<div>
<div style="background: #fce4ec; padding: 15px; border-radius: 8px; border-left: 5px solid #c2185b;">
<div style="font-weight: bold; color: #c2185b; margin-bottom: 8px;">📂 チャット履歴（画面左）</div>
過去の会話を保存・参照できる
</div>
</div>

</div>

</div>

---

## 実践演習①：最初の質問をしてみよう

<div style="font-size: 0.9em;">

まずはシンプルな質問から始めましょう。

<br>

<div style="background: #e8f5e9; border: 3px solid #388e3c; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-weight: bold; color: #388e3c; font-size: 1.2em; margin-bottom: 15px;">🎯 演習：簡単な質問をしてみる</div>

<div style="background: white; padding: 20px; border-radius: 8px; margin: 15px 0;">
<div style="font-weight: bold; margin-bottom: 10px;">入力例：</div>
<div style="font-family: monospace; background: #f5f5f5; padding: 12px; border-radius: 5px; border-left: 4px solid #388e3c;">
生成AIとは何ですか？初心者にもわかるように簡単に説明してください。
</div>
</div>

<div style="font-size: 0.95em; line-height: 1.6;">
<div style="margin-bottom: 8px;"><strong>手順：</strong></div>
1. 上記の文章をコピー、または自分の言葉で入力<br>
2. Enterキーを押す、または送信ボタンをクリック<br>
3. Geminiの回答を読んでみる
</div>
</div>

<br>

<div style="background: #fff3e0; padding: 15px; border-radius: 8px; border-left: 5px solid #f57c00;">
💡 <strong>ポイント：</strong>最初は完璧なプロンプトでなくても大丈夫。まずは気軽に話しかけてみましょう！
</div>

</div>

---

## 実践演習②：プロンプトを改善してみよう

<div style="font-size: 0.85em;">

同じ質問でも、プロンプトの書き方で回答の質が変わります。

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px;">

<div style="background: #ffebee; border: 2px solid #d32f2f; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 12px; font-size: 1.1em;">❌ あいまいな質問</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.9em; margin-bottom: 12px;">
メールを書いて
</div>
<div style="font-size: 0.9em;">
<strong>問題点：</strong><br>
• 誰に？<br>
• 何について？<br>
• どんなトーン？<br>
→ AIが推測で書くしかない
</div>
</div>

<div style="background: #e8f5e9; border: 2px solid #388e3c; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 12px; font-size: 1.1em;">✅ 具体的な指示</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.85em; margin-bottom: 12px; line-height: 1.5;">
取引先の田中様に、来週の打ち合わせ日程の変更をお願いするメールを書いてください。丁寧なトーンで、200文字程度でお願いします。
</div>
<div style="font-size: 0.9em;">
<strong>改善点：</strong><br>
✓ 相手が明確<br>
✓ 目的が明確<br>
✓ トーンと文字数を指定
</div>
</div>

</div>

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
🎯 演習：両方試して、回答の違いを体感してみましょう！
</div>

</div>

---

## 実践演習③：業務で使えるシーン

<div style="font-size: 0.85em;">

実際の業務で今すぐ使える3つのシーンを体験しましょう。

<br>

<div style="display: flex; flex-direction: column; gap: 15px;">

<div style="background: #e3f2fd; border-left: 5px solid #1976d2; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #1976d2; font-size: 1.1em; margin-bottom: 10px;">📧 シーン1：メール作成</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.9em; line-height: 1.5;">
新入社員向けに、明日のオリエンテーションの案内メールを作成してください。<br>
【含める内容】<br>
・日時：明日10時〜12時<br>
・場所：本社3F会議室<br>
・持ち物：筆記用具、社員証<br>
親しみやすいトーンで、300文字程度でお願いします。
</div>
</div>

<div style="background: #fff3e0; border-left: 5px solid #f57c00; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #f57c00; font-size: 1.1em; margin-bottom: 10px;">📊 シーン2：データ要約</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.9em; line-height: 1.5;">
以下の会議メモから、決定事項とネクストアクションを抽出してください。<br>
【会議メモ】<br>
（ここに実際の議事録を貼り付ける）<br>
<br>
箇条書きで、重要度順に並べてください。
</div>
</div>

<div style="background: #e8f5e9; border-left: 5px solid #388e3c; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #388e3c; font-size: 1.1em; margin-bottom: 10px;">💡 シーン3：アイデア出し</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.9em; line-height: 1.5;">
チームの業務効率化のアイデアを5つ提案してください。<br>
【条件】<br>
・コストは月10万円以内<br>
・3ヶ月以内に実現可能<br>
・リモートワークにも対応<br>
各アイデアに、期待効果も添えてください。
</div>
</div>

</div>

</div>

---

## うまくいかないときの対処法

<div style="font-size: 0.9em;">

Geminiの回答が期待通りでないときは、以下を試してみましょう。

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin: 20px 0;">

<div style="background: #e3f2fd; padding: 20px; border-radius: 10px; border-left: 5px solid #1976d2;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 10px;">🔄 追加で指示を出す</div>
<div style="font-size: 0.95em;">
「もっと詳しく説明してください」<br>
「専門用語を減らしてください」<br>
「箇条書きにしてください」
</div>
</div>

<div style="background: #fff3e0; padding: 20px; border-radius: 10px; border-left: 5px solid #f57c00;">
<div style="font-weight: bold; color: #f57c00; margin-bottom: 10px;">✏️ プロンプトを書き直す</div>
<div style="font-size: 0.95em;">
・より具体的な情報を追加<br>
・出力形式を明示<br>
・例を示す
</div>
</div>

<div style="background: #e8f5e9; padding: 20px; border-radius: 10px; border-left: 5px solid #388e3c;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 10px;">🔁 再生成する</div>
<div style="font-size: 0.95em;">
回答の下にある「他の下書きを表示」で、別の回答を見る
</div>
</div>

<div style="background: #fce4ec; padding: 20px; border-radius: 10px; border-left: 5px solid #c2185b;">
<div style="font-weight: bold; color: #c2185b; margin-bottom: 10px;">🆕 新しいチャットで試す</div>
<div style="font-size: 0.95em;">
会話履歴をリセットして、新しい視点から質問
</div>
</div>

</div>

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
💡 試行錯誤は学習のプロセス。恐れずに何度でもトライしましょう！
</div>

</div>

---

## Gemini活用のベストプラクティス

<div style="font-size: 0.9em;">

Geminiをより効果的に使うためのヒント：

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 12px; font-size: 0.85em;">

<div style="background: #e3f2fd; padding: 18px; border-radius: 8px; text-align: center;">
<div style="font-size: 2em; margin-bottom: 8px;">📝</div>
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px;">具体的に</div>
5W1Hを意識して<br>詳細に伝える
</div>

<div style="background: #fff3e0; padding: 18px; border-radius: 8px; text-align: center;">
<div style="font-size: 2em; margin-bottom: 8px;">🎭</div>
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px;">役割を与える</div>
「あなたは〇〇の<br>専門家です」
</div>

<div style="background: #e8f5e9; padding: 18px; border-radius: 8px; text-align: center;">
<div style="font-size: 2em; margin-bottom: 8px;">📋</div>
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px;">形式を指定</div>
箇条書き、表形式<br>など明示
</div>

<div style="background: #fce4ec; padding: 18px; border-radius: 8px; text-align: center;">
<div style="font-size: 2em; margin-bottom: 8px;">💬</div>
<div style="font-weight: bold; color: #c2185b; margin-bottom: 8px;">対話を続ける</div>
不十分なら<br>追加質問する
</div>

<div style="background: #f3e5f5; padding: 18px; border-radius: 8px; text-align: center;">
<div style="font-size: 2em; margin-bottom: 8px;">🔍</div>
<div style="font-weight: bold; color: #7b1fa2; margin-bottom: 8px;">検証する</div>
重要な情報は<br>必ず確認
</div>

<div style="background: #e0f2f1; padding: 18px; border-radius: 8px; text-align: center;">
<div style="font-size: 2em; margin-bottom: 8px;">💾</div>
<div style="font-weight: bold; color: #00796b; margin-bottom: 8px;">保存する</div>
良いプロンプトは<br>記録しておく
</div>

</div>

</div>

---

## 第3章のまとめ

<div style="font-size: 0.95em;">

### Google Geminiで実践体験

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 15px; margin: 20px 0;">

<div style="background: #e3f2fd; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #1976d2;">
<div style="font-size: 1.8em; margin-bottom: 10px;">🚀</div>
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px;">始め方</div>
<div style="font-size: 0.85em;">
gemini.google.com<br/>
すぐに始められる
</div>
</div>

<div style="background: #fff3e0; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #f57c00;">
<div style="font-size: 1.8em; margin-bottom: 10px;">💬</div>
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px;">使い方</div>
<div style="font-size: 0.85em;">
具体的に質問<br/>
対話を重ねる
</div>
</div>

<div style="background: #e8f5e9; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #388e3c;">
<div style="font-size: 1.8em; margin-bottom: 10px;">📊</div>
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px;">実践</div>
<div style="font-size: 0.85em;">
業務シーンで<br/>すぐ活用できる
</div>
</div>

</div>

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
実際に手を動かすことで、生成AIの可能性が実感できます！
</div>

</div>

---

## 目次

1. <font color=#E5E8EA>「生成AI」とは何か？</font>
   
2. <font color=#E5E8EA>生成AIに関する基礎知識</font>

3. <font color=#E5E8EA>Google Geminiを使ってみよう</font>

4. 生成AIをより上手に使うために

5. <font color=#E5E8EA>まとめ</font>

---

## 第4章で学ぶこと

生成AIを効果的に使うための実践的なヒントと、知っておくべき注意点を学びます。

### この章のポイント

1. **プロンプトのレベルアップ** 〜 より良い回答を得るために
2. **AIの限界を知る** 〜 上手に付き合うために
3. **安全な使い方** 〜 責任ある利用のために

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px; border-left: 5px solid #388e3c; margin-top: 25px;">
💡 AIを賢く、安全に使いこなすための実践的な知識です
</div>

---

## プロンプトをレベルアップさせる3つのコツ

<div style="font-size: 0.9em;">

第3章で基本を学びました。ここでは、さらに回答の質を高めるコツを紹介します。

<br>

<div style="display: flex; flex-direction: column; gap: 18px; margin: 25px 0;">

<div style="background: #e3f2fd; border-left: 8px solid #1976d2; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 2.5em;">💡</div>
<div>
<div style="font-weight: bold; color: #1976d2; font-size: 1.2em; margin-bottom: 5px;">1. 例を示す</div>
<div style="font-size: 0.9em;">期待する出力の形式や内容の例を1〜2個示すと、AIが意図を正確に理解します</div>
</div>
</div>
</div>

<div style="background: #fff3e0; border-left: 8px solid #f57c00; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 2.5em;">🎭</div>
<div>
<div style="font-weight: bold; color: #f57c00; font-size: 1.2em; margin-bottom: 5px;">2. 役割を与える</div>
<div style="font-size: 0.9em;">「あなたは〇〇の専門家です」と伝えることで、専門的で適切な回答が得られます</div>
</div>
</div>
</div>

<div style="background: #e8f5e9; border-left: 8px solid #388e3c; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 2.5em;">🔄</div>
<div>
<div style="font-weight: bold; color: #388e3c; font-size: 1.2em; margin-bottom: 5px;">3. 対話で磨く</div>
<div style="font-size: 0.9em;">最初の回答が不十分なら「もっと詳しく」「具体例を追加して」と追加で指示しましょう</div>
</div>
</div>
</div>

</div>

</div>

---

## コツ①：例を示すプロンプト

<div style="font-size: 0.85em;">

実際の例を見てみましょう。

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px;">

<div style="background: #ffebee; border: 2px solid #d32f2f; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 12px; font-size: 1.1em;">❌ 例なし</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.9em; margin-bottom: 12px; line-height: 1.5;">
顧客レビューの感情を分析してください。<br>
<br>
「サポートが親切でした」
</div>
<div style="font-size: 0.9em;">
AIは形式がわからず、<br>回答がバラバラに
</div>
</div>

<div style="background: #e8f5e9; border: 2px solid #388e3c; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 12px; font-size: 1.1em;">✅ 例あり</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.85em; margin-bottom: 12px; line-height: 1.5;">
以下の例を参考に感情分析してください。<br>
例）「商品が早く届いた」→ポジティブ<br>
例）「対応が遅い」→ネガティブ<br>
<br>
「サポートが親切でした」
</div>
<div style="font-size: 0.9em;">
形式が統一され、<br>一貫した回答に
</div>
</div>

</div>

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
💡 1〜2個の例を示すだけで、回答の質が大きく向上します
</div>

</div>

---

## コツ②：役割を与えるプロンプト

<div style="font-size: 0.85em;">

AIに「専門家」の役割を与えることで、視点や専門性が変わります。

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px;">

<div style="background: #ffebee; border: 2px solid #d32f2f; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 12px; font-size: 1.1em;">❌ 役割なし</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.9em; margin-bottom: 12px;">
データセキュリティについて説明して
</div>
<div style="font-size: 0.9em;">
一般的で抽象的な<br>回答になりがち
</div>
</div>

<div style="background: #e8f5e9; border: 2px solid #388e3c; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 12px; font-size: 1.1em;">✅ 役割あり</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.85em; margin-bottom: 12px; line-height: 1.5;">
あなたは情報セキュリティの専門家です。中小企業の経営者向けに、データセキュリティの重要性を3つのポイントで説明してください。
</div>
<div style="font-size: 0.9em;">
対象者に合わせた<br>具体的な回答に
</div>
</div>

</div>

<br>

<div style="background: #e3f2fd; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold; color: #1976d2;">
🎯 「専門家」「初心者向けの先生」など、役割を明確にしましょう
</div>

</div>

---

## コツ③：対話で磨くプロンプト

<div style="font-size: 0.9em;">

完璧な回答を一度で得ることは難しいです。対話を重ねて改善しましょう。

<br>

<div style="background: white; border: 3px solid #667eea; padding: 25px; border-radius: 12px; margin: 20px 0;">

<div style="background: #e3f2fd; padding: 15px; border-radius: 8px; margin-bottom: 15px;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px;">📝 最初の質問</div>
<div style="font-family: monospace; font-size: 0.9em;">
「チーム会議の効率化方法を教えて」
</div>
</div>

<div style="text-align: center; margin: 15px 0; font-size: 1.5em; color: #667eea;">⬇️</div>

<div style="background: #fff3e0; padding: 15px; border-radius: 8px; margin-bottom: 15px;">
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px;">💬 追加指示①</div>
<div style="font-family: monospace; font-size: 0.9em;">
「もっと具体的な方法を教えてください」
</div>
</div>

<div style="text-align: center; margin: 15px 0; font-size: 1.5em; color: #667eea;">⬇️</div>

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px;">✨ 追加指示②</div>
<div style="font-family: monospace; font-size: 0.9em;">
「リモートワークでも使える方法に絞ってください」
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
対話を重ねることで、求める回答に近づいていきます
</div>

</div>

---

## AIの限界①：ハルシネーション

<div style="font-size: 0.9em;">

生成AIは強力ですが、万能ではありません。限界を知ることが重要です。

<br>

<div style="background: #ffebee; border: 3px solid #d32f2f; padding: 20px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; color: #d32f2f; margin-bottom: 10px;">⚠️ ハルシネーション（幻覚）</div>

AIが事実に基づかない情報や、もっともらしい嘘を、  
あたかも真実であるかのように生成してしまう現象
</div>

<br>

### なぜ起こる？

AIは統計的なパターンに基づいて応答しているだけで、  
**真実を理解しているわけではない**ため

<br>

<div style="background: #fff3e0; padding: 15px; border-radius: 8px; border-left: 5px solid #f57c00;">
<div style="font-weight: bold; color: #f57c00;">💡 対策</div>
• 重要な情報は必ず事実確認する<br/>
• RAGなどで情報源を明示する<br/>
• 複数の情報源と照合する
</div>

</div>

---

## AIの限界②：ナレッジカットオフ

<div style="font-size: 0.9em;">

<div style="background: #fff3e0; border: 3px solid #f57c00; padding: 20px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; color: #f57c00; margin-bottom: 10px;">📅 ナレッジカットオフ（知識の締切日）</div>

AIモデルは特定の時点までのデータで学習されているため、  
**その後の最新情報については知識がない**
</div>

<br>

### 例

<div style="background: white; border: 2px solid #f57c00; padding: 15px; border-radius: 8px; font-family: monospace; font-size: 0.9em; margin: 15px 0;">
質問：「2024年10月の最新ニュースを教えて」<br/>
<br/>
<span style="color: #d32f2f;">❌ 回答できない：</span>学習データが2024年4月までの場合
</div>

<br>

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px; border-left: 5px solid #388e3c;">
<div style="font-weight: bold; color: #388e3c;">💡 対策</div>
• 最新情報が必要な場合は情報源を別途確認<br/>
• 検索機能と組み合わせて使う<br/>
• いつの情報か常に意識する
</div>

</div>

---

## AIの限界③：データへの依存とバイアス

<div style="font-size: 0.9em;">

<div style="background: #fce4ec; border: 3px solid #c2185b; padding: 20px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.2em; font-weight: bold; color: #c2185b; margin-bottom: 10px;">⚠️ データへの依存とバイアス</div>

モデルの性能・知識・潜在的なバイアスは、  
**すべて学習に使用されたデータに完全に依存**する
</div>

<br>

### バイアスの問題

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9em;">

<div style="background: #ffebee; border-left: 5px solid #d32f2f; padding: 15px; border-radius: 8px;">
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 8px;">🚫 問題</div>
学習データに社会的な偏見や差別的な内容が含まれていると、AIがそれを学習し、増幅させてしまう
</div>

<div style="background: #fff3e0; border-left: 5px solid #f57c00; padding: 15px; border-radius: 8px;">
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px;">⚠️ 影響</div>
融資審査、採用選考など重要な場面で不公平な結果を招く危険性
</div>

</div>

<br>

<div style="background: #e3f2fd; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold; color: #1976d2;">
高品質で公平なデータこそが、信頼できるAIを生み出す鍵
</div>

</div>

---

## 責任あるAI利用

<div style="font-size: 0.9em;">

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; margin-bottom: 10px;">🤝 責任あるAI（Responsible AI）</div>

AIが人間に害を及ぼさず、公平かつ倫理的に使用されることを  
保証するための指針や実践
</div>

<br>

### 利用者としての責任

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9em; margin-top: 15px;">

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px;">
✅ **批判的な視点**<br/>
AIの出力を鵜呑みにしない
</div>

<div style="background: #e3f2fd; padding: 15px; border-radius: 8px;">
✅ **検証の習慣**<br/>
重要な情報は必ず確認する
</div>

<div style="background: #fff3e0; padding: 15px; border-radius: 8px;">
✅ **限界の理解**<br/>
何ができて何ができないかを知る
</div>

<div style="background: #fce4ec; padding: 15px; border-radius: 8px;">
✅ **倫理的配慮**<br/>
バイアスや差別に注意を払う
</div>

</div>

</div>

---

## 安全に使うための心得

<div style="font-size: 0.9em;">

生成AIを業務で使う際に、必ず守るべきルールがあります。

<br>

<div style="display: flex; flex-direction: column; gap: 15px; margin: 20px 0;">

<div style="background: #ffebee; border: 3px solid #d32f2f; padding: 20px; border-radius: 10px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 2em;">🔒</div>
<div>
<div style="font-weight: bold; color: #d32f2f; font-size: 1.1em; margin-bottom: 5px;">機密情報は入力しない</div>
<div style="font-size: 0.9em;">顧客情報、社内機密、個人情報などは絶対にAIに入力しないでください</div>
</div>
</div>
</div>

<div style="background: #fff3e0; border: 3px solid #f57c00; padding: 20px; border-radius: 10px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 2em;">✅</div>
<div>
<div style="font-weight: bold; color: #f57c00; font-size: 1.1em; margin-bottom: 5px;">必ず内容を確認する</div>
<div style="font-size: 0.9em;">AIの出力をそのまま使わず、必ず人間が内容を確認・修正してから使用しましょう</div>
</div>
</div>
</div>

<div style="background: #e3f2fd; border: 3px solid #1976d2; padding: 20px; border-radius: 10px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 2em;">📋</div>
<div>
<div style="font-weight: bold; color: #1976d2; font-size: 1.1em; margin-bottom: 5px;">社内ルールを守る</div>
<div style="font-size: 0.9em;">会社の生成AI利用ガイドラインがあれば、必ず確認して従ってください</div>
</div>
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #d32f2f 0%, #c2185b 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
⚠️ 安全に使うことが、長く活用し続けるための大前提です
</div>

</div>

---

## 第4章のまとめ

<div style="font-size: 0.9em;">

### 賢く、安全に使いこなすために

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 15px; margin: 20px 0;">

<div style="background: #e3f2fd; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #1976d2;">
<div style="font-size: 1.8em; margin-bottom: 10px;">📚</div>
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px;">レベルアップ</div>
<div style="font-size: 0.85em;">
• 例を示す<br/>
• 役割を与える<br/>
• 対話で磨く
</div>
</div>

<div style="background: #ffebee; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #d32f2f;">
<div style="font-size: 1.8em; margin-bottom: 10px;">⚠️</div>
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 8px;">限界を知る</div>
<div style="font-size: 0.85em;">
• ハルシネーション<br/>
• 古い情報<br/>
• バイアス
</div>
</div>

<div style="background: #e8f5e9; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #388e3c;">
<div style="font-size: 1.8em; margin-bottom: 10px;">🔒</div>
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px;">安全に使う</div>
<div style="font-size: 0.85em;">
• 機密情報は入力しない<br/>
• 必ず確認する<br/>
• ルールを守る
</div>
</div>

</div>

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
AIは強力なツール。正しく理解して、安全に活用しましょう！
</div>

</div>

---

## 目次

1. <font color=#E5E8EA>「生成AI」とは何か？</font>
   
2. <font color=#E5E8EA>生成AIに関する基礎知識</font>

3. <font color=#E5E8EA>Google Geminiを使ってみよう</font>

4. <font color=#E5E8EA>生成AIをより上手に使うために</font>

5. まとめ

---

## 今日学んだこと：全体の振り返り

<div style="font-size: 0.85em;">

本日は、生成AIの基礎から実践的な活用方法まで学びました。

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin: 20px 0;">

<div style="background: #e3f2fd; border-radius: 10px; padding: 20px; border-top: 5px solid #1976d2;">
<div style="font-size: 1.3em; margin-bottom: 8px; text-align: center;">1️⃣</div>
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px; text-align: center;">生成AIとは</div>
<div style="font-size: 0.9em;">
• AI技術の階層<br/>
• 4つの能力<br/>
• マルチモーダル
</div>
</div>

<div style="background: #fff3e0; border-radius: 10px; padding: 20px; border-top: 5px solid #f57c00;">
<div style="font-size: 1.3em; margin-bottom: 8px; text-align: center;">2️⃣</div>
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px; text-align: center;">基礎知識</div>
<div style="font-size: 0.9em;">
• モデルとLLM<br/>
• データの重要性<br/>
• プロンプトの基本
</div>
</div>

<div style="background: #e8f5e9; border-radius: 10px; padding: 20px; border-top: 5px solid #388e3c;">
<div style="font-size: 1.3em; margin-bottom: 8px; text-align: center;">3️⃣</div>
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px; text-align: center;">Geminiで実践</div>
<div style="font-size: 0.9em;">
• アクセス方法<br/>
• 基本的な使い方<br/>
• 実践的な演習
</div>
</div>

<div style="background: #fce4ec; border-radius: 10px; padding: 20px; border-top: 5px solid #c2185b;">
<div style="font-size: 1.3em; margin-bottom: 8px; text-align: center;">4️⃣</div>
<div style="font-weight: bold; color: #c2185b; margin-bottom: 8px; text-align: center;">賢く使う</div>
<div style="font-size: 0.9em;">
• プロンプトの改善<br/>
• AIの限界<br/>
• 安全な利用
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold; margin-top: 20px;">
これであなたも「Generative AI Leader」への第一歩！
</div>

</div>

---

## 生成AIを使いこなすための3つの心構え

<div style="font-size: 0.9em;">

学んだ知識を活かして、生成AIと上手に付き合うために：

<div style="display: flex; flex-direction: column; gap: 18px; margin: 25px 0;">

<div style="background: #e3f2fd; border-left: 8px solid #1976d2; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 2.5em;">🎯</div>
<div>
<div style="font-weight: bold; color: #1976d2; font-size: 1.2em; margin-bottom: 5px;">1. 具体的に指示する</div>
<div style="font-size: 0.9em;">あいまいな質問より、役割・形式・期待値を明確に伝えることで、望む結果が得られます</div>
</div>
</div>
</div>

<div style="background: #fff3e0; border-left: 8px solid #f57c00; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 2.5em;">⚖️</div>
<div>
<div style="font-weight: bold; color: #f57c00; font-size: 1.2em; margin-bottom: 5px;">2. 批判的に検証する</div>
<div style="font-size: 0.9em;">AIの回答を鵜呑みにせず、ハルシネーションやバイアスに注意して事実確認を行いましょう</div>
</div>
</div>
</div>

<div style="background: #e8f5e9; border-left: 8px solid #388e3c; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 2.5em;">🚀</div>
<div>
<div style="font-weight: bold; color: #388e3c; font-size: 1.2em; margin-bottom: 5px;">3. 試行錯誤を楽しむ</div>
<div style="font-size: 0.9em;">最初から完璧なプロンプトは書けません。試して、改善して、学ぶプロセスを楽しみましょう</div>
</div>
</div>
</div>

</div>

</div>

---

## おすすめの生成AIツール

<div style="font-size: 0.9em;">

まずは無料で始められる主要ツールを紹介します。

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 15px; margin: 25px 0;">

<div style="background: white; border: 3px solid #4285f4; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #4285f4; font-size: 1.2em; margin-bottom: 10px; text-align: center;">Google Gemini</div>
<div style="font-size: 0.85em; line-height: 1.6;">
<strong>特徴：</strong>Googleアカウントで即利用可能<br/>
<strong>強み：</strong>最新情報へのアクセス、Google製品との連携<br/>
<strong>URL：</strong>gemini.google.com
</div>
</div>

<div style="background: white; border: 3px solid #10a37f; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #10a37f; font-size: 1.2em; margin-bottom: 10px; text-align: center;">ChatGPT</div>
<div style="font-size: 0.85em; line-height: 1.6;">
<strong>特徴：</strong>最も有名で利用者が多い<br/>
<strong>強み：</strong>豊富な学習データ、プラグイン機能<br/>
<strong>URL：</strong>chatgpt.com
</div>
</div>

<div style="background: white; border: 3px solid #9b59b6; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #9b59b6; font-size: 1.2em; margin-bottom: 10px; text-align: center;">Claude</div>
<div style="font-size: 0.85em; line-height: 1.6;">
<strong>特徴：</strong>長文の処理が得意<br/>
<strong>強み：</strong>正確性、詳細な回答<br/>
<strong>URL：</strong>claude.ai
</div>
</div>

</div>

<div style="background: #e3f2fd; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold; color: #1976d2;">
💡 どれも無料プランがあります。まずは気になるものから試してみましょう！
</div>

</div>

---

## 今日から始められること：3ステップ

<div style="font-size: 0.9em;">

研修が終わったら、すぐに始められる3つのステップです。

<br>

<div style="display: flex; flex-direction: column; gap: 20px; margin: 25px 0;">

<div style="background: #e3f2fd; border: 3px solid #1976d2; padding: 25px; border-radius: 12px;">
<div style="display: flex; align-items: center; gap: 20px;">
<div style="background: #1976d2; color: white; width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.5em; font-weight: bold; flex-shrink: 0;">1</div>
<div>
<div style="font-weight: bold; color: #1976d2; font-size: 1.2em; margin-bottom: 5px;">まずはアクセス</div>
<div style="font-size: 0.95em;">今日のうちに <strong>gemini.google.com</strong> を開いて、簡単な質問を1つしてみましょう</div>
</div>
</div>
</div>

<div style="background: #fff3e0; border: 3px solid #f57c00; padding: 25px; border-radius: 12px;">
<div style="display: flex; align-items: center; gap: 20px;">
<div style="background: #f57c00; color: white; width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.5em; font-weight: bold; flex-shrink: 0;">2</div>
<div>
<div style="font-weight: bold; color: #f57c00; font-size: 1.2em; margin-bottom: 5px;">小さなタスクで試す</div>
<div style="font-size: 0.95em;">メール下書き、議事録要約など、<strong>失敗しても大丈夫なタスク</strong>から始めましょう</div>
</div>
</div>
</div>

<div style="background: #e8f5e9; border: 3px solid #388e3c; padding: 25px; border-radius: 12px;">
<div style="display: flex; align-items: center; gap: 20px;">
<div style="background: #388e3c; color: white; width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.5em; font-weight: bold; flex-shrink: 0;">3</div>
<div>
<div style="font-weight: bold; color: #388e3c; font-size: 1.2em; margin-bottom: 5px;">習慣にする</div>
<div style="font-size: 0.95em;"><strong>週に3回、5分だけ</strong>使ってみる。継続することで、自然に使えるようになります</div>
</div>
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
💡 完璧を目指さず、まずは触れてみることが大切です！
</div>

</div>

---

## 生成AIは、あなたの可能性を広げるパートナー

<div style="font-size: 0.95em;">

<div style="text-align: center; margin: 35px 0;">

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 40px; border-radius: 20px; box-shadow: 0 8px 20px rgba(0,0,0,0.2);">

<div style="font-size: 2.5em; margin-bottom: 20px;">🌟</div>

<div style="font-size: 1.8em; font-weight: bold; margin-bottom: 20px; line-height: 1.4;">
生成AIは、あなたの創造性を<br/>解放する強力な味方です
</div>

<div style="font-size: 1.1em; line-height: 1.8; margin: 20px 0;">
• ルーチンワークから解放され、本当に大切な仕事に集中できる<br/>
• 新しいアイデアを生み出すためのブレインストーミングパートナー<br/>
• 知識の壁を越えて、専門外の領域にも挑戦できる
</div>

</div>

</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9em; margin-top: 25px;">

<div style="background: #e3f2fd; padding: 20px; border-radius: 10px; text-align: center;">
<div style="font-size: 2em; margin-bottom: 10px;">🧠</div>
<div style="font-weight: bold; color: #1976d2;">AIの長所を活かす</div>
</div>

<div style="background: #fff3e0; padding: 20px; border-radius: 10px; text-align: center;">
<div style="font-size: 2em; margin-bottom: 10px;">⚠️</div>
<div style="font-weight: bold; color: #f57c00;">限界を理解する</div>
</div>

</div>

</div>

---

<!-- _backgroundColor: #0a1929 -->
<!-- _color: white -->

![bg](../../assets/images/3shake-background-full.png)

<div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); text-align: center; width: 80%;">

<div style="font-size: 3em; font-weight: bold; margin-bottom: 30px; text-shadow: 2px 2px 4px rgba(0,0,0,0.3);">
ありがとうございました！
</div>

<div style="font-size: 1.8em; margin-bottom: 40px; line-height: 1.6;">
さあ、今日から<br/>
生成AIを使い始めましょう！
</div>

<div style="background: rgba(255,255,255,0.1); backdrop-filter: blur(10px); padding: 30px; border-radius: 15px; border: 2px solid rgba(255,255,255,0.3);">
<div style="font-size: 1.3em; font-weight: bold; margin-bottom: 15px;">
🎓 なれる！Generative AI Leader
</div>
<div style="font-size: 1.1em; opacity: 0.9;">
あなたの変革の旅は、今ここから始まります
</div>
</div>

</div>

---

