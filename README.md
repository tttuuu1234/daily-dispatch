# daily-dispatch

技術と暮らしのニュースを新聞風HTMLにまとめる、個人用日刊紙「Daily Dispatch」を毎日投稿するリポジトリです。手元では `/make-newspaper` でも呼び出せます。

## 構成

```
.
├─ .claude/
│  └─ skills/
│     ├─ commit/SKILL.md            変更をmainに直接pushする
│     ├─ create-pr/SKILL.md         作業ブランチにpushしてPRを作る
│     ├─ clean-dot-underscore/      macOSの ._ ファイルを消す
│     └─ make-newspaper/            新聞作成スキル
│        ├─ SKILL.md                毎日の編集方針。スキルの本体
│        ├─ template.html           見た目のテンプレート
│        ├─ scripts/build_index.py  バックナンバー一覧を作る
│        └─ routine-prompt.txt      ルーティンの指示欄に貼る文
├─ index.html                       バックナンバー一覧(自動生成)
└─ archive/YYYY-MM-DD.html          各号
```

## 掲載内容

| セクション | 件数 | 対象期間 | 掲載する日 |
|---|---|---|---|
| AIニュース | 5 | 過去48時間 | 毎日 |
| ITニュース | 5 | 過去48時間 | 毎日 |
| Flutter | 10 | 過去7日 | 土曜のみ |
| セキュリティ | 5 | 過去48時間 | 毎日 |
| キャリア / 人生観 / 名言 | 各1 | 直近1か月 | 毎日 |

編集方針を変えたいときは、`.claude/skills/make-newspaper/SKILL.md` を編集してpushする。

## 読み方

- ローカル: `git pull` して、`index.html` をブラウザで開く。
- GitHub Pages: 設定で `main` ブランチの `/ (root)` を公開元にする(公開範囲に注意)。

## ルーティンの設定

1. claude.ai/code/routines で新規作成する。
2. 指示欄に `.claude/skills/make-newspaper/routine-prompt.txt` の内容を貼る。
3. リポジトリに `daily-dispatch` を選ぶ。
4. 環境のネットワークアクセスを「Full」か、ニュースサイトを許可した「Custom」にする。
5. コネクタは、すべて外す。
6. トリガーはスケジュール(毎日朝)にする。
7. 最初に「Run now」で試し、実行の記録を開いて結果を確認する。
