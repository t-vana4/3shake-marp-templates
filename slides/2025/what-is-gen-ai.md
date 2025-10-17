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

# <span style="font-size: 0.7em;">今日からはじめる生成AI</span>

</div>

<div class="author-info" style="text-align: left; padding-left: 0; text-indent: 0;">
2025/10/22<br/>Hajime Tachibana
</div>

---

## はじめに

- 本日の勉強会の目的は **「生成AIを使ったことがない、またはなんとなくで使っている人に、<br/>生成AIの概要と基本的な使い方を知ってもらうこと」** です。

- そのため、情報の網羅性・正確性よりも「分かりやすさ」「実践しやすさ」を優先しています。

- 技術的に不正確な内容や発言が含まれる可能性がありますので、あらかじめご了承ください。

---

## 本日のゴール
<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 20px; margin: 30px 0;">

<div style="background: linear-gradient(135deg, #e3f2fd 0%, #bbdefb 100%); padding: 25px; border-radius: 12px; border-left: 5px solid #1976d2;">
<div style="font-size: 2em; text-align: center; margin-bottom: 10px;">📚</div>
<div style="font-weight: bold; color: #1976d2; font-size: 1.1em; margin-bottom: 10px; text-align: center;">理解する</div>
<div style="font-size: 0.9em;">
生成AIとは何か、どんなことができるのかを理解する
</div>
</div>

<div style="background: linear-gradient(135deg, #fff3e0 0%, #ffe0b2 100%); padding: 25px; border-radius: 12px; border-left: 5px solid #DDAC26;">
<div style="font-size: 2em; text-align: center; margin-bottom: 10px;">🛠️</div>
<div style="font-weight: bold; color: #DDAC26; font-size: 1.1em; margin-bottom: 10px; text-align: center;">実践する</div>
<div style="font-size: 0.9em;">
良いプロンプトの書き方と、上手な活用方法を学ぶ
</div>
</div>

<div style="background: linear-gradient(135deg, #e8f5e9 0%, #c8e6c9 100%); padding: 25px; border-radius: 12px; border-left: 5px solid #29A87F;">
<div style="font-size: 2em; text-align: center; margin-bottom: 10px;">🚀</div>
<div style="font-weight: bold; color: #29A87F; font-size: 1.1em; margin-bottom: 10px; text-align: center;">使いこなす</div>
<div style="font-size: 0.9em;">
明日からの業務に活かすためのイメージを持つ
</div>
</div>

</div>

<br/>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.2em; font-weight: bold;">
💡「生成AIを使ってみよう！」と思ってもらえることを目指します
</div>

---

## 目次

1. 「生成AI」とは何か？
   
2. 生成AIに関する基礎知識

3. Geakeを使ってみよう

4. 生成AIを上手く使うコツ

5. まとめ

---

## 目次

1. 「生成AI」とは何か？
   
2. <font color=#E5E8EA>生成AIに関する基礎知識</font>

3. <font color=#E5E8EA>Geakeを使ってみよう</font>

4. <font color=#E5E8EA>生成AIを上手く使うコツ</font>

5. <font color=#E5E8EA>まとめ</font>

---

## 「AI」の全体像

「生成AI」とは何かを理解するために、まずはAI技術の全体像から解説します。

<div style="text-align: center; margin: 30px auto;">

<div style="background: #e3f2fd; border: 3px solid #1976d2; border-radius: 15px; padding: 25px; margin: 10px auto; max-width: 85%;">
<div style="font-size: 1.3em; font-weight: bold; color: #1976d2;">AI（人工知能）</div>

<div style="background: #fff3e0; border: 3px solid #DDAC26; border-radius: 12px; padding: 20px; margin: 15px auto; max-width: 90%;">
<div style="font-size: 1.2em; font-weight: bold; color: #DDAC26;">機械学習（ML）</div>

<div style="background: #fce4ec; border: 3px solid #c2185b; border-radius: 10px; padding: 15px; margin: 12px auto; max-width: 90%;">
<div style="font-size: 1.1em; font-weight: bold; color: #c2185b;">ディープラーニング</div>

<div style="background: #e8f5e9; border: 4px solid #29A87F; border-radius: 8px; padding: 12px; margin: 10px auto; max-width: 90%;">
<div style="font-size: 1.0em; font-weight: bold; color: #29A87F;">生成AI</div>
</div>
</div>
</div>
</div>

</div>

---

## 「AI」の全体像

「生成AI」とは何かを理解するために、まずはAI技術の全体像から解説します。

<br/>

✅ **AI（人工知能）**：人間の知能を必要とするタスクを実行できるシステムの総称（最も広い概念）

✅ **機械学習（ML）**：データから自動的に学習し、パターンを見つけ出す技術

✅ **ディープラーニング**：脳の神経回路を模した多層構造で複雑なパターンを抽出する技術

✅ **生成AI**：**新しいコンテンツを作成することに特化** したAIの応用分野

---

## 生成AIとは？

既存のデータを分析したり予測したりするだけでなく、新しいものを **「生み出す」** ことができるのが、<br/>生成AIの最大の特徴です。

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; margin-bottom: 10px;">💡 生成AI</div>
まったく新しいコンテンツやアイデアを「生成」することができるAIの一種
</div>

---

## 生成AIの4つの能力

生成AIには、主に **4つの能力** があります。

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 30px; font-size: 0.9em;">

<div style="background: #e3f2fd; padding: 20px; border-radius: 10px; border-left: 5px solid #1976d2;">
<strong>1. 作成（Create）</strong><br/>
まったく新しいコンテンツを生成する
</div>

<div style="background: #fff3e0; padding: 20px; border-radius: 10px; border-left: 5px solid #DDAC26;">
<strong>2. 要約（Summarize）</strong><br/>
長い情報を簡潔にまとめる
</div>

<div style="background: #fce4ec; padding: 20px; border-radius: 10px; border-left: 5px solid #c2185b;">
<strong>3. 自動化（Automate）</strong><br/>
定型的なタスクを自動化する
</div>

<div style="background: #e8f5e9; padding: 20px; border-radius: 10px; border-left: 5px solid #29A87F;">
<strong>4. 発見（Discover）</strong><br/>
必要な情報を迅速に発見する
</div>

</div>

---

## 1. 作成（Create）

文章、画像、コード、音楽など、まったく新しいコンテンツをゼロから生成します。

### 具体例

- 📝 **マーケティング**：新商品のキャッチコピーを考える
- 🎨 **デザイン**：製品デザインのコンセプト画像を生成する
- 💻 **プログラミング**：特定の機能を実現するコードを作成する
- 🎵 **音楽**：雰囲気に合ったBGMを作曲する

<br/>

<div style="background: #e3f2fd; padding: 20px; border-radius: 10px; border-left: 5px solid #1976d2;">
💡 <strong>あなたの「創造的パートナー」として活躍！</strong>
</div>

</div>

---

## 2. 要約（Summarize）

長いレポートや会議の議事録などを、要点を押さえた簡潔な文章にまとめます。

### 具体例

- 📄 **長文レポート**：100ページの報告書を3ページに要約
- 📰 **ニュース記事**：長いニュース記事を3行で要約
- 💬 **会議議事録**：2時間の会議内容を決定事項中心にまとめる
- 📧 **メールの山**：大量のメールから重要な情報だけを抽出

<br/>

<div style="background: #fff3e0; padding: 20px; border-radius: 10px; border-left: 5px solid #DDAC26;">
💡 <strong>情報過多の時代に、あなたの「時間」を取り戻す！</strong>
</div>

</div>

---

## 3. 自動化（Automate）

これまで手作業で行っていた定型的なタスクを自動化し、業務効率を向上させます。

### 具体例

- ✉️ **顧客対応**：問い合わせメールへの返信文案を自動作成
- 📊 **レポート作成**：データから定型レポートを自動生成
- 📝 **文書整理**：社内文書の分類やタグ付けを自動化
- 🔄 **データ変換**：異なる形式のデータを一括変換

<br/>

<div style="background: #fce4ec; padding: 20px; border-radius: 10px; border-left: 5px solid #c2185b;">
💡 <strong>ルーティンワークから解放され、本当に大切な仕事に集中！</strong>
</div>

</div>

---

## 4. 発見（Discover）

膨大なデータの中から必要な情報を迅速に見つけ出し、適切なタイミングで提供します。

### 具体例

- 🔍 **社内ナレッジ検索**：過去のプロジェクト資料から類似事例を発見
- 👥 **専門家発見**：特定の知識を持つ社員を瞬時に特定
- 📚 **関連情報の提示**：現在の作業に関連する参考資料を提案
- 🎯 **パターン分析**：データから隠れたトレンドを発見

<br/>

<div style="background: #e8f5e9; padding: 20px; border-radius: 10px; border-left: 5px solid #29A87F;">
💡 <strong>組織の知識を「使える資産」に変える！</strong>
</div>

</div>

---

## さらなる特徴：マルチモーダル

最近の生成AIは**マルチモーダル**（複数のデータ形式を扱える）能力を持っています。

<div style="display: flex; justify-content: center; align-items: center; gap: 30px; margin: 30px 0;">

<div style="background: #f3e5f5; border: 3px solid #7b1fa2; border-radius: 15px; padding: 20px; text-align: center; min-width: 120px;">
<div style="font-size: 1.5em;">👤</div>
<div style="font-weight: bold; color: #7b1fa2; margin-top: 5px;">ユーザー</div>
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
<div style="background: #fff3e0; border: 2px solid #DDAC26; border-radius: 10px; padding: 12px; text-align: center;">
<div style="font-size: 1.2em;">🖼️</div>
<div style="font-size: 0.85em; font-weight: bold; color: #DDAC26;">画像</div>
</div>
<div style="background: #fce4ec; border: 2px solid #c2185b; border-radius: 10px; padding: 12px; text-align: center;">
<div style="font-size: 1.2em;">🔊</div>
<div style="font-size: 0.85em; font-weight: bold; color: #c2185b;">音声</div>
</div>
<div style="background: #e8f5e9; border: 2px solid #29A87F; border-radius: 10px; padding: 12px; text-align: center;">
<div style="font-size: 1.2em;">💻</div>
<div style="font-size: 0.85em; font-weight: bold; color: #29A87F;">コード</div>
</div>
</div>

</div>

<br/>

複数種類のデータを同時に理解し、処理・生成できる能力を持っている
　＝ 人間が思考し、創造するプロセスにより近い形でAIと対話できるようになってきている！

</div>

---

## 第 1 章のまとめ

✅ **生成AI**：「新しいコンテンツを作る」ことに特化したAIの応用分野

✅ **生成AIの4つの能力**：作成、要約、自動化、発見

✅ **マルチモーダル**：テキストだけでなく、画像・音声・コードも扱える

<br/>
<br/>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
💡 生成AIは、あなたの仕事を支援する「万能アシスタント」です！
</div>

---

## 目次

1. <font color=#E5E8EA>「生成AI」とは何か？</font>
   
2. 生成AIに関する基礎知識

3. <font color=#E5E8EA>Geakeを使ってみよう</font>

4. <font color=#E5E8EA>生成AIを上手く使うコツ</font>

5. <font color=#E5E8EA>まとめ</font>

---

## 第 2 章で学ぶこと

生成AIがどのように機能しているのか、その舞台裏にある重要な構成要素を理解します。

1. **モデル**：生成AIの「頭脳」

2. **データ**：生成AIの「賢さ」の源泉

3. **プロンプト**：生成AIとの「対話方法」

---

## 「モデル」とは？

生成AIの中核をなすのが、**「モデル」** と呼ばれる複雑なアルゴリズムの集合体です。

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; margin-bottom: 10px;">💡 モデル ＝ 生成AIの「頭脳」</div>
多量のデータを学習し、新しいコンテンツを生成する能力を持つもの
</div>

特に重要な次の2つの概念について、次ページ以降で解説します。

- **基盤モデル（Foundation Model）**

- **大規模言語モデル（LLM：Large Language Model）**

</div>

---

## 基盤モデル（Foundation Model）

<div style="background: #e3f2fd; border-left: 5px solid #1976d2; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-size: 1.1em; font-weight: bold; color: #1976d2; margin-bottom: 10px;">📚 基盤モデルとは</div>

- 大量のデータで事前にトレーニングされた、非常に大規模なAIモデル
- 特定のタスクに特化せず、**幅広い知識と能力を持つ**汎用的な土台

</div>

### 特徴

✅ **広範な知識**：インターネット上の膨大なデータから自律的に学習  
✅ **汎用性**：様々な用途に応用可能  
✅ **自己学習**：人間が正解ラベルを付けなくても学習できる

---

## 大規模言語モデル（LLM）

<div style="background: #e8f5e9; border-left: 5px solid #29A87F; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-size: 1.1em; font-weight: bold; color: #29A87F; margin-bottom: 10px;">💬 LLMとは</div>

- 基盤モデルの一種
- 特に **人間の言語（テキスト）の理解と生成に特化**したモデル

</div>

### できること

✅ **文章の作成**：レポート、メール、記事など  
✅ **要約**：長文を短くまとめる  
✅ **翻訳**：多言語間の翻訳  
✅ **質問応答**：質問に対して適切な回答を生成

---

## 両者の関係性

- **基盤モデル（Foundation Model）**：特定のタスクに特化しない汎用的な土台

- **大規模言語モデル（LLM）**：基盤モデルの中でも言語能力を極めた専門家

<br/>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
💡 Gemini や ChatGPT, Claude などは、基盤モデルでもあり大規模言語モデルでもある。
</div>

---

## モデルの学習

モデルが賢くなるプロセスは **「学習」または「トレーニング」** と呼ばれます。

<br/>

### 主な学習アプローチ

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 15px; margin-top: 20px; font-size: 0.9em;">

<div style="background: #e3f2fd; padding: 15px; border-radius: 10px; border-top: 5px solid #1976d2;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 8px;">📖　教師あり学習</div>
<div style="font-size: 0.85em;">
問題と正解のセットで学習<br/>
<span style="color: #666;">例：画像認識</span>
</div>
</div>

<div style="background: #fff3e0; padding: 15px; border-radius: 10px; border-top: 5px solid #DDAC26;">
<div style="font-weight: bold; color: #DDAC26; margin-bottom: 8px;">🔍　教師なし学習</div>
<div style="font-size: 0.85em;">
データから自動的にパターンを発見<br/>
<span style="color: #666;">基盤モデルで使用</span>
</div>
</div>

<div style="background: #e8f5e9; padding: 15px; border-radius: 10px; border-top: 5px solid #29A87F;">
<div style="font-weight: bold; color: #29A87F; margin-bottom: 8px;">🎮　強化学習</div>
<div style="font-size: 0.85em;">
試行錯誤で良い行動を学習<br/>
<span style="color: #666;">例：ゲームAI</span>
</div>
</div>

</div>

</div>

---

## 学習データの重要性

<div style="background: #fff3e0; border: 3px solid #DDAC26; padding: 20px; border-radius: 12px; margin: 20px 0; text-align: center;">
<div style="font-size: 1.5em; font-weight: bold; color: #DDAC26; margin-bottom: 10px;">
⚠️ Garbage In, Garbage Out
</div>
<div style="font-size: 1.1em;">
ゴミを入れれば、ゴミしか出てこない
</div>
</div>

### 高品質なデータの条件

✅ **正確性**：データに誤りがないこと
✅ **完全性**：必要な情報が欠けていないこと
✅ **整合性**：データ間で矛盾がないこと
✅ **関連性**：課題に対して適切なデータであること

---

## 学習データの質が低いとどうなるか

質の低いデータで学習したモデルでは、重大な問題が発生する可能性があります。

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 20px;">

<div style="background: #ffebee; border-left: 5px solid #d32f2f; font-size: 0.85em; padding: 20px; border-radius: 8px;">
<div style="font-size: 1.0em; font-weight: bold; color: #d32f2f; margin-bottom: 10px;">❌ 不正確な回答</div>
誤った情報や事実でない内容を生成してしまう
</div>

<div style="background: #fff3e0; border-left: 5px solid #DDAC26; font-size: 0.85em; padding: 20px; border-radius: 8px;">
<div style="font-size: 1.0em; font-weight: bold; color: #DDAC26; margin-bottom: 10px;">⚠️ バイアスの増幅</div>
社会的な偏見や差別的な内容を増幅してしまう
</div>

</div>

<br/>
<br/>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
💡 高品質なデータこそが、高性能で公正なAIモデルを生み出す最も重要な資源！
</div>

</div>

---

## AIとの対話方法

生成AIとやり取りするための方法が **「プロンプト」** です。

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-size: 1.3em; font-weight: bold; margin-bottom: 10px;">💡 プロンプト ＝ 生成AIとの「対話方法」</div>
AIに指示を与え、望む結果を引き出すための「入力」や「命令」のこと
</div>

<br/>

生成AIに対して **どのような指示を出すか** で、回答精度は劇的に変わります！

---

## プロンプトエンジニアリング

モデルの性能を最大限に引き出すためのプロンプト作成技術を **「プロンプトエンジニアリング」** と<br/>呼びます。

<div style="background: #e3f2fd; border-left: 5px solid #1976d2; padding: 20px; border-radius: 8px; margin: 20px 0;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 10px;">🎯 良いプロンプトのポイント</div>

✅ **具体的である**：何をしてほしいかを明確に指示する
✅ **形式を指定する**：箇条書き、表形式など出力形式を指定する
✅ **役割を与える**：生成AIに演じてほしい役割を与える
✅ **例を示す**：期待する出力の例を提示する

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 25px; border-radius: 12px; margin: 20px 0;">
💡 プロンプトエンジニアリングは、生成AIを使いこなすための重要スキル！
</div>

---

## 良いプロンプトの例 1：レポート作成

<div style="font-size: 0.85em;">

<div style="background: #ffebee; border: 2px solid #d32f2f; padding: 15px; border-radius: 8px; margin: 15px 0;">
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 8px;">❌ 悪い例</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.95em;">
AI活用について書いて
</div>
</div>

<div style="background: #e8f5e9; border: 2px solid #29A87F; padding: 15px; border-radius: 8px; margin: 15px 0;">
<div style="font-weight: bold; color: #29A87F; margin-bottom: 8px;">✅ 良い例</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.9em; line-height: 1.6;">
あなたは経験豊富なITコンサルタントです。<br/>
# 依頼内容<br/>
中小企業向けに、生成AIの業務活用について説明するレポートを作成してください。<br/>
# 形式<br/>
• 見出しは「1. 〇〇」「2. 〇〇」の形式<br/>
• 各セクションは200文字程度　・・・<br/>
# 含めてほしい内容<br/>
1. 生成AIとは何か<br/>
2. 中小企業にとってのメリット　・・・<br/>
</div>
</div>

</div>

---

## 良いプロンプトの例 2：データ分析

<div style="font-size: 0.85em;">

<div style="background: #ffebee; border: 2px solid #d32f2f; padding: 15px; border-radius: 8px; margin: 15px 0;">
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 8px;">❌ 悪い例</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.95em;">
この数字を分析して
</div>
</div>

<div style="background: #e8f5e9; border: 2px solid #29A87F; padding: 15px; border-radius: 8px; margin: 15px 0;">
<div style="font-weight: bold; color: #29A87F; margin-bottom: 8px;">✅ 良い例</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.9em; line-height: 1.6;">
あなたはデータアナリストです。<br/>
# データ<br/>
• 1月売上：500万円、2月：450万円、3月：600万円<br/>
• 1月訪問者：1000人、2月：900人、3月：1200人<br/>
# 分析してほしいこと<br/>
1. 月ごとの売上トレンド<br/>
2. 1人あたりの購入単価の変化　・・・<br/>
# 出力形式<br/>
• 箇条書きで簡潔に　・・・<br/>
</div>
</div>

</div>

---

## プロンプト作成のコツ

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin: 20px 0;">

<div style="background: #e3f2fd; border-left: 5px solid #1976d2; font-size: 0.85em; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #1976d2; font-size: 1.1em; margin-bottom: 10px;">📋 構造化する</div>
# 役割, # 依頼内容, # 形式 など、指示内容をセクションに分ける
</div>

<div style="background: #fff3e0; border-left: 5px solid #DDAC26; font-size: 0.85em; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #DDAC26; font-size: 1.1em; margin-bottom: 10px;">🎯 具体的に示す</div>
「短く」のような抽象的な表現ではなく、「200文字程度」のように具体的に指示する
</div>

<div style="background: #fce4ec; border-left: 5px solid #c2185b; font-size: 0.85em; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #c2185b; font-size: 1.1em; margin-bottom: 10px;">👤 役割を設定する</div>
「あなたは〇〇です」のように、生成AIに演じてほしい役割を設定する
</div>

<div style="background: #e8f5e9; border-left: 5px solid #29A87F; font-size: 0.85em; padding: 20px; border-radius: 8px;">
<div style="font-weight: bold; color: #29A87F; font-size: 1.1em; margin-bottom: 10px;">✨ 期待値を明示する</div>
何を、どのように、どう出力してほしいかなど、期待する回答内容を明確に指示する
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
💡 最初は上手くいかなくても大丈夫。試しながら改善していきましょう！
</div>

---

## 第 2 章のまとめ

✅ **モデル**：基盤モデルと大規模言語モデルは生成AIの「頭脳」

✅ **データ**：データの質が生成AIの回答精度を決める

✅ **プロンプト**：生成AIの能力をフル活用できるかどうかはプロンプト次第

<br/>
<br/>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
💡 この3つが理解できれば生成AIは怖くない！
</div>

---

## 目次

1. <font color=#E5E8EA>「生成AI」とは何か？</font>
   
2. <font color=#E5E8EA>生成AIに関する基礎知識</font>

3. Geakeを使ってみよう

4. <font color=#E5E8EA>生成AIを上手く使うコツ</font>

5. <font color=#E5E8EA>まとめ</font>

---

## 第 3 章で学ぶこと

実際にGeakeを使いながら、生成AIの基本動作を確認します。

<img src="../../assets/images/geake_logo.png" alt="Geake logo" width="50%" style="display: block; margin: 0 auto;">

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
💡 ぜひお手元のGeakeでもやってみてください！
</div>

---

## 実践 1：シンプルな質問をする

まずはシンプルな質問から始めます。（モデルは gemini-2.5-flash を使います）

<div style="background: #e8f5e9; border: 3px solid #29A87F; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-weight: bold; color: #29A87F; font-size: 1.2em; margin-bottom: 15px;">🎯 実践：シンプルな質問をしてみる</div>

<div style="background: white; font-size: 0.8em; font-family: monospace; padding: 20px; border-radius: 8px; margin: 15px 0;">
生成AIとは何ですか？初心者にもわかるように簡単に説明してください。
</div>

---

## 実践 2：プロンプトエンジニアリングを実践する

第2章で学んだ「プロンプトエンジニアリング」の知識にもとづいてプロンプトを改善してみます。

<div style="background: #e8f5e9; border: 3px solid #29A87F; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-weight: bold; color: #29A87F; font-size: 1.2em; margin-bottom: 15px;">🎯 実践：プロンプトエンジニアリングを実践してみる</div>

<div style="background: white; font-size: 0.8em; font-family: monospace; padding: 20px; border-radius: 8px; margin: 15px 0;">
# 役割<br/>
あなたは生成AIの専門家です。難しい生成AIの概念を、初心者にも分かりやすく伝えることに長けています。<br/>
<br/>
# 背景<br/>
あなたはこれから生成AIに興味を持つ中学生に対して、生成AIについての授業を行う予定です。<br/>
<br/>
# 依頼<br/>
上記の役割と背景を踏まえて、「生成AIとは何か？」を、中学生に分かりやすく説明してください。
</div>

---

## 実践 3：モデルを変える

実践2とまったく同じプロンプトを、別のモデル（gemini-2.5-pro）に投げてみます。

<div style="background: #e8f5e9; border: 3px solid #29A87F; padding: 25px; border-radius: 12px; margin: 20px 0;">
<div style="font-weight: bold; color: #29A87F; font-size: 1.2em; margin-bottom: 15px;">🎯 実践：モデルを変えてみる</div>

<div style="background: white; font-size: 0.8em; font-family: monospace; padding: 20px; border-radius: 8px; margin: 15px 0;">
# 役割<br/>
あなたは生成AIの専門家です。難しい生成AIの概念を、初心者にも分かりやすく伝えることに長けています。<br/>
<br/>
# 背景<br/>
あなたはこれから生成AIに興味を持つ中学生に対して、生成AIについての授業を行う予定です。<br/>
<br/>
# 依頼<br/>
上記の役割と背景を踏まえて、「生成AIとは何か？」を、中学生に分かりやすく説明してください。
</div>

---

## うまくいかないときの対処法

Geakeの回答が期待通りにならない時は、以下を試してみましょう。

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin: 20px 0;">

<div style="background: #e3f2fd; padding: 20px; border-radius: 10px; border-left: 5px solid #1976d2;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 10px;">➕ 追加で指示を出す</div>
<div style="font-size: 0.8em;">
・「もっと詳しく説明してください」<br/>
・「専門用語を減らしてください」<br/>
</div>
</div>

<div style="background: #fff3e0; padding: 20px; border-radius: 10px; border-left: 5px solid #DDAC26;">
<div style="font-weight: bold; color: #DDAC26; margin-bottom: 10px;">ℹ️ 指示を詳細化する</div>
<div style="font-size: 0.8em;">
・より具体的な情報を追加する<br/>
・より詳細な役割を与える<br/>
</div>
</div>

<div style="background: #fce4ec; padding: 20px; border-radius: 10px; border-left: 5px solid #c2185b;">
<div style="font-weight: bold; color: #c2185b; margin-bottom: 10px;">✏️ プロンプトを改善する</div>
<div style="font-size: 0.8em;">
「AIでプロンプトを改善」を試してみる
</div>
</div>

<div style="background: #e8f5e9; padding: 20px; border-radius: 10px; border-left: 5px solid #29A87F;">
<div style="font-weight: bold; color: #29A87F; margin-bottom: 10px;">🆕 新しいチャットで試す</div>
<div style="font-size: 0.8em;">
新しいスレッドに移動して、別の視点から質問してみる
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
💡 試行錯誤は学習のプロセス。恐れずに何度でもトライしましょう！
</div>

---

## 目次

1. <font color=#E5E8EA>「生成AI」とは何か？</font>
   
2. <font color=#E5E8EA>生成AIに関する基礎知識</font>

3. <font color=#E5E8EA>Geakeを使ってみよう</font>

4. 生成AIを上手く使うコツ

5. <font color=#E5E8EA>まとめ</font>

---

## 第 4 章で学ぶこと

生成AIを上手に使うための実践的なヒントと、知っておくべき注意点を理解します。

1. **プロンプトのレベルアップ**：より良い回答を得るための工夫を知る

2. **生成AIの限界**：生成AIと上手に付き合うために、その限界を知る

3. **安全な使い方**：責任を持って生成AIを利用するために守るべきことを知る

---

## プロンプトをレベルアップさせる 3 つのコツ

第3章でプロンプトエンジニアリングの基礎を学びました。
この章では、回答精度をさらに高めるためのコツを3つ紹介します。

<div style="display: flex; flex-direction: column; gap: 18px; margin: 25px 0;">

<div style="background: #e3f2fd; border-left: 8px solid #1976d2; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 1.5em;">💡</div>
<div>
<div style="font-weight: bold; color: #1976d2; font-size: 1.0em; margin-bottom: 5px;">1. 例を示す</div>
<div style="font-size: 0.8em;">期待する出力の形式や内容の例を1〜2個示すと、AIが回答形式を正確に理解します</div>
</div>
</div>
</div>

<div style="background: #fff3e0; border-left: 8px solid #DDAC26; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 1.5em;">🎭</div>
<div>
<div style="font-weight: bold; color: #DDAC26; font-size: 1.0em; margin-bottom: 5px;">2. 専門的な役割を与える</div>
<div style="font-size: 0.8em;">「あなたは〇〇の専門家です」のように伝えることで、専門的で適切な回答が得られやすくなります</div>
</div>
</div>
</div>

<div style="background: #e8f5e9; border-left: 8px solid #29A87F; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 1.5em;">🔄</div>
<div>
<div style="font-weight: bold; color: #29A87F; font-size: 1.0em; margin-bottom: 5px;">3. 対話を重ねる</div>
<div style="font-size: 0.8em;">最初の回答が不十分なら「もっと詳しく」「具体例を追加して」などと追加で指示を出します</div>
</div>
</div>
</div>

</div>

---

## コツ 1：例を示す

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px;">

<div style="background: #ffebee; border: 2px solid #d32f2f; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 12px; font-size: 1.1em;">❌ 例なし</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.8em; margin-bottom: 12px; line-height: 1.5;">
顧客レビューの感情を分析してください。<br/>
<br/>
「サポートが親切でした」
</div>
<div style="font-size: 0.8em;">
どのように分析すればいいのかAIにはわからず、<br/>回答形式がバラバラに
</div>
</div>

<div style="background: #e8f5e9; border: 2px solid #29A87F; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #29A87F; margin-bottom: 12px; font-size: 1.1em;">✅ 例あり</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.8em; margin-bottom: 12px; line-height: 1.5;">
例を参考に顧客レビューの感情を分析してください。<br/>
例）「商品が早く届いた」→ポジティブ<br/>
例）「対応が遅い」→ネガティブ<br/>
<br/>
「サポートが親切でした」
</div>
<div style="font-size: 0.8em;">
どのように分析すればいいかをAIに示すことで、<br/>一貫した回答形式に
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
💡 回答例を1〜2個示してあげるだけでも、回答の質が大きく向上します
</div>

---

## コツ 2：専門的な役割を与える

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px;">

<div style="background: #ffebee; border: 2px solid #d32f2f; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #d32f2f; margin-bottom: 12px; font-size: 1.1em;">❌ 役割指定なし</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.8em; margin-bottom: 12px; line-height: 1.5;">
データセキュリティの重要性を説明してください。
</div>
<div style="font-size: 0.8em;">
一般的で抽象的な回答になりがち
</div>
</div>

<div style="background: #e8f5e9; border: 2px solid #29A87F; padding: 20px; border-radius: 10px;">
<div style="font-weight: bold; color: #29A87F; margin-bottom: 12px; font-size: 1.1em;">✅ 役割指定あり</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.8em; margin-bottom: 12px; line-height: 1.5;">
あなたは情報セキュリティの専門家です。<br/>
中小企業の経営者向けに、データセキュリティの重要性を3つのポイントで説明してください。
</div>
<div style="font-size: 0.8em;">
生成AIに専門家として振る舞わせることで、<br/>正確性の高い回答に
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
💡「専門家」「プロフェッショナル」「経験豊富な〇〇」などを指定してみましょう
</div>

---

## コツ 3：対話を重ねる

<div style="display: flex; flex-direction: column; gap: 18px; margin: 25px 0;">

<div style="background: #e3f2fd; border-left: 8px solid #1976d2; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="flex: 1;">
<div style="font-weight: bold; color: #1976d2; font-size: 0.8em; margin-bottom: 5px;">1️⃣ 最初の指示</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.6em;">チームミーティングを効果的に実施するにはどうしたらいいですか？</div>
</div>
</div>
</div>

<div style="background: #fff3e0; border-left: 8px solid #DDAC26; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="flex: 1;">
<div style="font-weight: bold; color: #DDAC26; font-size: 0.8em; margin-bottom: 5px;">2️⃣ 追加指示</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.6em;">リモートワークでも実践できる方法に絞って、再度提案してください。</div>
</div>
</div>
</div>

<div style="background: #e8f5e9; border-left: 8px solid #29A87F; padding: 20px; border-radius: 8px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="flex: 1;">
<div style="font-weight: bold; color: #29A87F; font-size: 0.8em; margin-bottom: 5px;">3️⃣ 追加指示</div>
<div style="background: white; padding: 12px; border-radius: 5px; font-family: monospace; font-size: 0.6em;">「全員からの意見を促す」について、具体的にどのように発言を促せばよいですか？</div>
</div>
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; text-align: center; font-weight: bold;">
💡 対話を重ねることで、求める回答に近づいていきます
</div>

---

## 生成AIの限界

万能そうに見える生成AIですが、もちろんできないこともあります。
ここでは、生成AIが抱える2つの限界について説明します。

1. **ハルシネーション**

2. **ナレッジカットオフ**

---

## 生成AIの限界 1：ハルシネーション

事実に基づかない情報やもっともらしい嘘を、生成AIがあたかも真実であるかのように生成してしまう
現象のことを **「ハルシネーション（幻覚）」** と言います。

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; font-weight: bold;">
💡 対策<br/>
　・重要な情報は必ず事実確認をする<br/>
　・複数の情報源と照合して妥当性を検証する<br/>
　・グラウンディング（生成AIの出力を検証可能な情報源に紐付ける技術）で情報源を明示させる
</div>

<br/>

<div style="font-size: 0.8em;">

### なぜ起こる？

AIは統計的なパターンに基づいて応答しているだけで、**真実を理解しているわけではない**ため

</div>

---

## 生成AIの限界 2：ナレッジカットオフ

特定時点以降の知識を生成AIが持っていない現象のことを **「ナレッジカットオフ」** と言います。

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 15px; border-radius: 8px; font-weight: bold;">
💡 対策<br/>
　・いつ時点の情報に基づく回答かを意識しておく<br/>
　・通常の検索と組み合わせて利用する<br/>
　・DeepResearch機能を利用する
</div>

<br/>

<div style="font-size: 0.8em;">

### なぜ起こる？

AIモデルは特定時点までのデータを使って学習されており、**それ以降の知識は学習されていない**ため

</div>

---

## 責任あるAI利用

生成AIの限界をユーザー一人ひとりが正しく理解しておくとともに、生成された結果を鵜呑みにせず、
常に批判的な視点を持って利用することが重要です。

<br/>

### 利用者としての責任

✅ **批判的な視点**：AIの出力を鵜呑みにしない
✅ **検証の習慣**：重要な情報は必ず確認する
✅ **限界の理解**：何ができて何ができないかを知る
✅ **倫理的配慮**：バイアスや差別に注意を払う

---

## 安全に使うための心得

生成AIを安全に使うために、次のルールは必ず守ってください。

<div style="display: flex; flex-direction: column; gap: 15px; margin: 20px 0;">

<div style="background: #ffebee; border: 3px solid #d32f2f; padding: 20px; border-radius: 10px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 1.5em;">🔒</div>
<div>
<div style="font-weight: bold; color: #d32f2f; font-size: 1.0em; margin-bottom: 5px;">機密情報は入力しない</div>
<div style="font-size: 0.8em;">顧客情報、社内機密、個人情報などは絶対にAIに入力しないでください　　* GeakeはOK</div>
</div>
</div>
</div>

<div style="background: #fff3e0; border: 3px solid #DDAC26; padding: 20px; border-radius: 10px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 1.5em;">✅</div>
<div>
<div style="font-weight: bold; color: #DDAC26; font-size: 1.0em; margin-bottom: 5px;">生成物の内容を確認する</div>
<div style="font-size: 0.8em;">生成AIの出力をそのまま使わず、必ず人間が内容を確認・修正してから使用してください</div>
</div>
</div>
</div>

<div style="background: #e3f2fd; border: 3px solid #1976d2; padding: 20px; border-radius: 10px;">
<div style="display: flex; align-items: center; gap: 15px;">
<div style="font-size: 1.5em;">📋</div>
<div>
<div style="font-weight: bold; color: #1976d2; font-size: 1.0em; margin-bottom: 5px;">社内ルールを守る</div>
<div style="font-size: 0.8em;">「生成AI利活用ガイドライン」の内容を理解し、遵守してください</div>
</div>
</div>
</div>

</div>

---


## 第 4 章のまとめ

✅ **レベルアップする**：プロンプトエンジニアリングにはコツがある

✅ **限界を知る**：生成AIにはできないこともある

✅ **安全に使う**：ルールを守り、利用者の責任を果たしましょう

<br/>
<br/>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
💡 生成AIの限界と利用のルールを理解した上で、安全＆便利に利用しましょう！
</div>

---

## 目次

1. <font color=#E5E8EA>「生成AI」とは何か？</font>
   
2. <font color=#E5E8EA>生成AIに関する基礎知識</font>

3. <font color=#E5E8EA>Geakeを使ってみよう</font>

4. <font color=#E5E8EA>生成AIを上手く使うコツ</font>

5. まとめ

---

## 全体の振り返り



<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin: 20px 0;">

<div style="background: #e3f2fd; padding: 20px; border-radius: 10px; border-left: 5px solid #1976d2;">
<div style="font-weight: bold; color: #1976d2; margin-bottom: 10px;">1️⃣ 第 1 章</div>
<div style="font-size: 0.7em;">
・「AI」の全体像：生成AIはAIの応用分野<br/>
・生成AIの4つの能力：作成、要約、自動化、発見<br/>
・マルチモーダルの概念：画像・音声・コードも扱える
</div>
</div>

<div style="background: #fff3e0; padding: 20px; border-radius: 10px; border-left: 5px solid #DDAC26;">
<div style="font-weight: bold; color: #DDAC26; margin-bottom: 10px;">2️⃣ 第 2 章</div>
<div style="font-size: 0.7em;">
・モデル：基盤モデル（土台）と大規模言語モデル（言語特化）<br/>
・データ：データの質が生成AIの回答精度を決める<br/>
・プロンプト：生成AIとやり取りするための方法
</div>
</div>

<div style="background: #fce4ec; padding: 20px; border-radius: 10px; border-left: 5px solid #c2185b;">
<div style="font-weight: bold; color: #c2185b; margin-bottom: 10px;">3️⃣ 第 3 章</div>
<div style="font-size: 0.7em;">
・プロンプトエンジニアリングの例<br/>
・モデル変更の例<br/>
・うまくいかないときの対処法
</div>
</div>

<div style="background: #e8f5e9; padding: 20px; border-radius: 10px; border-left: 5px solid #29A87F;">
<div style="font-weight: bold; color: #29A87F; margin-bottom: 10px;">4️⃣ 第 4 章</div>
<div style="font-size: 0.7em;">
・プロンプトエンジニアリングのコツ：例、専門性、対話<br/>
・生成AIの限界：ハルシネーション、ナレッジカットオフ<br/>
・安全に使うための心得：機密保持、生成物確認、ルール遵守
</div>
</div>

</div>

<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; padding: 20px; border-radius: 10px; text-align: center; font-size: 1.1em; font-weight: bold;">
💡 兎にも角にも「まずは使ってみる」から始めましょう！
</div>

---

<!-- _backgroundColor: #0a1929 -->
<!-- _color: white -->

![bg](../../assets/images/3shake-background-full.png)

<div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); text-align: center; width: 80%;">

<div style="font-size: 3em; font-weight: bold; margin-bottom: 30px; text-shadow: 2px 2px 4px rgba(0,0,0,0.3);">
ありがとうございました！
</div>

</div>
