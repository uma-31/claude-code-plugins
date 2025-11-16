# go-learning-plugin

Go 言語学習支援用の Claude Code プラグインです。

## 前提

Go や Golangci-lint が利用可能な環境であること。

## インストール

```bash
/plugin marketplace add uma-31/claude-code-plugins
/plugin install go-learning-plugin@umarket
```

## 使い方

まずは、学習用のプロジェクトを配置するディレクトリを作成します。

```bash
mkdir go-learning
cd go-learning
```

この際、`CLAUDE.md` を作成し、下記のような内容を記載することを推奨します。

```markdown
# Go Learning Project

## 学習者について

- プログラミング経験: [例: Web バックエンド開発 3 年（TS, Perl）]
- Go 言語への理解度: [例: 基本的な文法は理解しているが、実務経験はない]
- Go で作ってみたいもの: [例: Web アプリケーション、CLI ツール、ライブラリなど]
- 学習の目的: [例: 実務で利用するため、趣味で利用するためなど]
```

準備が整ったら、Claude Code を起動します。

```bash
claude
```

続いて、`/go-learning-plugin:propose` コマンドを実行します。
コマンドには、今あなたが学びたいテーマを指定してください。

```bash
/go-learning-plugin:propose 並列処理とコンテキストの基本的な使い方
```

このコマンドでは、学習テーマに基づいて課題を提案し、最終的に選択した課題のディレクトリと `CHALLENGE.md` を作成します。
次に、作成されたディレクトリへ移動し、`/go-learning-plugin:start` コマンドで課題を開始します。

```bash
cd <提案された課題のディレクトリ>
claude
```

```bash
/go-learning-plugin:start
```

`/go-learning-plugin:start` コマンドは、`TODO.md` ファイルを始めとした、
学習を進めるために必要なファイルを作成します。

準備が整ったら、`/go-learning-plugin:guide` コマンドで課題を進めていきます。

```bash
/go-learning-plugin:guide
```

`/go-learning-plugin:guide` コマンドは、`TODO.md` に基づいて次のタスクを案内します。
不明点があれば質問し、タスクが完了したらレビューを依頼しましょう。
承認されると次のタスクに進み、すべてのタスクを完了すると課題達成となります。

## ライセンス

MIT
