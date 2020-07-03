## 编写习惯

- 三联运算符

- 连接字符串用模板字符串

- 箭头函数的使用

## 压缩

GZIP压缩

Brotli （br）：比其他压缩算法更多地减少资源的文件大小

## 缓存

memory cache 内存缓存

disk cache 磁盘缓存

**禁止缓存**

Cache-Control: no-store

**缓存静态资源**

Cache-Control:public, max-age=31536000

**需要重新验证**

指定 no-cache 或 max-age=0 表示客户端可以缓存资源，每次使用缓存资源前都必须重新验证其有效性。这意味着每次都会发起 HTTP 请求，但当缓存内容仍有效时可以跳过 HTTP 响应体的下载。

Cache-Control: no-cache

Cache-Control: max-age=0

## babel

Babel默认只转换新的JavaScript句法（syntax），而不转换新的API，比如Iterator、Generator、Set、Maps、Proxy、Reflect、Symbol、Promise等全局对象，以及一些定义在全局对象上的方法（比如Object.assign）都不会转码

npm install --save @babel/runtime-corejs3

npm install --save-dev @babel/plugin-transform-runtime

```
{
  "presets": ["@babel/preset-env"],
  "plugins": [
    [
      "@babel/plugin-transform-runtime",
      {
        "corejs": 3
      }
    ]
  ]
}
```
