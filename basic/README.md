# gitの使い方を改めて学ぶ

```shell
git init （リポジトリを作る）
git status （状況を確認する）
git add （ステージする）
git commit （コミットする）
git log （履歴を見る）
git log --graph（グラフィックに履歴書を表示）
git log --oneline（履歴を一行形式で表示）
git branch（ブランチを作る）
git checkout （チェックアウトする）
git checkout -b [ブランチ名] （ブランチの作成とチェックアウトを同時に行えます）
git checkout -f [ブランチ名]（ブランチを強制的に切り替えることができます。（コミットしていない作業データは消えるので注意））
git cat-file -p [マージコミットのID] （コミットオブジェクトを見る）
git merge [ブランチ名]（マージする）
git merge --abort（マージを中止する）
git revert [打ち消したいコミットID]（コミットを打ち消す）
git reset --soft HEAD^（直前のコミット内容を修正したい・コミットし直したい時などに使える[コミットされていたものが、ステージに移動]）
git reset --mixed HEAD（ステージしたものを取り消す。git reset HEADでもOK[ステージしていたものが、作業ディレクトリに移動するイメージ]）
git reset --hard HEAD^（ひとつ前のコミットまでまるごと消すので、取り扱い注意[すべてが指定した時点まで巻き戻しされるイメージ]）
git reflog（HEAD の移動履歴一覧を表示）
git reset --hard HEAD@{n}（特定の時点までファイルを巻き戻す（nには戻りたい地点の数字を入力））
git switch [ブランチ名]（ブランチを切り替え）
git switch -c [ブランチ名]（ブランチを新規作成して切り替える）
git restore [ファイル名]（作業ディレクトリ上の編集内容を取り消す[addする前の状態から、直前のコミットの状態に戻す]）
git restore --source [コミット識別子] [ファイル名]（特定のファイルを、特定のコミット時点に戻す）
git restore --staged [ファイル名]（ステージしたファイルを、ステージングエリアから下ろす[addしたあとの状態から、addする前に戻す]）
git diff [変更前のコミット識別子]..[変更後のコミット識別子]（特定コミット同士の差分）
git diff [ブランチ名]..[ブランチ名]（ブランチ同士の差分）
git diff origin/main..HEAD（リモートとHEADの差分）
git diff（git add前に引数無しで実行すると編集箇所と直前のコミット差分が確認できる）
git rebase -i [ひとまとめにする地点の一つ前のコミットID]（コミットをひとまとめにする）
```

## HEADとは

自分が今いる位置。たいていはブランチの先頭のコミットのこと。

`HEAD^`は1つ前のコミットという意味。`^`の数を増やすことでその数に応じていくつ戻るか指定できる。数が多い場合は`HEAD~8`のようにもかける

## 参考

[第1話 リポジトリを作ってコミットしてみよう【連載】マンガでわかるGit ～コマンド編～ \- itstaffing エンジニアスタイル](https://www.r-staffing.co.jp/engineer/entry/20190621_1?mls=i01_0001_20190719)

[第2話 ブランチとは？ポインタってどういう意味？作成・確認・切り替え方法【連載】マンガでわかるGit ～コマンド編～ \- itstaffing エンジニアスタイル](https://www.r-staffing.co.jp/engineer/entry/20190719_1)

[第3話 マージの仕組みを見てみよう【連載】マンガでわかるGit～コマンド編～ \- itstaffing エンジニアスタイル](https://www.r-staffing.co.jp/engineer/entry/20190830_1?mls=i01_0001_20190927)

[第4話 コンフリクトは怖くない！解決方法【連載】マンガでわかるGit ～コマンド編～ \- itstaffing エンジニアスタイル](https://www.r-staffing.co.jp/engineer/entry/20190927_1?mls=i01_0001_20191025)

[第5話 プッシュ済みのコミットを取り消したい！リバートの使い方【連載】マンガでわかるGit ～コマンド編～ \- itstaffing エンジニアスタイル](https://www.r-staffing.co.jp/engineer/entry/20191025_1)

[第6話 git reset 3種類をどこよりもわかりやすい図解で解説！【連載】マンガでわかるGit ～コマンド編～ \- itstaffing エンジニアスタイル](https://www.r-staffing.co.jp/engineer/entry/20191129_1)

[第7話 間違えて reset しちゃった？git reflogで元どおり【連載】マンガでわかるGit ～コマンド編～ \- itstaffing エンジニアスタイル](https://www.r-staffing.co.jp/engineer/entry/20191227_1)

[第8話 switchとrestoreを使ってみよう 【連載】マンガでわかるGit ～コマンド編～ \- itstaffing エンジニアスタイル](https://www.r-staffing.co.jp/engineer/entry/20200131_1)

[第9話 git diff で差分を確認！【連載】マンガでわかるGit ～コマンド編～ \- itstaffing エンジニアスタイル](https://www.r-staffing.co.jp/engineer/entry/20200228_1)

[これで完璧\! 図解でわかるgit rebaseの2つの使い方\! \| 侍エンジニアブログ](https://www.sejuku.net/blog/71919)