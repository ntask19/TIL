# Nuxt.jsのasyncDataとfetchの使い分け

サーバサイドからデータを取得するためのメソッドの2つをどう使い分けるのか

## asyncDataとfetchについて

- asyncDataとfetchはいずれもcomponentがロードされる前に呼び出され、外部からデータを取得する際に使用される。
- いずれもcomponentのインスタンスが生成される前に実行されるので、thisからcomponentのインスタンスにアクセスすることはできない。


## asyncDataの使用タイミング

- 返り値をcomponentにセットすることができる
- componentにデータをセットしたいときに使う 

```JavaScript
  export default {
    async asyncData({}) {
      const data = await axios.get('localhost:8000') 
      return { title: data.title }
    },
  }
```


## fetchの使用タイミング

- fetchメソッドは、ページがレンダリングされる前に、データをstoreに入れるために使われる。
- componentのデータをセットしない点がasyncDataと異なる。
- データをcommitしたり、dispatchしたいときに使う

```JavaScript
  export default {
    async fetch({ store }) {
      const data = await axios.get('localhost:8000') 
      store.commit('setStars', data)
    },
  }
```
