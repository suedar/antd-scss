# antd-scss


## 问题描述
各位基友好，由于 `antd` 使用的是 `less` 进行 `css` 预处理, 因此想要[定制主题](https://ant.design/docs/react/customize-theme-cn)，必须在业务相应得使用 `less`。

那么对于 `sass` 爱好者，定制主题采用官方的方法是不可行的，因为定制主题是使用对 `less` 的 `css` 变量进行更改，因此我们在业务中需要引入的是 `antd` 的 `less` 版本的 `css`，然后对变量进行相应更改。

也就是说我们不可避免得需要引入 `less-loader`, 而 `sass-loader` 与 `less-loader` 会冲突，因此官方的路走不通。


因此我把编译后的完整版的 `css` 下载下来，并把一些主题色替换为 `css` 变量。
并上传到百度云，链接为：https://antd-scss.bj.bcebos.com/antd.css

如此便让 `sass` 跟定制主题相兼容了。

## 解决方法

### 1
```
// App.js
import './App.scss';

// App.scss
@import "https://antd-scss.bj.bcebos.com/antd.css";
:root {
  --primary-color: #1890ff; /* 全局主色 */
  --success-color: #52c41a; /* 成功色 */
  --warning-color: #faad14; /* 警告色 */
  --error-color: #f5222d; /* 错误色 */
  --font-size-base: 14px; /* 主字号 */
  --heading-color: rgba(0, 0, 0, 0.85); /* 标题色 */
  --text-color: rgba(0, 0, 0, 0.65); /* 主文本色 */
  --text-color-secondary: rgba(0, 0, 0, 0.45); /* 次文本色 */
  --disabled-color: rgba(0, 0, 0, 0.25); /* 失效色 */
}
```

在根目录全局引入后，更改 `root` 里面的 `css` 变量即可。

或者你也可以把这个文件下载在本地。

### 2
或者你可以试试[antd-scss-theme-plugin](https://www.npmjs.com/package/antd-scss-theme-plugin)。
