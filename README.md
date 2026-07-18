# ことば10（初版）

スマートフォンで使える、4択式の単語学習Webアプリです。

## 収録内容

- 中国語（簡体字／繁体字）60語
- 韓国語 60語
- エスペラント語 60語
- 1セット10問
- 日本語→外国語、外国語→日本語、ランダム
- 誤答記録と誤答のみの復習
- 例文表示
- 学習履歴
- JSON形式のバックアップ／復元
- スマートフォン対応、PWA、オフライン利用

収録語彙は日常的なA1〜A2程度を目安にした初版です。

## 手元で確認する方法

`index.html`を直接開くと基本機能を確認できます。ただし、オフライン機能（Service Worker）は
HTTPSまたはローカルサーバー上でのみ動作します。

パソコンにPythonがある場合は、このフォルダーで次を実行できます。

```bash
python -m http.server 8000
```

その後、ブラウザーで `http://localhost:8000` を開きます。

## GitHub Pagesで公開する方法

1. GitHubにログインします。
2. `kotoba10` などの名前で新しいリポジトリを作ります。
3. このフォルダー内のファイルをすべてアップロードします。
4. リポジトリの `Settings` → `Pages` を開きます。
5. `Build and deployment` の `Source` を `Deploy from a branch` にします。
6. Branchを `main`、フォルダーを `/(root)` にして保存します。
7. 数分後に表示されるURLを開きます。

## iPhoneでアプリのように使う方法

1. 公開URLをSafariで開きます。
2. 共有ボタンを押します。
3. `ホーム画面に追加` を選びます。

## 単語を追加する方法

`words.js` の各言語の配列に、既存データと同じ形式で項目を追加します。
IDは重複しないようにしてください。

### 中国語

```javascript
{
  "id": "zh061",
  "simplified": "旅行",
  "traditional": "旅行",
  "pinyin": "lǚxíng",
  "japanese": "旅行",
  "exampleSimplified": "我喜欢旅行。",
  "exampleTraditional": "我喜歡旅行。",
  "exampleJapanese": "私は旅行が好きです。",
  "category": "日常"
}
```

### 韓国語・エスペラント語

```javascript
{
  "id": "ko061",
  "word": "여행",
  "japanese": "旅行",
  "example": "저는 여행을 좋아해요.",
  "exampleJapanese": "私は旅行が好きです。",
  "category": "日常"
}
```

## 保存について

学習記録はブラウザーの `localStorage` に保存されます。
ブラウザーのデータ削除や端末変更で失われるため、設定画面から定期的にバックアップしてください。
