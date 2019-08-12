# Redux TODO(draft)

## Make a action creator

Example
``` javacript:action/index.js

export const INCREMENT = 'INCREMENT'
export const DECREMENT = 'DECREMENT'

export const increment = () => ({
  type: INCREMENT
})

export const decrement = () => ({
  type: DECREMENT
})
```
これがアクションクリエータでtypeを返す関数なんだとか


## Implement reducer

``` javascript:reducers/count.js
import { INCREMENT, DECREMENT } from '../actions'

const initialState = { value: 0 }

export default (state = initialState, action) => {
  switch (action.type) {
    case INCREMENT:
      return { value: state.value + 1 }
    case DECREMENT:
      return { value: state.value - 1 }
    default:
      return state
  }
}
```

```javascript:reducers/index.js
import { combineReducers } from 'redux'
import count from './count'

export default combineReducers({ count })
```



reducerを使う前はstateはcomponentで管理していたが、reducerを使えば一元管理される?
actionのtypeで条件分岐し、stateの値を弄るような関数

index.jsではcombineReducerでreducerをまとめてexport(今回は一つなので恩恵なし)

## Main js
```javascript:index.js
import { createStore } from 'redux'
import { Provider } from 'react-redux'
import reducer from './reducers'

const store = createStore(reducer)

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);
```
前の段階で作ったreducerでstoreを作成
Providerでrootコンポーネントに渡して上げることで下位のコンポーネントも楽々使える(はず)

## Dispatch

```javascript:app.js
import React, { Component } from 'react';
import { connect } from 'react-redux'

import { increment, decrement } from '../actions'

class App extends Component {
  render() {
    const props = this.props

    return (
      <React.Fragment>
        <div>value: { props.value }</div>
        <button onClick={props.increment}>+1</button>
        <button onClick={props.decrement}>-1</button>
      </React.Fragment>
    )
  }
}

const mapStateToProps = state => ({ value: state.count.value })

 const mapDispatchToProps = dispatch => ({
   increment: () => dispatch(increment()),
   decrement: () => dispatch(decrement())
 })



export default connect(mapStateToProps, mapDispatchToProps)(App)
```

ここでactionを呼び出してる？らしいがようわからん。
props.incrementとやることであのactionのincrementを指しているのか？
connectでAppコンポーネントとactionを結びつけていた気がする(要検証)




## 参考
- [udemy-react-redux-crud-application](https://github.com/gipcompany/udemy-react-redux-crud-application) 混乱した
- [【React.js】createStoreを実装してみたらReduxの理解が捗った](https://qiita.com/miyarappo/items/30fff8d23704e92211b7)しっかり読んでない






