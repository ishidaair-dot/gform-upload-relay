# Googleフォーム用 ファイルアップロード中継ページ（relay.html）

このリポジトリは、Googleフォームで **ログイン不要のファイルアップロード** を実現するための  
「中継ページ（relay.html）」を公開するためのものです。

Googleフォームの仕様上、外部リンクで開いたタブを自動で閉じることができないため、  
中継ページを GitHub Pages 上に配置し、以下の動作を実現します。

- ① Googleフォーム内のリンク → relay.html を新規タブで開く  
- ② relay.html が GAS（File Uploader App）にリダイレクト  
- ③ アップロードが完了したら relay.html に戻る  
- ④ relay.html が自動でタブを閉じる

この流れによって、ユーザーは **「アップロード後、元のフォーム画面に戻る」** 体験が可能になります。

---

## 📂 ファイル構成
├─ index.html（任意・未使用の場合は削除可）
└─ relay.html ← Googleフォームに貼るリンク用ページ


---

## 🌐 GitHub Pages での公開

GitHub Pages は以下の設定で公開しています。

- **公開対象ブランチ**： main  
- **公開ディレクトリ**： /（root）  

公開URL は以下です：
https://ishidaair-dot.github.io/gform-upload-relay/relay.html


Googleフォームの説明文やボタンリンクには、この URL を貼り付けてください。

---

## 📝 relay.html の役割

relay.html は以下のことを行うシンプルな中継ページです。

1. GAS アプリの URL へ即時リダイレクト  
2. GAS 処理完了後、また relay.html に戻る  
3. 画面を自動で閉じる（ブラウザの許可範囲内で実行）

ブラウザ側の制限で完全に閉じられない場合もありますが、  
最も安全かつ一般的に実現できる方法です。

---

## 🛠 使用方法（概要）

1. このリポジトリをフォーク or クローン  
2. relay.html に GAS Webアプリの URL を設定  
3. GitHub Pages を有効化  
4. Googleフォームに  
   `https://ishidaair-dot.github.io/gform-upload-relay/relay.html`  
   を貼る

---

## 📌 注意点

- Googleフォームは外部サイトのウィンドウを強制的に閉じる操作を禁止しているため、  
  **中継ページを経由する方法が最も安定**します。  
- iPhone Safari では自動 close が OS によって制限されることがあります。

※このリポジトリは個人利用のための公開です。他者による利用は想定していません。
