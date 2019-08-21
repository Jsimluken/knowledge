# WEB

## Redux

### Tutorial
- [Redux(official)](https://redux.js.org/introduction/getting-started)

### 用語

#### Action
```
{
  type: 'ADD_TODO',
  text: 'Build my first Redux app'
}
```
- 何が起こったかを司る
- Actionは必ずtypeを持つ(string型)
- その他適当な情報を持っても良い
```
function addTodo(text) {
  return {
    type: 'ADD_TODO',
    text
  }
}
```
こんな感じでActionCreatorによって作られる

#### Reducer
```
function todos(state = [], action) {
  switch (action.type) {
    case ADD_TODO:
      return [
        ...state,
        {
          text: action.text,
          completed: false
        }
      ]
    case TOGGLE_TODO:
      return state.map((todo, index) => {
        if (index === action.index) {
          return Object.assign({}, todo, {
            completed: !todo.completed
          })
        }
        return todo
      })
    default:
      return state
  }
}

```
- Actionを受けてどう変更をするかを司る
- こんな感じでActionで場合分け
#### Store
- ActionとReducerを結ぶ(dispatchとかで)
- アプリケーション状態の一元管理

