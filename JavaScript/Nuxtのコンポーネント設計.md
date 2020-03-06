# Nuxtのコンポーネント設計

コンポーネント設計におけるコンポーネントの種類は2種類ある

1. Presentational Component
2. Container Component

## Presentational Component

自身は上から言われたとおりに動いて、なにか問題が起きたら自分で判断せずにすぐに上に報告する

- propsで受け取った値を表示する
- イベントが発火したときにはemitで親コンポーネントに伝播して、後の処理を委ねる。

```
ex. Page, SideBar, Story, UserInfo, List
```

## Container Component 

アプリケーションのいろはを知っている指揮官で、各部署に指示を出したり、問題が起きたときには部署からの報告をもって処理を判断する

- アプリケーションのふるまいを定義する
- 読み込んだデータをpropsで子コンポーネントに渡す
- データの読み込みやStore、Routerを知っている

```
ex. UserPage, FollowersSideBar, StoryContainer, FollowedUserList
```
