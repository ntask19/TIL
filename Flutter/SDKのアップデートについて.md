# SDKのアップデートについて

## overview

SDKのアップデートは

```
$ flutter upgrade 
```

でできるが、channelが違うと目的のバージョンに変更できない。

https://flutter.dev/docs/development/tools/sdk/releases?tab=macos

そこで、変更したいバージョンに対応しているchannelに切り替えてあげる

## channelの確認

```
$ flutter channel
Flutter channels:
  master
  dev
* beta
  stable
```

## channelの切り替え

```
$ flutter channel beta
```
