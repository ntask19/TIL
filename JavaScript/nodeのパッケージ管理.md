# nodeのパッケージ管理

- nodeのパッケージ管理にはnpmとyarnがある
- npmはアプリによってバージョン管理がややこしいので、 [nodebrew](https://github.com/hokaccha/nodebrew) を使うと良い


## npmかyarnか

- yarnの方が後に出た技術ではあるが、多くのコマンドがnpmに似ている
- yarnはダウンロードしたパッケージはキャッシュ化しているので、一度インストールしたパッケージの再インストールは速い
- ローカルパッケージの実行が簡単
