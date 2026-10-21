# SlideKit

PowerPoint と Excel の作業をキーボード中心で速くする Office アドインです。

- 図形の揃え・均等配置・サイズ揃え・グリッド整列・重ね順
- 滝グラフ・積み上げ棒・Marimekko・Gantt をデータから図形で作成
- ハーベイボール・プロセスフロー・アジェンダ（各章の前に現在地付き）
- Excel: 数値/日付/文字色/塗り/罫線の巡回、参照元・参照先ジャンプ、エラーや直書き数値の検出

対応: PowerPoint / Excel for Mac 16.105 以降（Microsoft 365）。

## インストール

1. 次の 2 つをダウンロードします。
   - PowerPoint 用: [package-ppt.zip](https://sgymdik.github.io/slidekit/package-ppt.zip)
   - Excel 用: [package-xl.zip](https://sgymdik.github.io/slidekit/package-xl.zip)
2. ターミナルで、自分の Microsoft 365 アカウントに登録します（個人用）。

   ```bash
   npx -y -p @microsoft/m365agentstoolkit-cli atk auth login m365
   npx -y -p @microsoft/m365agentstoolkit-cli atk install --file-path package-ppt.zip --scope Personal
   npx -y -p @microsoft/m365agentstoolkit-cli atk install --file-path package-xl.zip --scope Personal
   ```

3. PowerPoint / Excel を ⌘Q で終了して開き直すと、「SlideKit」タブが出ます。

組織の設定でカスタムアプリのアップロードが禁止されている場合は、登録できません。

## 使い方

| やりたいこと | 操作 |
|---|---|
| コマンドを探して実行 | ⌃⌥P（コマンドパレット）→ やりたいことを入力、または 2 文字のコード |
| ショートカット一覧 | ⌃⌥K |
| 選択に応じたヒント | ⌃⌥I |
| リボンを番号で操作 | ⌥ → Y → 番号 |

### ⌥ → Y → 番号 を使うには

Mac の Office は、リボンの文字表示（KeyTips）が初期状態でオフです。PowerPoint・Excel それぞれで 1 回だけ設定してください。

1. メニューバーの **PowerPoint（Excel）> 環境設定 > アクセシビリティ**
2. **KeyTips** の「アクティブ化キー」で **Option（⌥）** を選ぶ

1〜9 はよく使う操作、それ以外は「グループの頭文字 + 番号」です（例: 右揃え = ⌥ → Y → A2）。番号はボタン名の先頭とツールチップに出ています。

## アンインストール

```bash
npx -y -p @microsoft/m365agentstoolkit-cli atk uninstall --mode title-id --title-id <登録時に表示された TitleId> --interactive false
```

## ライセンス

MIT
