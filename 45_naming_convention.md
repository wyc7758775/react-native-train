# 4.5 Naming convention

1.Containers & Components

1.1. Container file: 
```javascript
src/containers/ModuleNameView.js
```
Component files:

```javascript
src/components/module-name-view
 - index.js
 - Main.js
 - Header.js
 - ...
 - img
   - icon@2x.png
   - icon@3x.png
```

1.2. Event name: 

```javascript
handleEventName = ()=>{//todo}
...
<MyComponent onEventName={this.handleEventName}/>
```

1.3. Render methods:

```javascript
  renderMethodName = () => {
   //todo
  }
  render() {
    return (
      <View>
        {this.renderMethodName()}
      </View>
    );
  }
````
1.4. mapStateToProps & mapDispatchToProps

```javascript
function mapStateToProps(state) {
  return {
    todos: state.todos
  };
}

function mapDispatchToProps(dispatch) {
  return {
    actions: bindActionCreators(Actions, dispatch)
  }
}
```

2.actions ```src/actions```

```
index.js
todos.js
navigation.js
```

2.1```src/constants/ActionTypes.js```

```javascript
export const SWITCH_MAIN_TAB = 'SWITCH_MAIN_TAB';

```
2.2```src/actions/todos.js````
```javascript
import * as types from '../constants/ActionTypes'

export function addTodo(title, hour) {
  return {type: types.ADD_TODO, title, hour}
}
```

3.reducers```src/reducers```
```
index.js
todos.js
navigation.js
```
3.1.```src/reducers/todos.js```
```javascript
import { ADD_TODO, DELETE_TODO, EDIT_TODO, COMPLETE_TODO } from '../constants/ActionTypes'
const initialState = []

export default function todos(state = initialState, action) {
  switch (action.type) {
    case ADD_TODO:
      //todo
    default:
      return state
  }
}

```
4.styles```src/styles```

```
index.js
Basic.js
Theme.js
```
4.1```src/styles/Basic.js```

```javascript
import { StyleSheet, Dimensions } from 'react-native';
let winSize = Dimensions.get('window');
const Basic = StyleSheet.create({
  text: {
    fontSize: 32/winSize.scale
  }
});
export default Basic;

```
4.2```src/styles/Theme.js```

```javascript
//colors
const color = {
  green: '#00551e',
  brown: '#693504',
  red: '#db2828'
}

//other
const active = {
  opacity: 0.6
}

export default {color, active}
```
4.3```import {Theme, BasicStyle} from '../../styles';```