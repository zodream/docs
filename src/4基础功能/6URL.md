## URL

使用 `url()` 生成网址

特殊路径

    /      返回主页

    null    返回当前网址

    ./      返回当前模块的主页

    -1      返回来源

## 生成基础 URL

```php
url($path, $params, $secure): string;
```

    $path 路径
    $params 参数
    $secure http/https/ftp

变种写法

#### 假定当前网址为 https://zodrean.cn

`url(): Zodream\Infrastructure\Contracts\UrlGenerator` 无参数

`url('./'): string` 为当前模块的首页，如果无模块则为全站首页

`url('/post', ['id' => 1]): string`  输出的内容为 `https://zodrean.cn/post?id=1`

`url('/post', ['id' => 1], false): string`  则输出 `http://zodrean.cn/post?id=1`，注意：当前启用路由重写是，  第三个参数为不启用路由重写

参数可变规则：

`url(['/post', 'id' => 1], false): string` 第一个参数为数组，则会提取里面的路径，把其他参数替换为第二个参数，第二个参数为非数组时会视作三个参数。

`url('/post', false): string` 输出的内容为 `http://zodrean.cn/post`


## 访问当前 URL

`url()->current(): string` 不带参数

`url()->full(): string` 完整的当前网址

## 输出资源的 URL

`url()->asset(string $path, $secure = null): string` 不会进行其他更多优化改变操作