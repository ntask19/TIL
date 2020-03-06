# Vuexについて

Vuexについて不明瞭になっていたところを明らかにする。

## overview

Fluxの流れを組んだアーキテクチャで、データの流れは以下の通り

![データの流れ](https://raw.githubusercontent.com/facebook/flux/master/examples/flux-concepts/flux-simple-f8-diagram-with-client-action-1300w.png)
https://github.com/facebook/flux/tree/master/examples/flux-concepts より

### Action 

一連の処理の流れを管理する機構。

バックエンドのAPIからデータを取得する処理はこちらで行う。また、commitをすることでMutation内の関数を呼び出す処理はAction内で行う。

非同期処理が可能。

### Mutation

Stateを更新するための機構。

Mutationの関数を直接呼ぶことはできずに、`store.commit()` でmutationに登録している関数を呼び出すことができる。なお、こちらは非同期処理はできない。

### State

Storeで管理している状態やデータ。

このデータを直接参照したり、変更したりすることはせずにGetterやMutationで値の管理を行う。

### Getter

stateのデータを参照するためのGetterメソッド。

必要に応じてデータを加工して、viewに返すことができる。


## Sample

```JavaScript
export const state = () => ({
  eventDataList: {}
})

export const getters = {
  eventDataList: state => state.eventDataList
}

export const mutations = {
  setEventDataList(state, eventDataList) {
    state.eventDataList = eventDataList
  }
}

export const actions = {
  async fetchEventDataList({ commit }) {
    const eventDataList = await this.$api.getEventList()
    commit('setEventDataList', eventDataList )
  }
}
```

## Tips

- コンポーネントからmutationもactionも呼び出すことができるので、チームの方針によって全てaction経由で呼び出すのか、mutationとactionを併用するのかを決める必要がある
- propsでデータを橋渡ししていた処理もVuexを使うことでデータ管理がしやすくなる
