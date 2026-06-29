# 読者公開用サイト

このディレクトリだけをホスティング先へ公開する。

## 公開ページ

- `index.html`：キーワード入力式の資料照会端末
- `text-index.html`：JavaScriptや画像を使用しない文字資料版
- 完全版・予告版は別リポジトリ `unregistered-broadcast-web` で公開する

## 更新

作中資料や画像を更新した後、プロジェクト直下で次を実行する。

```sh
ruby build_public.rb
```

この処理は12資料、表示用CSS・JavaScript、公開画像をコピーし、会議録・資料プロファイルを除いた公開専用 `meeting-data.js` を生成する。

## 公開前確認

- `arg/01_release_timing.md` と章公開位置が一致している。
- `public/app.js` の照会語ハッシュを不用意に変更していない。
- `public/` 以外をアップロード対象にしていない。
- 404ページがホスティングサービスのカスタム404として設定されている。
- HTTPSで公開され、照会語のSHA-256照合が動作する。
- スマートフォン幅、画像非表示、JavaScript無効時を確認する。

## JavaScript無効時

資料解放機能は動作しない。`text-index.html` と小説本文だけで情報不足が起きない設計とする。
