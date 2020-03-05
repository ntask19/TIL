# direnv

## Overview

ディレクトリ毎に環境変数を分けたいときに使う。各ディレクトリ内に `.envrc` を設置し、そこに定義した環境変数を読み込んでくれる。
読み込むのは、対象のディレクトリに移動したときのみ。

リポジトリはこちら

https://github.com/direnv/direnv


## Install

brewでインストール

```
$ brew install direnv
```

シェルにhookを追加する。bashの人はzshの箇所をbashにすればOK。

```zsh:~/.zshrc
eval "$(direnv hook zsh)"
```

設定のリロードをすることでdirenvの導入は完了

```
source ~/.zshrc
```

もし、 `direnv: error .envrc is blocked. Run `direnv allow` to approve its content.` というエラーが出たら以下のようにする。

```
$ direnv allow .
```

## Usage

`.envrc` を作ってそこに環境変数を定義していく。(`.env` と考え方は同じ)

```
$ direnv edit .
```
