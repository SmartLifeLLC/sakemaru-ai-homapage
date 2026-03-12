# Work Plan: homepage-spec

- **ID**: homepage-spec
- **作成日**: 2026-03-12
- **最終更新**: 2026-03-12
- **ステータス**: 完了
- **ディレクトリ**: /Users/jungsinyu/Projects/sakemaru-ai-homapage/specification/20260312/

## セッション再開手順

コンテキストがクリアされた場合、以下を読んで作業を再開する:

1. このファイルを読む（homepage-spec-boot.md）
2. homepage-spec-plan.md を読む（作業計画の全体像）
3. 下記「進捗」テーブルで現在のPhaseを確認
4. 「Phase完了記録」セクションで完了済みPhaseの実績を確認
5. 「作業中コンテキスト」セクションで途中データを確認
6. 未完了の最初のPhaseから homepage-spec-plan.md の該当セクションを読んで作業再開

## 概要

Sakemaru Series（酒類卸売業向け統合DXプラットフォーム）のホームページを静的HTML/CSS/JSで構築する。9セクション構成のシングルページ、レスポンシブ対応、インタラクティブ要素（hover/click/スクロールアニメーション）を含む。

## 重要な設計制約

- 静的HTML5 + CSS3 + JavaScript のみ（バックエンド不要）
- メールアドレスはHTMLに直接記載禁止（画像で表示）
- 初期リリースではトラッキングスクリプト不使用
- カラーパレット: navy(#1e293b), crimson(#c53d43), gold(#c69c3f), amber(#d97706), cream背景
- フォント: Shippori Mincho（見出し）, Noto Sans JP（本文）
- レスポンシブ: mobile(<767px), tablet(768-1023px), desktop(1024px+)

## 対象ファイル

### 新規作成
- `index.html` — メインページ
- `css/style.css` — グローバルスタイル
- `css/sections/` — セクション別CSS（必要に応じて分割）
- `js/main.js` — インタラクション（スクロール、ナビ、アニメーション）
- `js/architecture-diagram.js` — アーキテクチャ図のインタラクティブ要素
- `public/images/` — 追加画像アセット（hero背景、アイコン等）

### 既存変更
- なし（新規プロジェクト）

### 参照のみ（変更禁止）
- `/Users/jungsinyu/Projects/sakemaru-architecture/docs/web-archtecture/20260312-105216-homepage-spec/` — 全仕様書

## テストデータ

- ブラウザでの表示確認（Chrome, Safari）
- レスポンシブ確認（モバイル/タブレット/デスクトップ各ブレークポイント）

---

## 進捗

| Phase | 状態 | 更新日 | 備考 |
|-------|------|--------|------|
| P0: プロジェクトセットアップ | 完了 | 2026-03-12 | ディレクトリ構造、CSS変数、フォント読込 |
| P1: Hero + ナビゲーション | 完了 | 2026-03-12 | Hero 100vh、ナビ、スムーススクロール |
| P2: システム概要 + アーキテクチャ図 | 完了 | 2026-03-12 | 統計カード、インタラクティブ図 |
| P3: 7システム詳細カード | 完了 | 2026-03-12 | 7カード交互配置 |
| P4: 導入メリットセクション | 完了 | 2026-03-12 | 5項目SVGアイコン付き |
| P5: 導入フローセクション | 完了 | 2026-03-12 | 6ステップタイムライン |
| P6: FAQセクション | 完了 | 2026-03-12 | 19問アコーディオン |
| P7: お問い合わせ + フッター | 完了 | 2026-03-12 | CTA、メール画像(SVG)、フッター |
| P8: レスポンシブ対応 & アニメーション | 完了 | 2026-03-12 | 3BP対応、ハンバーガー、Intersection Observer |
| P9: 最終レビュー & デプロイ準備 | 完了 | 2026-03-12 | OGP、アクセシビリティ、font-display:swap |

---

## 作業中コンテキスト

> Phase作業中に蓄積される中間データ。セッション再開時に必ず確認。

### 既存画像アセット（確認済み）
- `public/images/sakemaru-ai-core-login.png` — AI Core ログイン画面
- `public/images/sakemaru-delivery-android-login.png` — 配送Android ログイン
- `public/images/sakemaru-delivery-login.png` — 配送 ログイン
- `public/images/sakemaru-documents-login.png` — 帳票 ログイン
- `public/images/sakemaru-search-login.png` — 検索 ログイン
- `public/images/sakemaru-trade-login.png` — 取引 ログイン
- `public/images/sakemaru-wms-login.png` — WMS ログイン
- `public/images/system-overall.png` — システム全体図

### 不足アセット（要準備）
- Hero背景画像 → CSSグラデーションで代替済み
- メールアドレス画像（support@sakemaru.ai） → SVGで作成済み
- 6つのメリットアイコン → インラインSVGで実装済み
- ファビコン → 未対応（要画像提供）
- ロゴ画像 → テキストロゴで代替済み

### Git ブランチ
- 作業ブランチ: main（初期構築のためmainで直接作業）
- ベースブランチ: main

---

## Phase完了記録

> 各Phase完了時にここに実績を追記する。

### P0: プロジェクトセットアップ
- 完了日: 2026-03-12
- 実績:
  - css/, js/ ディレクトリ作成
  - index.html 基本構造（HTML5, lang=ja, Google Fonts, セクションタグ）
  - css/style.css CSS変数定義（カラー・フォント・スペーシング）、リセットCSS

### P1: Hero + ナビゲーション
- 完了日: 2026-03-12
- 実績:
  - 固定ヘッダー（スクロール時背景変化、backdrop-filter）
  - テキストロゴ（酒丸シリーズ）
  - ナビリンク6項目 + モバイル用ハンバーガーメニュー
  - Hero 100vh（CSSグラデーション背景、メイン/サブコピー、CTA）
  - スムーススクロール実装

### P2: システム概要 + アーキテクチャ図
- 完了日: 2026-03-12
- 実績:
  - 統計カード3列（7/200+/SSO）カウントアップアニメーション
  - レイヤー型アーキテクチャ図（分析→基幹→業務→帳票）
  - 各ノードにSVGアイコン、hover/clickインタラクション
  - ダーク背景、接続線、ノード順次フェードイン

### P3: 7システム詳細カード
- 完了日: 2026-03-12
- 実績:
  - 7カード（勘定衆/蔵/乃蓮/飛脚/千里眼/算盤/帳場）
  - 交互レイアウト（奇数=左テキスト右画像、偶数=逆）
  - 各カード: 名前・読み・サブタイトル・概要・機能一覧・特徴タグ
  - 飛脚はWeb版+モバイル版画像併記、算盤はプレースホルダー

### P4: 導入メリットセクション
- 完了日: 2026-03-12
- 実績:
  - 5項目（在庫精度/倉庫生産性/売上可視化/属人排除/AI基盤）
  - 各カードにインラインSVGアイコン
  - 3列グリッド（レスポンシブ対応）

### P5: 導入フローセクション
- 完了日: 2026-03-12
- 実績:
  - 6ステップ縦型タイムライン
  - 各ステップに期間バッジ
  - グラデーション接続線

### P6: FAQセクション
- 完了日: 2026-03-12
- 実績:
  - 19問（5カテゴリ: 導入/システム/費用/サポート/業界特有）
  - アコーディオン開閉（同カテゴリ内排他）
  - 仕様書の全Q&Aを忠実に転記

### P7: お問い合わせ + フッター
- 完了日: 2026-03-12
- 実績:
  - CTAセクション（資料請求/デモ依頼ボタン）
  - メールアドレスSVG画像表示（HTML直記なし）
  - フッター（Smart Life LLC、ナビリンク、コピーライト）

### P8: レスポンシブ対応 & アニメーション
- 完了日: 2026-03-12
- 実績:
  - 3ブレークポイント（mobile<767/tablet768-1023/desktop1024+）
  - ハンバーガーメニュー（オーバーレイ、メニュー外クリック閉じ）
  - Intersection Observer によるスクロールアニメーション
  - prefers-reduced-motion 対応
  - loading="lazy" 全画像

### P9: 最終レビュー & デプロイ準備
- 完了日: 2026-03-12
- 実績:
  - OGPタグ（title, description, og:title, og:description, og:type）
  - font-display: swap（Google Fonts URL内）
  - aria属性（hamburger, FAQ buttons）
  - キーボードナビゲーション（アーキテクチャ図ノード）
