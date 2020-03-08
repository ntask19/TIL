# Sassファイルのコンパイル

Sassファイルをnode-sassでコンパイルするときに使った方法のメモ

## 導入

```
$ yarn global add node-sass
```

## 使い方

開発用に使用する(ファイル更新時にコンパイル)

```
$ node-sass {コンパイル元}.scss {コンパイル先}.css -w
```

本番公開用に使用する(圧縮コンパイルする)

```
$ node-sass {コンパイル元}.scss {コンパイル先}.css --output-style compressed
```
