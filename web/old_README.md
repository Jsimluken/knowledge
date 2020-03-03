


## Server
- ### nginx
  - [Docker nginx+phpfpm](https://github.com/mochizukikotaro/docker-nginx-phpfpm)
## Backend
- Laravel
  - [Docker laravel](https://github.com/ucan-lab/docker-laravel)
- Flask
## Frontend
### general
### React
#### Router
- [React router v4](https://the2g.com/2789)




- [Resource of react, redux and ohers](https://github.com/markerikson/react-redux-links)


  
## Web local storage
- [indexedDB](https://developer.mozilla.org/ja/docs/Web/API/IndexedDB_API)
- [WebStorage](https://developer.mozilla.org/ja/docs/Web/API/Web_Storage_API)


## Browser Extentions
## Documentation
- [Chrome extention](https://developer.chrome.com/extensions/devguide)
## dev tool
- [Browserify](https://github.com/browserify/browserify)
- [generator-chrome-extension](https://github.com/yeoman/generator-chrome-extension)
## API
- chrome.tabs.captureVisibleTab: Take a screenshot of tab!!
## Example
- [tensorflowjs on extension](https://github.com/TakeshiOnishi/dehehe)
- [screenshot](https://github.com/mrcoles/full-page-screen-capture-chrome-extension)
- [Metamask!!](https://github.com/MetaMask/metamask-extension)





## UI
- [Material-UI](https://material-ui.com/)
  - [Templates](https://github.com/mui-org/material-ui/tree/master/docs/src/pages/getting-started/templates)

# Redux
## Tool
- [Redux DevTools](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd/related)
This is store state viewer!!

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

