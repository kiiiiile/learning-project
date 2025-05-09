# Tools

1. classNames - 用于生成类名的工具库，支持嵌套和条件生成。

```tsx
import classNames from 'classnames';

// 生成类名
const className = classNames('class1', { class2: true, class3: false });
console.log(className); // 输出：'class1 class2'
```

2. lodash - 一个 JavaScript 工具库，提供了许多实用的函数和方法，用于处理数组、对象、字符串等。

```tsx
import _ from 'lodash';

// 过滤数组中的元素
const array = [1, 2, 3, 4, 5];

// 使用 lodash 的 filter 方法过滤数组中的元素
const filteredArray = _.filter(array, (num) => num > 3);
console.log(filteredArray); // 输出：[4, 5]
```

3. dayjs - 一个轻量级的 JavaScript 日期处理库，提供了丰富的日期和时间操作方法。

```tsx
import dayjs from 'dayjs';

// 获取当前日期和时间
const now = dayjs();
console.log(now.format('YYYY-MM-DD HH:mm:ss')); // 输出：当前日期和时间
```

4. react-router-dom - 用于在 React 应用中实现路由功能的库，提供了路由管理、导航等功能。

```tsx
import { BrowserRouter as Router, Route, Link } from 'react-router-dom';

// 定义路由组件
const App = () => {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/about">About</Link>  
            </li>
          </ul>
        </nav>

        <Route path="/" exact component={Home} />
        <Route path="/about" component={About} />
      </div>
    </Router>
  );

}
```

5. axios - 一个基于 Promise 的 HTTP 客户端库，用于发送 HTTP 请求和处理响应。

```tsx
import axios from 'axios';

// 发送 GET 请求
axios.get('URL_ADDRESSaxios.get('api.example.com/data')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });

// 发送 POST 请求
axios.post('URL_ADDRESS', { name: 'John', age: 30 })
 .then(response => {
    console.log(response.data);
  })
 .catch(error => {
    console.error(error);
  });
```

6. react-query - 一个用于管理和缓存异步数据的库，提供了简单易用的 API，用于处理数据获取、缓存和更新等操作。

```tsx
import { useQuery } from 'react-query';

// 定义一个异步函数来获取数据
const fetchData = async () => {
  const response = await axios.get('URL_ADDRESS');
  return response.data;
};

// 使用 useQuery 钩子来获取数据
const App = () => {
  const { data, isLoading, error } = useQuery('data', fetchData);  
  if (isLoading) {
    return <div>Loading...</div>; 
  }
}
```
