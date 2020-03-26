# RenderFlex children have non-zero flex but incoming height constraints are unbounded. のエラー

## 発生した問題

Flutterで以下のエラーが出て、進行不能。

```
RenderFlex children have non-zero flex but incoming height constraints are unbounded.
```

プログラムは以下

```dart:main.dart
SingleChildScrollView(
  child: Column(
    children: <Widget>[
      Expanded(
        child: Text('テキストです。')
      ),
    ],
  ),
);
```

## 環境

- macOS Catalina 10.15.1
- Android Studio 3.6.1
- Flutter 1.12.13


## 結論

`Column` 直下の `Expanded` を外して、子Widgetのサイズを見直すことで解決。


## 原因

スクロールができることで、Widgetの高さに制限がなったColumnが子WidgetのExpandedが高さを埋めるのに合わせて、無限に大きくなってしまったこと。

本来ならば、親Widgetの最大まで埋めてくれるのがExpandedですが、columnに高さの上限値がないとこのようなエラーが起きる模様。

```dart:main.dart
SingleChildScrollView(
  child: Column(
    children: <Widget>[
      Expanded(
        child: Text('テキストです。')
      ),
    ],
  ),
);
```

## 参考記事

Flutter RenderFlex children have non-zero flex but incoming height constraints are unbounded
https://stackoverflow.com/questions/59291894/renderflex-children-have-non-zero-flex-but-incoming-height-constraints-are-unbou

Column class(そもそもドキュメントでも注意されていました…)
https://api.flutter.dev/flutter/widgets/Column-class.html
