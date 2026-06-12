# Active STORY LIFF プロジェクト

LINE公式アカウント（@196ytvjn）のLIFFフォーム＋リッチメニュー応答システム。

## 構成

| ファイル | 役割 |
|---------|------|
| `index.html` | LINEアンケートフォーム（LIFF） |
| `seminar.html` | セミナー申込フォーム（LIFF） |
| `faq.png` / `faq-preview.jpg` | Q&A応答用画像（原寸／プレビュー用1MB以下） |
| `gas/Code.gs` | GAS統合スクリプト v3（**トークンを含むためGit管理外**） |

- GitHubリポジトリ: https://github.com/ya20100809-boop/activestory-liff （公開）
- スプレッドシートID: `1ZFGWdAthO3J0Yo2u-DE8Hlzm96A-kUUekaWcVn6K970`
- GAS URL: `https://script.google.com/macros/s/AKfycbx_UjLeyVD6ZFM0xYFo724tlctb7sWycUeKXfGt73CPFvgKfTeaW9o4PDguCi4yr2XrrA/exec`

## 実装済み機能（Code.gs v3）

- **友達追加**: ウェルカムメッセージ＋紹介コード入力案内
- **「紹介コード発行」**: AS-XXXXXX発行・再送、紹介人数管理
- **紹介コード入力（AS-）**: クーポン発行（双方）、1/5/10人達成特典
- **クーポンコード入力（GIFT-）**: 使用済み処理
- **「Active STORYって？」**: Flexカルーセル（概要＋コーチ4名）
- **「Q&A」**: FAQ画像を返信（jsDelivr CDN経由）
- **「まず話してみる」「体験希望」**: コーチ選択クイックリプライ → 体験希望受付
- **LIFFフォーム**: アンケート（グループ判定・Re-Roots案内）／セミナー申込（type振り分け）

## 重要ルール

- **GASを再デプロイしたら**: 「既存デプロイの編集→新バージョン」ならURL不変。**新規デプロイにした場合は index.html / seminar.html の GAS_URL を必ず貼り替える**
- **gas/Code.gs はプッシュ禁止**（チャネルアクセストークン入り。.gitignore済み）
- このMacにはGitHubの認証情報がない → プッシュはターミナルでPAT入力 or GitHub Web UIでアップロード

## 未解決・保留

- [ ] faq.png / faq-preview.jpg のプッシュ（認証がなくローカルから未プッシュ。2026-06-12時点）
- [ ] GASエディタに最新 Code.gs を反映して再デプロイ
- [ ] リッチメニュー側のメッセージアクション設定確認（「紹介コード発行」「Q&A」「Active STORYって？」「まず話してみる」がテキスト送信になっているか）
- [ ] `REROOTS_DATE`（現在「未定」）と `REROOTS_IMAGE_URL`（空）の設定
- [ ] 実機テスト：Q&A画像・体験希望フロー・紹介コードフロー

## 次にやるべきこと（直近タスク）

1. faq.png / faq-preview.jpg をGitHubにプッシュ → jsDelivr URLが有効化
2. Code.gs をGASに反映・再デプロイ
3. LINE実機でリッチメニュー全ボタンの応答テスト
