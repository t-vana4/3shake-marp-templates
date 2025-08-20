---
marp: true
theme: ../../themes/3shake-theme.css
paginate: true
math: mathjax
mermaid: true
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
  /* カスタムテーマにMermaidのスタイル設定を追加 */
  mermaid {
    display: block;
    margin: 0 auto;
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

# <span style="font-size: 0.8em;">顧客案件における</br>生成AI利用ガイドラインの説明</span>

</div>

<div class="author-info" style="text-align: left; padding-left: 0; text-indent: 0;">
2025/08/27　月次締め会</br>Hajime Tachibana
</div>

---

## なぜガイドラインが必要なのか？

[『顧客案件における生成AI利用ガイドライン』](https://www.notion.so/3shake/AI-224b1e6bcbc280cb82fddae88eed6b73?source=copy_link)は、生成AIの利用を制限するためのものではなく、
生成AIを顧客案件で<span class="highlight-red">**「安全」かつ「戦略的」に活用できるようにするための指針**</span>です。

<br>

エンジニアのみなさんが生成AIを安心して使いこなすための<span class="highlight-red">**「攻めのガードレール」**</span>となるように、
このガイドラインを策定しました。

---

## 今日の最重要ポイント

1.  **生成AIは「武器」である**
  <span style="font-size: 0.85em;">簡単な作業はAIに任せ、私たちはより価値の高い仕事に集中しましょう。</span>
<br>
2.  **成果物責任は「人」にある**
  <span style="font-size: 0.85em;">AIは優秀なアシスタントですが、成果物に対する最終責任は私たち人間が負います。</span>
<br>
3.  **「顧客からの信頼」がすべて**
  <span style="font-size: 0.85em;">私たちのビジネスは顧客の信頼の上に成り立っています。信頼を壊すようなルール違反はしないでください。</span>

---

## 基本方針

顧客案件における生成AIの基本的な利用方針は次のとおりです。

<style>
.container { display: flex; gap: 20px; align-items: stretch; margin-top: 20px !important; }
.box { flex: 1; padding: 15px; border-radius: 10px; }
.box h3 { text-align: center; margin-top: 0; padding-bottom: 10px; border-bottom: 2px solid; }
.box ul { font-size: 0.85em; margin-top: 10px !important; }
.allow { border: 2px solid #28a745; }
.allow h3 { color: #28a745; border-color: #28a745; }
.deny { border: 2px solid #dc3545; }
.deny h3 { color: #dc3545; border-color: #dc3545; }
</style>

<div class="container">
<div class="box allow">
<h3>✅ どんどんやろう！</h3>
<ul>
<li>コード生成・リファクタリング</li>
<li>ドキュメント作成</li>
<li>問題解決・デバッグ</li>
<li>学習・スキルアップ</li>
<li>一般的な情報収集</li>
</ul>
</div>
<div class="box deny">
<h3>🚫 これはやめて！</h3>
<ul>
<li><span class="highlight-red">顧客固有の機密情報</span>を含む作業</li>
<li><span class="highlight-red">本番環境</span>に影響を及ぼす作業</li>
<li><span class="highlight-red">無検証</span>での変更マージ</li>
<li><span class="highlight-red">セキュリティ関連</span>の実装</li>
<li>顧客との<span class="highlight-red">合意なき</span>設計変更</li>
</ul>
</div>
</div>

万が一何かあっても致命的な影響が出ない作業では、積極的にAIを活用しましょう！

---

## 重要ルール 1.　入力禁止情報

情報漏洩時の影響が非常に大きいため、以下の情報はその一部であっても、
<span class="highlight-red">**会社が許可したAIツール以外への入力を禁止します。**</span>

- 顧客のソースコード、設定ファイル（Terraform, Kubernetesマニフェスト等）
- 顧客システムの構成情報、ネットワーク図、IPアドレス、ドメイン名
- APIキー、パスワード、証明書などのクレデンシャル情報
- 顧客から預託されたデータ（個人情報、決済情報など）
- 顧客の社内情報（従業員名、メールアドレス、非公開のプロジェクト名、資料）
- 当社と顧客、または第三者との間で締結したNDA（秘密保持契約）対象の情報

---

## 重要ルール 2.　禁止操作

直接的な情報入力でなくとも、以下ような操作は禁止です。

- Auto-approve 機能のような、人間がレビューできない自動操作
- 開発元が不明、あるいは非公式な外部ツール（ブラウザ拡張機能やMCPサーバーなど）の使用

---

## 重要ルール 3.　品質担保

AIの生成物はそのままでは使えません。人間による品質保証が必須です。

<style>
.container-qual { display: flex; gap: 20px; align-items: top; margin-top: 20px !important; }
.box-qual { flex: 1; padding: 15px; border-radius: 10px; border: 2px solid; }
.box-qual h3 { text-align: center; margin-top: 0; padding-bottom: 10px; border-bottom: 1px solid; }
.box-qual ul { font-size: 0.8em; margin-top: 10px !important; padding-left: 20px; }
.risk { border-color: #dc3545; }
.risk h3 { color: #dc3545; }
.process { border-color: #28a745; }
.process h3 { color: #28a745; }
</style>

<div class="container-qual">
<div class="box-qual risk">
<h3>⚠️ 生成物が内包するリスク</h3>
<ul>
<li><b>もっともらしい嘘 (ハルシネーション)：</b> 存在しない関数や古い技術を提案してしまう</li>
<li><b>脆弱なコード：</b> SQLインジェクション等の脆弱性を含んだコードを生成してしまう</li>
<li><b>ライセンス違反：</b> GPLライセンス等に該当するコードを混入させてしまう</li>
<br>
などなど...
</ul>
</div>
<div class="box-qual process">
<h3>🏁 必須の品質保証プロセス</h3>
<ol>
<li><b>担当者による理解・修正</b></li>
<li><b>ピアレビュー</b></li>
<li><b>静的解析・脆弱性スキャン</b></li>
<li><b>動作確認</b></li>
</ol>
</div>
</div>

AIの生成物は「素材」と捉え、最終的な成果物には<span class="highlight-red">**私たち人間が責任を持ちましょう。**</span>

---

## 重要ルール 4.　顧客との合意

AIツールの利用方針を事前に顧客に説明して合意してください。

<style>
.agreement-table { width: 100%; border-collapse: collapse; margin-top: 15px !important; font-size: 22px; }
.agreement-table th, .agreement-table td { border: 1px solid #ccc; padding: 12px; text-align: left; }
.agreement-table th { background-color: #f2f2f2; font-weight: bold; }
.agreement-table .level2-row { background-color: #e6f7ff; font-weight: bold; }
</style>

<table class="agreement-table">
  <thead>
    <tr>
      <th>レベル</th>
      <th>呼称</th>
      <th>利用範囲の概要</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>レベル0</td>
      <td>利用禁止</td>
      <td>AIツールの一切の利用禁止</td>
    </tr>
    <tr>
      <td>レベル1</td>
      <td>限定的な利用</td>
      <td>顧客情報を扱わない一般的な調査・検証のみ利用可能</td>
    </tr>
    <tr class="level2-row">
      <td>レベル2</td>
      <td>標準的な利用</td>
      <td>ガイドラインに則り、会社が許可したツールを利用可能</td>
    </tr>
    <tr>
      <td>レベル3</td>
      <td>高度な利用</td>
      <td>顧客の許諾を得て、個別に契約したツールも利用可能</td>
    </tr>
     <tr>
      <td>レベル4</td>
      <td>戦略的な利用</td>
      <td>顧客と合意した上で、ガイドラインのルールに準拠しないツールも積極的に利用可能</td>
    </tr>
  </tbody>
</table>

<div style="font-size: 0.7em; text-align: left; margin-top: 10px !important; padding-right: 20px;">
* 契約で特に規定がない場合は<span class="highlight-red">「レベル2」</span>を適用します
</div>

---

## 使えるツールの条件

新しい生成AIツールを利用したい場合、以下のような条件を満たしているかどうかを調査した上で、
総合的に利用可否を判断します。

- **データ非学習保証：** 入力データがAIの学習に使われない
- **暗号化通信：** やり取りが暗号化されている
- **ユーザー認証：** 会社のGoogleアカウントでログインできる
- **データ保存ポリシーの明示：** 保存期間や暗号化方法が明示されている
- **企業向けプラン：** 法人として契約できる

<br>

<div style="font-size: 0.7em; text-align: left; margin-top: 10px !important; padding-right: 20px;">
* 利用可能なツールは『承認済みAIツールリスト』を確認してください。<span class="highlight-red">リストにないツールの利用は厳禁です！</span>
</div>

---

## インシデント発生時の対応

- 万が一、情報漏洩などを起こしてしまった（または、その可能性に気づいた）場合は、
<span class="highlight-red">**隠さず、遅らせず、速やかに報告**</span>してください。自己判断は禁物です。
- 報告後は指示があるまで、関連データやログを削除したり、環境を変更したりしないでください。

<style>
.incident-container { display: flex; gap: 20px; align-items: top; margin-top: 20px !important; }
.incident-box { flex: 1; padding: 15px; border-radius: 10px; border: 1px solid #ccc; font-size: 0.9em; }
.incident-box h3 { text-align: center; margin-top: 0; padding-bottom: 10px; border-bottom: 1px solid #999; font-size: 1.1em; }
.incident-box ul { padding-left: 20px; }
</style>

<div class="incident-container">
<div class="incident-box">
<h3>📢 まず、誰に報告する？</h3>
<ul>
  <li>プロジェクトマネージャー (PM)</li>
  <li>部長</li>
  <li>チームリーダー</li>
</ul>
</div>
<div class="incident-box">
<h3>📋 何を報告する？</h3>
<ul>
  <li><b>When：</b> いつ (問題に気づいた日時)</li>
  <li><b>Where：</b> どこで (利用したツールなど)</li>
  <li><b>Who：</b> 誰が (操作した人)</li>
  <li><b>What：</b> 何を (問題の操作)</li>
  <li><b>Why：</b> なぜ (操作の目的)</li>
  <li><b>How：</b> どのように (発覚の経緯)</li>
</ul>
</div>
</div>

---

## おわりに

生成AIは非常に便利なツールですが、利用には相応のリスクも伴います。
ルールを守って便利に使いましょう。

<br>

<span style="font-size: 50px;">**ご清聴ありがとうございました**</span>
