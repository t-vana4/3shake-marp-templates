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
2025/xx/xx</br>Hajime Tachibana
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

3. <font color=#E5E8EA>Google Geminiを使ってみよう</font>

4. 生成AIをより上手に使うために

5. <font color=#E5E8EA>まとめ</font>

---

## 第4章で学ぶこと

生成AIをさらに効果的に使うための応用テクニックと、知っておくべき限界や注意点を学びます。

### この章のポイント

1. **高度なプロンプト技術** 〜 出力の質をさらに高める
2. **信頼性を高める技術** 〜 正確な回答を得るために
3. **AIの限界を知る** 〜 上手に付き合うために
4. **責任ある利用** 〜 安全に活用するために

<div style="background: #fff3e0; padding: 15px; border-radius: 8px; border-left: 5px solid #f57c00; margin-top: 25px;">
⚠️ AIを「道具」として正しく理解し、適切に使いこなすための知識です
</div>

---

## 高度なプロンプト技術①：ゼロショット

<div style="font-size: 0.9em;">

プロンプトの与え方には、いくつかのテクニックがあります。

<br>

<div style="background: #e3f2fd; border-left: 5px solid #1976d2; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-size: 1.1em; font-weight: bold; color: #1976d2; margin-bottom: 10px;">📝 ゼロショット プロンプティング</div>

事前情報や例を**一切与えず**、直接タスクを依頼する最もシンプルな方法
</div>

<br>

### 例

<div style="background: white; border: 2px solid #1976d2; padding: 15px; border-radius: 8px; font-family: monospace; font-size: 0.9em;">
生成AIのメリットを3つ挙げてください。
</div>

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.85em;">

<div style="background: #e8f5e9; padding: 12px; border-radius: 6px;">
✅ <strong>メリット</strong><br/>
シンプルで手軽
</div>

<div style="background: #ffebee; padding: 12px; border-radius: 6px;">
❌ <strong>デメリット</strong><br/>
期待通りの形式にならないことも
</div>

</div>

</div>

---

## 高度なプロンプト技術②：ワンショット

<div style="font-size: 0.9em;">

<div style="background: #fff3e0; border-left: 5px solid #f57c00; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-size: 1.1em; font-weight: bold; color: #f57c00; margin-bottom: 10px;">📝 ワンショット プロンプティング</div>

**1つだけ手本**となる例を示し、それを参考にタスクを実行させる方法
</div>

<br>

### 例

<div style="background: white; border: 2px solid #f57c00; padding: 15px; border-radius: 8px; font-family: monospace; font-size: 0.85em; line-height: 1.6;">
以下の例を参考に、「ML」について説明してください。<br/>
<br/>
<strong>例：</strong><br/>
Q: AIとは？<br/>
A: 人工知能（Artificial Intelligence）のことで、人間の知能を模倣したコンピュータシステムです。<br/>
<br/>
Q: MLとは？
</div>

<br>

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold; color: #388e3c;">
💡 出力の形式やスタイルを具体的に伝えたい場合に有効！
</div>

</div>

---

## 高度なプロンプト技術③：少数ショット

<div style="font-size: 0.9em;">

<div style="background: #e8f5e9; border-left: 5px solid #388e3c; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-size: 1.1em; font-weight: bold; color: #388e3c; margin-bottom: 10px;">📝 少数ショット プロンプティング</div>

**複数の例**を示すことで、より複雑なパターンやニュアンスを学習させる方法
</div>

<br>

### 例：顧客の感情分析

<div style="background: white; border: 2px solid #388e3c; padding: 15px; border-radius: 8px; font-family: monospace; font-size: 0.85em; line-height: 1.6;">
以下の例を参考に、顧客の感情を分析してください。<br/>
<br/>
「商品が予定より早く届いて嬉しいです」→ ポジティブ<br/>
「対応が遅くて困りました」→ ネガティブ<br/>
「普通の商品でした」→ ニュートラル<br/>
<br/>
「サポートの方が親切で助かりました」→ ?
</div>

<br>

<div style="background: #fff3e0; padding: 12px; border-radius: 6px; text-align: center; font-weight: bold; color: #f57c00;">
複数の例で学ばせることで、回答の精度がぐっと高まります！
</div>

</div>

---

## 高度なプロンプト技術④：ロール設定

<div style="font-size: 0.9em;">

<div style="background: #fce4ec; border-left: 5px solid #c2185b; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-size: 1.1em; font-weight: bold; color: #c2185b; margin-bottom: 10px;">👤 ロール設定（ペルソナ設定）</div>

AIに特定の**専門家やキャラクターの役割**を与えることで、出力のトーンや視点を制御
</div>

<br>

### 例の比較

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.85em;">

<div style="background: white; border: 2px solid #999; padding: 12px; border-radius: 8px;">
<div style="font-weight: bold; margin-bottom: 8px;">通常の質問</div>
<div style="font-family: monospace;">
生成AIのリスクを教えて
</div>
</div>

<div style="background: white; border: 2px solid #c2185b; padding: 12px; border-radius: 8px;">
<div style="font-weight: bold; margin-bottom: 8px; color: #c2185b;">ロール設定あり</div>
<div style="font-family: monospace;">
あなたは情報セキュリティの専門家です。経営者向けに、生成AIのセキュリティリスクを3つ、対策も含めて説明してください。
</div>
</div>

</div>

<br>

<div style="background: #e3f2fd; padding: 12px; border-radius: 6px; text-align: center; font-weight: bold; color: #1976d2;">
専門性の高い、具体的な回答が得られます！
</div>

</div>

---

## より信頼性の高い回答を得る：グラウンディング

<div style="font-size: 0.9em;">

AIの回答は常に正しいとは限りません。信頼性を高めるための技術があります。

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; margin-bottom: 10px;">⚓ グラウンディング（Grounding）</div>
AIの出力を、検証可能な特定の情報源に紐付ける（根拠を持たせる）技術
</div>

<br>

### 効果

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px;">

<div style="background: #e8f5e9; border-left: 5px solid #388e3c; padding: 15px; border-radius: 8px;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px;">✅ 正確性の向上</div>
事実に基づかない情報の生成を抑制
</div>

<div style="background: #e3f2fd; border-left: 5px solid #1976d2; padding: 15px; border-radius: 8px;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px;">✅ 信頼性の担保</div>
出典を明示できる
</div>

</div>

</div>

---

## RAG：検索拡張生成

<div style="font-size: 0.85em;">

グラウンディングを実現する代表的な手法が**RAG**です。

<br>

<div style="background: #fff3e0; border-left: 5px solid #f57c00; padding: 20px; border-radius: 8px; margin: 15px 0;">
<div style="font-size: 1.1em; font-weight: bold; color: #f57c00; margin-bottom: 10px;">🔍 RAG（Retrieval-Augmented Generation）</div>

LLMの一般的な知識と、あなたの組織が持つ専門知識を**会話の直前に融合**させる技術
</div>

<br>

### RAGの動作プロセス

<div style="background: white; border: 2px solid #667eea; padding: 20px; border-radius: 10px; margin: 15px 0;">

<div style="margin-bottom: 15px;">
<span style="background: #e3f2fd; color: #1976d2; padding: 5px 15px; border-radius: 20px; font-weight: bold;">1. 検索</span>
<div style="margin: 8px 0 0 20px; font-size: 0.95em;">質問に関連する情報を外部データベースから検索</div>
</div>

<div style="margin-bottom: 15px;">
<span style="background: #fff3e0; color: #f57c00; padding: 5px 15px; border-radius: 20px; font-weight: bold;">2. 拡張</span>
<div style="margin: 8px 0 0 20px; font-size: 0.95em;">見つけた情報を元のプロンプトに補足情報として追加</div>
</div>

<div style="margin-bottom: 15px;">
<span style="background: #e8f5e9; color: #388e3c; padding: 5px 15px; border-radius: 20px; font-weight: bold;">3. 生成</span>
<div style="margin: 8px 0 0 20px; font-size: 0.95em;">拡張されたプロンプトに基づいて最終的な回答を生成</div>
</div>

</div>

</div>

---

## RAGの活用例

<div style="font-size: 0.9em;">

RAGは、特に**社内情報を活用したい場合**に威力を発揮します。

<br>

### 具体例

<div style="background: linear-gradient(to right, #e8f5e9, #fff); border: 2px solid #388e3c; padding: 20px; border-radius: 10px; margin: 20px 0;">

<div style="font-weight: bold; color: #388e3c; margin-bottom: 10px;">📚 社内ナレッジベースと連携</div>

**質問**：「過去に同様のトラブルはありましたか？」

**RAGの動作**：
1. 社内の過去のトラブルシューティング文書から関連情報を検索
2. 検索した具体的な事例をプロンプトに追加
3. 実際の事例に基づいた、正確な回答を生成

</div>

<br>

<div style="background: #e3f2fd; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold; color: #1976d2;">
💡 「ハルシネーション」（後述）を効果的に防ぐことができます！
</div>

</div>

---

## モデルの「個性」を調整：パラメータ

<div style="font-size: 0.9em;">

AIモデルの出力の傾向は、いくつかの**パラメータ**を調整することで制御できます。

<br>

<div style="background: #fce4ec; border-left: 5px solid #c2185b; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-size: 1.1em; font-weight: bold; color: #c2185b; margin-bottom: 10px;">⚙️ サンプリング パラメータ</div>

AIの「性格」を調整するツマミのようなもの
</div>

<br>

### 主なパラメータ

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 12px; font-size: 0.85em;">

<div style="background: #e3f2fd; padding: 15px; border-radius: 8px; text-align: center;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px;">🌡️ 温度<br/>(Temperature)</div>
創造性の調整
</div>

<div style="background: #fff3e0; padding: 15px; border-radius: 8px; text-align: center;">
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px;">📊 Top-P</div>
単語の選択範囲
</div>

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px; text-align: center;">
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px;">📏 出力長</div>
テキストの長さ
</div>

</div>

</div>

---

## 温度（Temperature）：創造性のツマミ

<div style="font-size: 0.85em;">

<div style="background: #fff3e0; border-left: 5px solid #f57c00; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-weight: bold; color: #f57c00; margin-bottom: 10px;">🌡️ 温度とは</div>

AIに「どれだけ冒険させるか」を指示するツマミのようなもの
</div>

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">

<div style="background: #e3f2fd; border: 3px solid #1976d2; padding: 20px; border-radius: 10px;">
<div style="font-size: 1.5em; text-align: center; margin-bottom: 10px;">🧊</div>
<div style="font-weight: bold; color: #1976d2; text-align: center; margin-bottom: 10px;">低い温度（例：0.2）</div>
<div style="font-size: 0.95em;">
• **保守的で予測可能**<br/>
• 辞書通りの無難な言葉<br/>
• 事実に基づく要約に最適<br/>
<br/>
<strong>用途：</strong>技術文書、要約、翻訳
</div>
</div>

<div style="background: #ffebee; border: 3px solid #d32f2f; padding: 20px; border-radius: 10px;">
<div style="font-size: 1.5em; text-align: center; margin-bottom: 10px;">🔥</div>
<div style="font-weight: bold; color: #d32f2f; text-align: center; margin-bottom: 10px;">高い温度（例：1.0）</div>
<div style="font-size: 0.95em;">
• **創造的で多様**<br/>
• 意外な言葉の選択<br/>
• 独創的なアイデアに最適<br/>
<br/>
<strong>用途：</strong>創作文章、ブレスト、詩
</div>
</div>

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

## 第4章のまとめ

<div style="font-size: 0.9em;">

### 生成AIを使いこなすために

<br>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin: 20px 0;">

<div style="background: #e3f2fd; border-radius: 10px; padding: 20px; border-top: 5px solid #1976d2;">
<div style="font-size: 1.8em; margin-bottom: 10px; text-align: center;">📚</div>
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px; text-align: center;">高度な技術</div>
<div style="font-size: 0.85em;">
• ショットプロンプティング<br/>
• ロール設定<br/>
• RAGで信頼性向上
</div>
</div>

<div style="background: #fff3e0; border-radius: 10px; padding: 20px; border-top: 5px solid #f57c00;">
<div style="font-size: 1.8em; margin-bottom: 10px; text-align: center;">⚙️</div>
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px; text-align: center;">パラメータ調整</div>
<div style="font-size: 0.85em;">
• 温度で創造性を制御<br/>
• Top-Pで多様性を調整<br/>
• 用途に応じて最適化
</div>
</div>

<div style="background: #ffebee; border-radius: 10px; padding: 20px; border-top: 5px solid #d32f2f;">
<div style="font-size: 1.8em; margin-bottom: 10px; text-align: center;">⚠️</div>
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 8px; text-align: center;">限界を知る</div>
<div style="font-size: 0.85em;">
• ハルシネーション<br/>
• ナレッジカットオフ<br/>
• バイアスへの注意
</div>
</div>

<div style="background: #e8f5e9; border-radius: 10px; padding: 20px; border-top: 5px solid #388e3c;">
<div style="font-size: 1.8em; margin-bottom: 10px; text-align: center;">🤝</div>
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px; text-align: center;">責任ある利用</div>
<div style="font-size: 0.85em;">
• 批判的思考<br/>
• 検証の習慣<br/>
• 倫理的配慮
</div>
</div>

</div>

<br>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
AIの長所を活かし、限界を理解して、賢く付き合いましょう！
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

<div style="font-size: 0.9em;">

本日は、生成AIの基礎から実践的な活用方法まで学びました。

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 15px; margin: 25px 0;">

<div style="background: #e3f2fd; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #1976d2;">
<div style="font-size: 1.5em; margin-bottom: 10px;">1️⃣</div>
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px; font-size: 1.1em;">生成AIとは</div>
<div style="font-size: 0.85em;">
• AI技術の階層<br/>
• 4つの能力<br/>
• マルチモーダル
</div>
</div>

<div style="background: #fff3e0; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #f57c00;">
<div style="font-size: 1.5em; margin-bottom: 10px;">2️⃣</div>
<div style="font-weight: bold; color: #f57c00; margin-bottom: 8px; font-size: 1.1em;">基礎知識</div>
<div style="font-size: 0.85em;">
• モデル<br/>
• データ<br/>
• プロンプト
</div>
</div>

<div style="background: #e8f5e9; border-radius: 10px; padding: 20px; text-align: center; border-top: 5px solid #388e3c;">
<div style="font-size: 1.5em; margin-bottom: 10px;">4️⃣</div>
<div style="font-weight: bold; color: #388e3c; margin-bottom: 8px; font-size: 1.1em;">上手に使う</div>
<div style="font-size: 0.85em;">
• 高度な技術<br/>
• AIの限界<br/>
• 責任ある利用
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold; margin-top: 25px;">
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

## 今日から始められること：具体的な第一歩

<div style="font-size: 0.9em;">

<div style="background: linear-gradient(to right, #667eea, #764ba2); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; margin-bottom: 15px;">🎯 明日の業務で試してみよう</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9em; margin-top: 15px;">

<div style="background: rgba(255,255,255,0.15); padding: 15px; border-radius: 8px; backdrop-filter: blur(10px);">
<div style="font-weight: bold; margin-bottom: 8px;">📧 メール作成</div>
「取引先への新製品紹介メールを、丁寧なトーンで200文字程度で作成して」
</div>

<div style="background: rgba(255,255,255,0.15); padding: 15px; border-radius: 8px; backdrop-filter: blur(10px);">
<div style="font-weight: bold; margin-bottom: 8px;">📄 議事録要約</div>
「以下の議事録から、決定事項と次のアクションを3つずつ箇条書きで抽出して」
</div>

<div style="background: rgba(255,255,255,0.15); padding: 15px; border-radius: 8px; backdrop-filter: blur(10px);">
<div style="font-weight: bold; margin-bottom: 8px;">💡 アイデア出し</div>
「営業部の業務効率化のアイデアを5つ、それぞれ実現の難易度も含めて提案して」
</div>

<div style="background: rgba(255,255,255,0.15); padding: 15px; border-radius: 8px; backdrop-filter: blur(10px);">
<div style="font-weight: bold; margin-bottom: 8px;">📊 データ分析</div>
「この売上データから、トレンドと改善点を3つずつ分析して」
</div>

</div>
</div>

<div style="background: #e8f5e9; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold; color: #388e3c; margin-top: 20px;">
💡 所要時間：各5分程度。まずは1つ試してみましょう！
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

